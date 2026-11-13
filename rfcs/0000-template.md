# RFC 0000: Title of the proposal

| | |
|---|---|
| **Status** | draft |
| **Author(s)** | name, organisation, contact |
| **Created** | YYYY-MM-DD |
| **Version step** | patch / minor / major |
| **Affects** | Part 1 ontology / Part 2 language specification / Part 3 compiler specification / schema / governance |
| **Discussion** | link to the pull request |
| **Decision** | (filled in by the Editors) |

## Summary

One paragraph: what changes, for whom, and why.

## Motivation and evidence

- What problem do blueprint authors have today?
- Where was it seen? Describe real systems (anonymised if needed): how many, and how they
  work around it now (expressions, library functions, edge endpoints, external services).
- What happens if nothing changes?

## Proposal for blueprint authors

Explain the change as an author would learn it: the new or changed patterns and
properties, with a short blueprint example.

```json
{
  "example": "a minimal blueprint fragment using the proposal"
}
```

## Schema change

The exact change to `openappl.json`, for every pattern touched:

| Pattern | Property | Type | Default | Change | Documentation line |
|---|---|---|---|---|---|
| `ExamplePattern` | `exampleProperty` | `Boolean` | `false` | added | "One sentence, as it will appear in the schema." |

Validation rules: new errors and warnings, with their conditions and messages.

## Compiler specification (Part 3)

What a conforming compiler must produce. Keep the two kinds of conformance apart:

- **Behaviour (C1):** what the generated system does: storage, lifecycle, authorization,
  events, errors.
- **Interface (C2):** what clients see: routes, request and response shapes, event
  payloads, names of generated elements.
- **Derived surface:** does the proposal lower to other patterns, add routes, storage or
  library functions? (Part 3, chapter 12.)
- What is a compiler free to choose?

## Compatibility and migration

- Does any valid blueprint become invalid, or change meaning? If yes, this is a major
  version step.
- How are existing blueprints migrated? Can a tool do it automatically?
- What is deprecated, and what replaces it?

## Conformance tests

The tests the conformance suite needs for this change: reference blueprints and the
expected observable results.

## Alternatives

Other designs considered, including doing nothing and solving it in a compiler or a
library instead, and why this proposal is better.

## Prior art

Similar features in other languages, frameworks or standards.

## Unresolved questions

What should be settled during review, and what is deliberately left for later.

## Decision record

(Filled in by the Editors.)

| Date | Stage | Outcome and reasons |
|---|---|---|
| | | |
