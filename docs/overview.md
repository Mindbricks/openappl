# OpenAPPL

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

**Describe the business. Compile the system.**

OpenAPPL, the Open Application Pattern Language, is an open, typed language for
describing complete application backends at the level of business decisions: data,
access rules, APIs, workflows and integrations. A description written in OpenAPPL is
called a **blueprint**. A blueprint names no programming language, no framework and no
database. A **compiler** turns it into a running system.

People and AI agents write the blueprint. Reviewers read the blueprint. Compilers do the
rest.

## Why it exists

AI can already write code from a prompt. What it cannot give you on its own is a
contract: one small, precise document that says what the system does, that a person can
review, that a machine can check, and that stays stable when you regenerate. OpenAPPL is
that contract. Read more in [Why OpenAPPL](why-openappl.md).

## Three parts, one standard

OpenAPPL is published as three documents that together let anyone author, check and
compile blueprints.

| Part | What it gives you |
|---|---|
| **1. The ontology** | The map of the language: every pattern, where it sits in the blueprint tree, what it contains and what it refers to. Start here to learn the vocabulary. |
| **2. The language specification** | The normative reference for authors and validators: every property, its type, defaults, allowed values, constraints and examples. A blueprint is valid when it satisfies this part. |
| **3. The compiler specification** | What a conforming compiler must produce for each pattern: the behaviour, the interface and the rules for documented deviations. Read this to build your own compiler. |

The whole schema is also published as one machine-readable file, `openappl.json`, so
tools and agents can load the language directly.

## What you get

- **A reviewable contract.** A change in requirements becomes a short, semantic blueprint
  diff instead of thousands of regenerated lines.
- **Errors before code.** An unknown field, a missing reference or a wrong type is reported
  by the validator, with its path, before anything is compiled.
- **Freedom of target.** The same blueprint can be compiled to different languages,
  databases, message brokers and deployment shapes.
- **Governance by lookup.** Questions such as "which APIs can delete data without a
  permission check?" are answered by querying the blueprint, not by auditing code.
- **No lock-in.** The language is open and versioned. Any number of compilers, editors and
  tools can implement it.

## Start here

- [Read the ontology](https://openappl.org/ontology) - learn the vocabulary of the language.
- [Read the specification](https://openappl.org/spec) - the exact rules a valid blueprint follows.
- [Write a compiler](https://openappl.org/compiler) - build a conforming back end of your own.
- [Download openappl.json](../openappl.json) - the complete schema in one file.

New to OpenAPPL? See [How it works](how-it-works.md) and [Get started](get-started.md).
