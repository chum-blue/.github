# Contributing to Chum

Chum is content-addressed object storage on AT Protocol, built in public. Thanks
for considering a contribution.

This guide applies across the Chum repositories — `chum` (core service),
`pointer`, `lexicons`, `pellets`, `chum-cli`, and the SDKs. Build and run
specifics live in each repo's own `README.md`; this document covers how we work
together.

> **Status: early.** APIs change, decisions are still open. That makes this a
> good time to contribute — the design is still being shaped in the open.

## The most useful contribution right now

It's discussion. Several core decisions are deliberately unsettled and tracked
in `docs/decisions` (for example: auth on the data path, substrate hosting, and
where the signed pointer chain lives). A well-argued issue on one of those is
worth more than a speculative PR against a part of the system that may still
move.

So: **open an issue before a large or structural PR.** It saves you from
building against a decision that hasn't landed. Small, obvious fixes (typos,
clear bugs, docs) can go straight to a PR.

## Ground rules

- **Don't break the proof.** Chum's value is that an object's identity *is* its
  content digest, and a name's history is a signed, append-only chain. Changes
  that weaken content-addressing, the mutation chain, or their verifiability need
  an explicit, reviewed rationale — not an incidental one.
- **Match the existing code.** Read the surrounding code and mirror its
  conventions, naming, and structure before introducing new patterns.
- **Tests come with behavior.** New behavior lands with tests; bug fixes land
  with a test that fails before the fix and passes after.
- **No overclaim.** Docs and copy state what the code actually does today.
  In-progress work is described as in progress.

## Development workflow

1. Fork and clone the repo you're working in.
2. Create a branch off `main`.
3. Make your change. Keep the diff focused — one concern per PR.
4. Run that repo's test suite and make sure it's green. For the Go services
   (`chum`, `pointer`) that's `go test ./...` from the repo root, plus
   `gofmt`/`go vet`. JS/TS repos use their package scripts.
5. Open a PR against `main` with a clear description of what changed and why.

## Commits and PRs

- We use [Conventional Commits](https://www.conventionalcommits.org): a `type`
  prefix (`feat`, `fix`, `docs`, `refactor`, `test`, `chore`, `deploy`) and a
  short, imperative subject — e.g. `feat(pointer): verify prev-CID on append`.
- Keep the subject under ~50 characters; use the body to explain *why* when it
  isn't obvious from the diff.
- Squash noise before requesting review; each commit should make sense on its
  own.
- A PR that closes an issue should say so (`Closes #N`).

## Reporting bugs

Open an issue with what you expected, what happened, and the smallest steps to
reproduce. For anything involving object bytes, content IDs, pointer records, or
access grants that has a **security** dimension, do not open a public issue —
follow [SECURITY.md](./SECURITY.md) and email security@chum.blue.

## Code of conduct

Participation in the Chum community is governed by our
[Code of Conduct](./CODE_OF_CONDUCT.md). By participating, you're expected to
uphold it. Report unacceptable behavior to hello@chum.blue.

## Questions

General questions: hello@chum.blue, or [@chum.blue](https://bsky.app/profile/chum.blue)
on Bluesky. For how a piece of the system works, the repo's `docs/` and the
open-decisions notes are the best starting point.
