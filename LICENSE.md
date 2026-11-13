# Licensing

> **Status.** The owner chose these licences on 2026-11-13. They take effect once counsel
> has reviewed this page and the [patent commitment](PATENTS.md). Before publishing, add
> the official licence texts as the files named below, copied unchanged from the official
> sources.

## Which licence applies to what

| Material | Licence | Licence file |
|---|---|---|
| The specification text: the ontology, the language specification, the compiler specification and the documents in `docs/` | Creative Commons Attribution 4.0 International (**CC-BY-4.0**) | `LICENSE-CC-BY-4.0.txt`, from https://creativecommons.org/licenses/by/4.0/legalcode.txt |
| The schema `openappl.json`, every file in `versions/`, and the example blueprints in `examples/` | Apache License, Version 2.0 (**Apache-2.0**) | `LICENSE-APACHE-2.0.txt`, from https://www.apache.org/licenses/LICENSE-2.0.txt |

Why two licences: the specification is prose, which is best shared under a documentation
licence that only asks for attribution; the schema and the examples are machine-readable
files that tools and compilers copy into their own code, which an open-source software
licence with an explicit patent grant covers better.

## What this means in practice

- You may read, copy, translate, quote and redistribute the specification, including in
  commercial products, as long as you credit "OpenAPPL, stewarded by Mindbricks Labs" and
  link to the source.
- You may use, copy, modify and ship `openappl.json` and the examples inside your own
  tools, compilers and products, open or closed, under the terms of Apache-2.0.
- **Your blueprints are yours.** The licences of the Specification do not extend to the
  blueprints you write with the language, nor to the code a compiler generates from them.
  The terms of generated code are set by the compiler you use.
- Implementing the Specification does not require a licence from the steward. Patent
  rights are covered by the commitment in [PATENTS.md](PATENTS.md).
- The licences do not grant rights to the name "OpenAPPL" or to the steward's names and
  logos; see section 7 of [GOVERNANCE.md](GOVERNANCE.md).

## Contributions

By submitting a contribution (a change proposal, text, a schema change or an example) to
this repository, you agree that it is licensed under the licence of the material it
changes, as listed above, and that the patent commitment in [PATENTS.md](PATENTS.md)
extends to the parts of the Specification your contribution adds.

Every commit must carry a **Developer Certificate of Origin** sign-off
(https://developercertificate.org): a `Signed-off-by: Name <email>` line, added with
`git commit -s`. By signing off you certify that you wrote the contribution, or otherwise
have the right to submit it under these terms. No separate contributor licence agreement
is required.

## Copyright

Copyright © 2026 Mindbricks Labs and the OpenAPPL contributors.
