# Security Policy

Chum stores other people's data. We take reports seriously and respond quickly.

## Reporting a vulnerability

Email **security@chum.blue** with:

- a description of the issue and its impact,
- steps to reproduce (a proof of concept if you have one),
- any affected versions, components, or endpoints.

Please report privately first. Do not open a public issue, and do not disclose
publicly until we've had a chance to investigate and ship a fix.

## What to expect

- **Acknowledgement** within 3 business days.
- **An initial assessment** (severity, whether we can reproduce) within 7 business days.
- **Progress updates** as we work toward a fix.
- **Credit** in the release notes once resolved, if you'd like it.

## Scope

In scope: the `chum` core service, the `pointer` layer, `chum-cli`, the SDKs, and
anything that handles object bytes, content IDs, pointer records, or access grants.

Out of scope: issues in third-party dependencies (report those upstream, but tell
us so we can pin or patch), and findings that require physical access or a
compromised maintainer account.

## Safe harbor

We will not pursue or support legal action against anyone who reports a
vulnerability in good faith, follows this policy, and avoids privacy violations,
data destruction, or service disruption while testing.
