---
type: Reference
title: REST API Design Rulebook
tags: [rest, api-design, http, uri, hypermedia, hateoas, web-architecture]
timestamp: 2026-07-14
source: https://www.oreilly.com/library/view/rest-api-design/9781449317904/
---

# REST API Design Rulebook

Mark Massé's *REST API Design Rulebook* (O'Reilly, 2012) is a style guide for
designing REST APIs. Its premise is that most REST APIs differ from one another far
more than they need to: the web's architectural style already dictates most of the
answers, so a well-designed API should feel *predictable* to anyone who knows the
web. The book turns that predictability into a concrete set of prescriptive rules,
each phrased with RFC-2119 force (`must` / `should` / `may`), covering URIs, HTTP
usage, metadata, representations, and client concerns.

## REST as a set of design constraints

REST (Representational State Transfer) is a description of how the web achieves its
scale — effectively the web's "operating system." An API earns the label REST by
honoring the constraints of the web's architectural style:

- **Client–server** — separate the UI/consumer from data storage, so each evolves
  independently.
- **Uniform interface** — the single most defining constraint: resources are
  identified by URIs, manipulated through representations, described by
  self-descriptive messages, and driven by hypermedia (HATEOAS). Uniformity is what
  lets generic clients talk to any resource.
- **Layered system** — intermediaries (proxies, gateways, caches) can sit between
  client and server without either knowing.
- **Cache** — responses declare their own cacheability, cutting round trips.
- **Stateless** — each request carries everything needed to process it; the server
  keeps no client session state.
- **Code-on-demand** (optional) — servers may extend clients by shipping executable
  code (e.g. JavaScript).

The book's stance: a REST API should be *designed*, not coded incidentally — ideally
with tooling and shared conventions, because consistency across an organization's
APIs is itself a productivity win.

## URI design

URIs name resources. The rules keep them clean, hierarchical, and noun-oriented:

- **Forward slash `/`** indicates a hierarchical relationship between path segments.
- **No trailing slash** — a URI must not end in `/`.
- **Hyphens over underscores** — use `-` to improve readability; avoid `_` (it can be
  obscured by link underlining).
- **Lowercase** letters are preferred in the path (schemes and hosts are already
  case-insensitive; the path is not, so keep it lower).
- **No file extensions** — don't put `.json`/`.xml` in the URI; use content
  negotiation to select a format instead.
- Use **consistent subdomains** — e.g. `api.example.com` for the API and
  `developer.example.com` for the developer portal.

### Resource archetypes

Every resource should be modeled as one of four archetypes, and its URI naming
follows from the choice:

| Archetype | What it is | URI naming |
|-----------|------------|------------|
| **Document** | A single resource, like one record or object | Singular noun (`/customer/1234`) |
| **Collection** | A server-managed directory of resources | Plural noun (`/customers`) |
| **Store** | A client-managed resource repository (the client picks IDs and puts resources in) | Plural noun (`/users/1234/playlists`) |
| **Controller** | A procedural concept — an executable action that isn't naturally CRUD | Verb / verb phrase (`/alerts/245/resend`) |

Other path rules: variable segments may be substituted with identity values
(`/users/{id}`), and **CRUD function names must not appear in URIs** — the HTTP method
already conveys the operation, so `/deleteUser?id=1` is wrong; `DELETE /users/1` is
right. The **query component** is for filtering and paginating collections and stores
(`?color=red`, `?page=2&size=20`) — not for identifying resources.

## HTTP method semantics and status codes

HTTP methods carry the operation; they must not be tunneled through `GET`/`POST`:

- **GET** — retrieve a representation (safe, idempotent).
- **HEAD** — retrieve headers only.
- **PUT** — insert or update a stored resource; used to update mutable resources.
- **POST** — create a new resource *in a collection*, or execute a *controller*.
- **DELETE** — remove a resource from its parent.
- **OPTIONS** — retrieve metadata describing a resource's available interactions.

