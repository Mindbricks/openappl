# About OpenAPPL

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

OpenAPPL, the Open Application Pattern Language, is an open specification for describing
complete application backends at the level of business decisions. This page says who is
behind it: who stewards and supervises the standard, who sponsors the work, and how
anyone else can take part.

> **Status.** The owner of the standard took the governance decisions on 2026-11-13. The
> licences and the patent commitment take effect once counsel has reviewed their texts.

## The standard

OpenAPPL is three documents and one schema file:

- the [ontology](https://openappl.org/ontology) (Part 1): which patterns exist and how they relate;
- the [language specification](https://openappl.org/spec) (Part 2): every pattern, its properties,
  types, defaults and rules;
- the [compiler specification](https://openappl.org/compiler) (Part 3): what a conforming compiler
  must produce from a blueprint;
- the schema [`openappl.json`](https://openappl.org/spec/openappl-json), whose version is the version of
  the language.

All four are public. Anyone may read them, implement them and build tools or compilers on
them. See [Policy](policy.md) for the principles, versioning and licences.

## Stewardship

OpenAPPL is stewarded by **[Mindbricks Labs](https://mindbricks.com)**, where the language
originated. As steward, Mindbricks Labs:

- maintains the ontology, the language specification and the compiler specification;
- reviews and approves every change to them, and publishes the releases of the schema;
- maintains [Genesis](compilers.md), the first OpenAPPL compiler and today the reference
  implementation of the standard;
- runs this website.

The language itself is vendor-neutral. Stewardship is a responsibility for keeping the
standard coherent and published, not a claim on the blueprints people write or on the
systems they generate.

## Supervision and governance

The model is described in full in the
[Stewardship and governance statement](../GOVERNANCE.md):

- Mindbricks Labs, as steward, supervises the standard and decides on every change.
- Anyone may propose a change, with the need, the evidence from real systems, the new or
  changed patterns and the expected compiler behaviour.
- Implementers of conforming compilers are consulted on every change that affects the
  compiler specification.
- Proposals are submitted and decided through the [RFC process](../rfcs/README.md).

- Editors may come from any organisation; the steward appoints them.
- An **Advisory Group** of implementers and users gives a recorded opinion on changes that
  affect the compiler specification or break compatibility. It is formed as soon as a
  second, independent conforming compiler exists.
- Everyone taking part follows the [code of conduct](../CODE_OF_CONDUCT.md)
  (Contributor Covenant 2.1).

## Sponsorship

The development of OpenAPPL, the reference compiler and this website is funded by
**[Mindbricks Labs](https://mindbricks.com)**.

Mindbricks Labs is the only sponsor today. Organisations that want to support the
standard can write to openappl@mindbricks.com. Sponsorship does not give decision rights
over the specification.

## Taking part

- **Read and implement.** The specification is complete enough to write a compiler; Part
  3 states what a conforming compiler must do.
- **Build a compiler or a tool.** See [Compilers](compilers.md) for how compilers relate to
  the standard and how conformance is shown.
- **Give feedback.** Every page of this site has a feedback box at its end; it reaches the
  stewards and shapes the next release.

## Contact

- **Website:** [openappl.org](https://openappl.org)
- **Proposals, questions and implementer discussions:** the issues and discussions of the
  OpenAPPL repository on GitHub, following the [RFC process](../rfcs/README.md).
- **Sponsorship, private matters and code-of-conduct reports:** openappl@mindbricks.com.

## News and events

Announcements, releases and events are listed on the homepage of this site.
