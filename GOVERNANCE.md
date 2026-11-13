# OpenAPPL Stewardship and Governance Statement

> **Status.** The owner of the standard took the open decisions on 2026-11-13. The
> statement takes effect together with the licences and the patent commitment, once
> counsel has reviewed those texts; this notice is then removed.

Version: 1.0 (pre-publication) · Applies to: the OpenAPPL ontology, language specification, compiler
specification, the schema `openappl.json` and the example blueprints in this repository
(together, "the Specification").

## 1. Purpose

OpenAPPL is an open, vendor-neutral language for describing application backends at the
level of business decisions. This statement says who looks after the Specification, how
changes are decided, and what everyone who uses or implements it can rely on.

## 2. Principles

1. **Open.** The Specification is public. Anyone may read it, implement it, build tools on
   it and write compilers for it, without asking permission and without paying a fee.
2. **Vendor-neutral.** The Specification describes what a system does, never which product
   builds it. No requirement of the Specification may be satisfiable by only one vendor.
3. **Business-level.** A pattern describes a business decision. Technology choices
   (languages, frameworks, databases, topology) belong to compilers, not to the language.
4. **Evidence first.** A change is accepted because a recurring need was seen in real
   systems, not because it is possible.
5. **Specified for compilers.** A change to the language is complete only when the
   compiler specification says what a conforming compiler must do with it.
6. **Stable for users.** Valid blueprints stay valid within a major version. Breaking
   changes are rare, announced, versioned and accompanied by a migration path.

## 3. Roles

### 3.1 Steward

**Mindbricks Labs** ([mindbricks.com](https://mindbricks.com)) is the steward of OpenAPPL.
The steward:

- maintains the Specification and this repository, and runs the OpenAPPL website;
- appoints the Editors and the members of the Advisory Group;
- runs the change process in section 4 and makes the final decision on every change;
- publishes releases of the schema and of the specification documents;
- maintains the reference implementation of the Specification.

The steward acts for the benefit of the Specification and its users, not for the
advantage of any single implementation, including its own.

### 3.2 Editors

Editors are the people who write and maintain the specification text. They review change
proposals, keep the three parts of the Specification consistent with each other and with
the schema, and prepare releases. Editors are appointed by the steward and may come from
any organisation, including other implementers of the Specification.

### 3.3 Advisory Group

An Advisory Group of implementers and users reviews proposals that affect the compiler
specification or break compatibility. Its role is advisory: it gives a recorded opinion on
such proposals before the steward decides. It is formed as soon as a second, independent
conforming compiler exists, with a representative of every conforming compiler and up to
five users of the language, appointed by the steward for a renewable term of one year.
Until then, the steward consults known implementers directly on such proposals.

### 3.4 Contributors

Anyone may contribute: by reporting a problem, proposing a change through the RFC process
([rfcs/README.md](rfcs/README.md)), reviewing proposals, or improving the documents.
Contributions are accepted under the terms in [LICENSE.md](LICENSE.md) and
[CONTRIBUTING.md](CONTRIBUTING.md). Every contribution has a person who wrote it and
stands behind it: AI assistance is allowed when it is disclosed, and contributions opened
by an agent on its own are not accepted (CONTRIBUTING.md, "AI and automated
contributions").

### 3.5 Implementers

Anyone may implement the Specification, with a compiler of any kind: template, agent or
hybrid. A compiler that conforms to the compiler specification may say so, under the
rules for conformance claims in section 7.

## 4. How changes are decided

1. **Editorial changes** (typos, clarifications that do not change meaning, broken links)
   are made directly by the Editors and released as patch versions.
2. **Substantive changes** (a new pattern or property, a change in meaning, anything that
   affects compilers) go through the RFC process: a written proposal, a public review
   period, a final comment period and a recorded decision.
3. **Decisions** are made by the steward on the recommendation of the Editors, after the
   review periods have ended and, for changes that affect the compiler specification or
   break compatibility, after the Advisory Group has given its opinion. The reasons for
   every decision are published with the RFC.
4. **Reconsideration.** The author of a rejected RFC may ask once for reconsideration, with
   new evidence. A rejected RFC may be resubmitted after six months.

## 5. Releases and versioning

- The version of the schema `openappl.json` is the version of the language. It follows
  semantic versioning: patch for documentation, minor for compatible additions, major for
  changes that can make a valid blueprint invalid or change its meaning.
- Every release is published unchanged as `versions/openappl-<version>.json` and remains
  available permanently.
- A deprecated element stays in the schema, marked with a pointer to its replacement, for
  at least one minor release before a major release may remove it.
- An experimental element (a pattern, or a single property of a stable pattern, marked
  `experimental` in the schema with the version that added it) may arrive in a minor
  release. It is an unstable pre-release: it may change or disappear in any release before
  the next major release, and that major release either promotes it (the marker is
  removed) or drops it. Experimental elements are used only by blueprints that opt in and
  are outside conformance.
- Release cadence: patch releases at any time; minor releases at most once a month; major
  releases at most once a year, announced at least six months in advance.

## 6. Commitments of the steward

The steward commits to the following, for as long as it stewards the Specification:

1. The Specification remains available to everyone, free of charge, under the licences in
   [LICENSE.md](LICENSE.md). A published version is never withdrawn or relicensed under
   more restrictive terms.
2. The patent commitment in [PATENTS.md](PATENTS.md) applies to every published version
   and cannot be revoked for that version.
3. No feature of the Specification requires the steward's products or services.
4. The reference implementation does not receive non-public changes to the Specification
   in advance of other implementers; proposals and decisions are public.
5. **Continuity.** If the steward stops maintaining the Specification, it will either
   transfer stewardship to a neutral organisation (for example, an open-source or
   standards foundation) or announce the end of its stewardship with at least six months'
   notice. In every case the published versions remain usable under their licences and
   the patent commitment. A successor organisation will be chosen when it is needed; the
   steward commits that it will be a neutral, non-profit open-source or standards body.

## 7. Names and conformance claims

"OpenAPPL" is a name used by the steward to identify the Specification; the steward is
registering it as a word mark to protect these rules:

- Anyone may say that a product "implements OpenAPPL" or "supports OpenAPPL <version>".
- "OpenAPPL conformant" may be used only by a compiler that passes the published
  conformance suite for the stated version and profile, once the suite is available. The
  suite alone decides: the claim is open to every kind of compiler, whether it uses
  templates, an AI model (an agent compiler) or both, and whether or not its output is
  deterministic. The blueprint is the contract the suite tests against.
- "Deterministic" is an additional claim. A compiler that is OpenAPPL conformant may add
  it when it meets the deterministic rules of the compiler specification (the same
  blueprint gives the same output, and a small blueprint change gives a localised output
  change) and publishes the results of the corresponding checks
  (compiler specification, section 1.7). The claim is never made without
  "OpenAPPL conformant".
- No one may imply that the steward endorses a product without the steward's written
  agreement.

## 8. Conduct

Everyone taking part in OpenAPPL discussions is expected to be respectful and
constructive. OpenAPPL adopts the Contributor Covenant, version 2.1, as its code of
conduct ([CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)). Reports go to
openappl@mindbricks.com and are handled confidentially by the steward.

## 9. Changes to this statement

This statement is changed through the same RFC process as the Specification, with a
review period of at least 30 days. The steward approves the change.

## 10. Contact

- **Proposals, questions and implementer discussions:** the issues and discussions of the
  OpenAPPL repository on GitHub.
- **Sponsorship, private matters and code-of-conduct reports:** openappl@mindbricks.com.
- **Website:** [openappl.org](https://openappl.org).
