# Chum

**Content-addressed object storage on AT Protocol.**

Chum is a bucket-style object store built directly on the AT Protocol substrate. Objects are addressed by their content digest — immutable, de-duplicated, and verifiable by construction. A mutable naming layer maps human-meaningful `bucket/key` names onto content IDs, so you get familiar object-store ergonomics over a substrate that is verifiable across time.

We don't add verifiability to storage. We refuse to discard the verifiability the substrate already has.

## Why

Conventional object stores treat integrity and history as features to bolt on — checksums you have to trust, audit logs you hope weren't rewritten. AT Protocol repositories are signed, append-only Merkle structures; blobs are content-addressed. Chum exposes those properties instead of hiding them:

- **Content integrity is intrinsic.** An object's identity *is* its content digest. Change a byte, change the address — there's no metadata gap to trust.
- **History is a chain, not a log.** Every change to a name→content-ID pointer is a signed record linked to its predecessor. What a name resolved to, and when, is reconstructable and tamper-evident.

## Repositories

| Repo | What it is |
|---|---|
| `chum` | Core service — bucket API, object PUT/GET/HEAD/DELETE, multipart |
| `pointer` | Name→content-ID mutable pointer layer and signed mutation chain |
| `lexicons` | AT Protocol lexicon definitions Chum publishes and consumes |
| `pellets` | Content-keyed edge cache (compressed, locally-extractable warm tier) |
| `chum-cli` | Command-line client — push, fetch, and verify objects by content ID |
| `sdk-go` / `sdk-ts` | Client libraries |
| `docs` | Source for the documentation site |

## Status

Early. Building in public. The design decisions — and the ones still open — are documented as they happen.

## Links

- Site & docs: [chum.blue](https://chum.blue)
- Developer tools: [chum.tools](https://chum.tools)
- On Bluesky: [@chum.blue](https://bsky.app/profile/chum.blue)
- Contact: hello@chum.blue · Security: security@chum.blue