See [HTTP query method](http-query-method.md) for how the query string layers onto
`GET` for filtering, pagination, and partial/embedded responses.

Status codes are used specifically, not loosely:

- **2xx success** — `200 OK` for nonspecific success (but never to wrap an error in
  the body), `201 Created` for resource creation, `202 Accepted` for an async action
  that has started, `204 No Content` when the body is intentionally empty.
- **3xx redirection** — `301 Moved Permanently`, `303 See Other` (point client to a
  different URI), `304 Not Modified` (conditional GET, saves bandwidth),
  `307 Temporary Redirect`. `302 Found` should be avoided.
- **4xx client error** — `400 Bad Request` (nonspecific), `401 Unauthorized`
  (credential problem), `403 Forbidden` (denied regardless of auth), `404 Not Found`,
  `405 Method Not Allowed`, `406 Not Acceptable` (can't produce the requested media
  type), `409 Conflict` (resource-state violation), `412 Precondition Failed`
  (conditional operations), `415 Unsupported Media Type`.
- **5xx server error** — `500 Internal Server Error` for API malfunction.

The cardinal rule: **never return `200` and stuff an error inside the body.** The
status code is the primary signal.

## Metadata design (headers, media types, negotiation)

Metadata lives in HTTP headers and media types:

- **Headers** — `Content-Type` must be present; `Content-Length` should be.
  `Last-Modified` and `ETag` on responses enable caching and conditional requests;
  stores must support conditional `PUT`. `Location` gives the URI of a newly created
  resource. `Cache-Control`, `Expires`, and `Date` encourage caching; caching should
  generally be encouraged, especially on `200` responses. **Custom headers must not
  change the behavior of HTTP methods** — they may only carry extra metadata.
- **Media types** — follow the `type/subtype` syntax. Prefer registered types, but
  design **application-specific (vendor) media types** (e.g.
  `application/vnd.example.customer+json`) to describe an API's own representations.
- **Content negotiation** — when multiple representations exist, support negotiation
  via the `Accept` header; a query-parameter fallback for media-type selection *may*
  be offered.

## Representation design

Representations are the actual message bodies. The rules push hard toward
consistency and hypermedia:

- **Format** — JSON should be supported and must be well-formed. XML and others may
  also be offered. **Do not wrap responses in an extra envelope** — HTTP already
  provides the envelope (status + headers).
- **Hypermedia / HATEOAS** — a consistent form should represent links and link
  relations, and links should be *advertised* in the representation so clients can
  discover a resource's available actions in a state-sensitive way. Every response
  body should include a **self link**. Keep the number of advertised "entry point"
  URIs small — clients navigate from there by following links rather than
  constructing URIs. This is the constraint that makes an API self-describing and
  keeps clients loosely coupled to URI structure.
- **Error bodies** — use a **consistent form** for both errors and error responses,
  and reuse consistent error *types* for common conditions, so clients can handle
  failures uniformly.

## Client concerns and versioning

- **Versioning** — introduce genuinely *new concepts* at *new URIs*; use **schemas**
  to manage versions of representational *form*; use **entity tags (ETags)** to manage
  versions of representational *state*. The book deliberately avoids baking version
  numbers into every URI path as the default lever.
- **Security** — protect resources with OAuth and/or API-management solutions.
- **Response composition** — support **partial responses** and **embedding linked
  resources** through the query component, so clients can shape payloads.
- **JavaScript clients** — support **JSONP** for multi-origin *read* access and
  **CORS** for multi-origin *read/write* access.

## How this connects to broader design

The rulebook's emphasis on a uniform interface, stable URIs, and hypermedia-driven
navigation is the API-boundary expression of the same instinct behind
[Clean Architecture](clean-architecture.md): keep the stable contract (here, the
resource model and its representations) decoupled from volatile implementation
details, so that consumers depend on an interface that changes slowly and
predictably.

## References

- [REST API Design Rulebook — O'Reilly](https://www.oreilly.com/library/view/rest-api-design/9781449317904/)
