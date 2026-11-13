# Policy

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

This page describes how OpenAPPL is governed, how it is versioned and under which terms
it is published.

> **Status.** The owner of the standard took the governance decisions on 2026-11-13. The
> licences and the patent commitment take effect once counsel has reviewed their texts.

## Principles

- **Open.** The ontology, the language specification, the compiler specification and the
  schema file `openappl.json` are public. Anyone may read them, implement them and build
  tools on them.
- **Business-level.** A pattern describes what a system does. A proposal that adds
  open-ended technical description to the blueprint (frameworks, wire formats, topology)
  does not belong in the language; it belongs in a compiler.
- **Closed and typed.** Every addition is a declared pattern or property with a type,
  documentation and, where it applies, a default and validation rules. Nothing is added
  as a free-form field.
- **Evidence first.** A new pattern is added when a recurring need has been seen in real
  systems, usually as a repeated use of the extension points (expressions, library
  functions, edge endpoints) that a pattern can replace.
- **Specified for compilers.** A change to the language is not complete until the compiler
  specification says what a conforming compiler must do with it.

## Stewardship

OpenAPPL and this website are stewarded by [Mindbricks Labs](https://mindbricks.com),
where the language originated. The steward maintains the standard, publishes its
releases and runs this site. The language itself stays open and vendor-neutral: any
company or person may implement it, build tools on it or write a compiler for it.

## Governance

The full text is the [Stewardship and governance statement](../GOVERNANCE.md). In
short:

- Mindbricks Labs, as the steward, decides on every change to the ontology, the language
  specification and the compiler specification, on the recommendation of the Editors.
- Anyone may propose a change through the [RFC process](../rfcs/README.md),
  starting from the [RFC template](../rfcs/0000-template.md). Every proposal has a
  public review period and a final comment period, and every decision is published with
  its reasons.
- Editors may come from any organisation; the steward appoints them.
- An Advisory Group of implementers and users gives a recorded opinion on changes that
  affect the compiler specification or break compatibility. It is formed as soon as a
  second, independent conforming compiler exists; until then the steward consults known
  implementers directly.
- The steward commits to keeping published versions open, to vendor neutrality, and to
  continuity if it ever stops stewarding the standard.

## Versioning

**The schema version is the language version.** The schema file `openappl.json` carries a
semantic version number (`major.minor.patch`), and that number is the version of
OpenAPPL. There is no separate language version to keep in step.

- Every release of the schema is published twice: as `openappl-<version>.json`, which
  never changes, and as `openappl.json`, which always points at the latest release.
- A blueprint records the schema version it was written against, so tools always know
  which rules apply to it.
- Patch releases can come at any time; minor releases at most once a month; major
  releases at most once a year, announced at least six months in advance.

What each part of the number means:

| Change | Example | Version step |
|---|---|---|
| Fix or clarify documentation, no change in meaning | a better property description | patch |
| Add to the language without breaking valid blueprints | a new pattern, a new optional property, a new enum value | minor |
| Change that can make a valid blueprint invalid or change its meaning | removing or renaming a property, changing a type | major |

A property or pattern that is being retired is first marked **deprecated** in the schema,
with a pointer to its replacement where there is one, so that tools can migrate
blueprints automatically. It is removed only in a later major version.

A pattern, or a single property of a stable pattern, can also arrive marked
**experimental**: an unstable pre-release, added in a minor release when an important need
comes up. Its marker records the version that added it and what may still change. It is
used only by blueprints that opt in, and it may change or disappear before the next major
release, which promotes it (the marker is removed) or drops it. Experimental elements are
outside conformance: a compiler that does not support one refuses a blueprint that uses it
and stays conformant (compiler specification, section 1.5).

Compilers state which OpenAPPL versions they support. A compiler that supports a version
must accept every blueprint that is valid for that version, or refuse it at compile time
as outside its declared profile (see [Compilers](compilers.md)).

## Licences

The terms are on the [Licences](../LICENSE.md) page and in the
[Patent commitment](../PATENTS.md):

| What | Licence |
|---|---|
| Specification text: the ontology pages, the language specification and the compiler specification | Creative Commons Attribution 4.0 (CC-BY-4.0) |
| The schema `openappl.json` and the published example blueprints | Apache License 2.0 (Apache-2.0) |

The steward promises not to assert its patents against implementations that conform to
the specification, and contributors make the same promise for what they contribute
([Patent commitment](../PATENTS.md)). Every contribution carries a Developer
Certificate of Origin sign-off.

Your own blueprints are yours. The licence of the standard does not extend to the
blueprints you write with it, nor to the code a compiler generates from them; the terms
of the generated code are set by the compiler you use.

## Trademarks and naming

Anyone may say that a product "implements OpenAPPL" or "supports OpenAPPL <version>".
"OpenAPPL conformant" is reserved for compilers that pass the published conformance
suite. The steward is registering "OpenAPPL" as a word mark to protect these rules; the
full rules are in section 7 of the
[Stewardship and governance statement](../GOVERNANCE.md#7-names-and-conformance-claims).
