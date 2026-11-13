# OpenAPPL RFC process

> Review periods and roles follow the
> [Stewardship and Governance Statement](../GOVERNANCE.md); both take effect together.

A **Request for Comments (RFC)** is how a substantive change to OpenAPPL is proposed,
discussed and decided. Editorial changes (typos, clarifications that do not change
meaning, broken links) do not need an RFC: open a pull request directly.

## When an RFC is needed

- a new pattern, property, enum value or MScript slot;
- a change in the meaning, type, default or validation of an existing element;
- a deprecation or removal;
- any change to what a conforming compiler must produce (Part 3 of the specification);
- a change to the governance statement or the RFC process itself.

If you are not sure, open an issue first and ask.

## The life of an RFC

```
idea ──► draft ──► review ──► final comment ──► decision ──► implementation ──► released
                                               │
                                               ├─► accepted
                                               ├─► rejected   (may be resubmitted after 6 months)
                                               └─► postponed
```

| Stage | What happens | Minimum length |
|---|---|---|
| **Idea** (optional) | An issue describing the need. Useful to find out early whether an RFC is welcome. | none |
| **Draft** | Copy [`0000-template.md`](0000-template.md) to `rfcs/0000-short-name.md`, fill it in and open a pull request. The Editors assign a number and rename the file. | none |
| **Review** | Public discussion on the pull request. The author updates the RFC. The Editors check that the proposal is complete: schema change, Part 2 text, Part 3 behaviour, migration. | 14 days |
| **Final comment** | The Editors announce a recommendation (accept, reject or postpone). Last chance for objections. RFCs that affect the compiler specification or break compatibility also get the Advisory Group's opinion here. | 10 days (30 days for breaking changes and governance changes) |
| **Decision** | The steward decides and records the decision and its reasons in the RFC. Accepted RFCs are merged with status `accepted`. | none |
| **Implementation** | The schema, Part 1, Part 2 and Part 3 are updated, and the conformance suite gets tests for the change. The RFC links to the changes. | none |
| **Released** | The change ships in a release of `openappl.json`. The RFC records the version. | none |

## What makes an RFC acceptable

1. **A real need, with evidence.** Show the recurring problem in real systems, usually as
   repeated use of the extension points (expressions, library functions, edge endpoints)
   that the proposed pattern would replace.
2. **Business-level.** The change describes what a system does, not how one technology
   does it.
3. **Complete for compilers.** The RFC states what a conforming compiler must produce, in
   behaviour (C1) and interface (C2) terms.
4. **Compatible, or honestly versioned.** The RFC states the version step (patch, minor,
   major) and the migration for existing blueprints.
5. **Implementable by more than one vendor.** Nothing in the proposal depends on one
   product.

## Numbering and status

RFCs are numbered in order of acceptance into review (`0001`, `0002`, ...). The header of
each RFC carries its status: `draft`, `review`, `final-comment`, `accepted`, `rejected`,
`postponed`, `implemented`, `released (<version>)`, or `withdrawn`.

## Index

| RFC | Title | Status | Version |
|---|---|---|---|
| | *(none yet)* | | |
