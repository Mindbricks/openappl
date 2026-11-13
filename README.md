# OpenAPPL: Open Application Pattern Language

**Describe the business. Compile the system.**

OpenAPPL is an open, typed language for describing complete application backends at the
level of business decisions: data, access rules, APIs, workflows and integrations. A
description written in OpenAPPL is called a **blueprint**. A blueprint names no
programming language, framework or database. A **compiler** turns it into running
services.

This repository holds the published schema of the language, its basic documents and
example blueprints. The full specification lives on the OpenAPPL website,
[openappl.org](https://openappl.org/).

## Contents

```
openappl.json                 the schema of the latest release
versions/openappl-<v>.json    every release, unchanged once published
docs/                         the basic documents (overview, vision, policy, about, ...)
examples/                     example blueprints, each valid against the schema
rfcs/                         the change process and the RFC template
GOVERNANCE.md                 stewardship and governance statement
LICENSE.md, PATENTS.md        licences and the patent commitment
CONTRIBUTING.md               how to contribute (DCO sign-off)
CODE_OF_CONDUCT.md            Contributor Covenant 2.1
```

## The schema: `openappl.json`

`openappl.json` defines every pattern of the language: its properties, their types,
defaults, allowed values and documentation. Tools read it to validate, complete and
explain blueprints; compilers read it to know what they must accept.

- **The schema version is the language version.** The version is the `__patternsVersion`
  field of the file (`1.103.0` today) and follows semantic versioning: a patch fixes
  documentation, a minor release adds to the language without breaking valid blueprints,
  a major release may change or remove something.
- `openappl.json` always holds the latest release. Every release is also kept, unchanged,
  as `versions/openappl-<version>.json`; pin that file when you need stable rules.
- A blueprint records the schema version it was written against.
- The root pattern of a blueprint is `Project`. The earlier name `MindbricksProject` is
  still accepted as an alias.

See [docs/policy.md](docs/policy.md) for the versioning rules and deprecation policy.

## A blueprint in brief

A blueprint is one JSON document. Its root is a `Project`; a project has services, a
service has data objects and business APIs. The excerpt below is from
[`examples/todo.json`](examples/todo.json):

```json
{
  "codename": "todolist",
  "services": [
    {
      "serviceSettings": { "serviceBasics": { "name": "tasks" } },
      "dataObjects": [
        {
          "objectSettings": { "basicSettings": { "name": "task" } },
          "properties": [
            { "basicSettings": { "name": "title", "type": "String", "isRequired": true } },
            { "basicSettings": { "name": "done", "type": "Boolean", "defaultValue": false } }
          ]
        }
      ],
      "businessLogic": [
        {
          "basics": {
            "apiOptions": { "name": "listTasks", "crudType": "list", "dataObjectName": "task" },
            "authOptions": { "loginRequired": true, "ownershipCheck": true }
          }
        }
      ]
    }
  ]
}
```

Everything not written takes its documented default. The compiler derives the rest:
storage, routes, authorization checks, events, the search projection and the
authentication service.

## Examples

| Example | What it shows |
|---|---|
| [`todo.json`](examples/todo.json) | One service, one data object owned by its creator, the four basic API types with ownership checks. |
| [`blog.json`](examples/blog.json) | Two related objects, an enum with a default, public read APIs filtered by a where clause, an owner-only publish step. |
| [`shop.json`](examples/shop.json) | A high-level pattern: the order object is marked as a checkout order, and the compiler adds the payment records, payment APIs and payment routes. |

[examples/README.md](examples/README.md) explains each one. Every example validates with
no errors against the reference compiler for the schema version in this repository.

## Documents

| Document | |
|---|---|
| [Overview](docs/overview.md) | What OpenAPPL is and the problems it solves. |
| [Vision and mission](docs/vision-and-mission.md) | Where the language is going and why. |
| [Why OpenAPPL](docs/why-openappl.md) | The case for describing systems at the business level. |
| [How it works](docs/how-it-works.md) | From blueprint to running system. |
| [Compilers](docs/compilers.md) | Compilers of the language, starting with Genesis. |
| [Get started](docs/get-started.md) | Writing a first blueprint. |
| [Policy](docs/policy.md) | Principles, governance, versioning and licences. |
| [About](docs/about.md) | Who stewards, supervises and sponsors the standard. |

The three parts of the specification are on the website:
[Part 1, ontology](https://openappl.org/ontology),
[Part 2, language specification](https://openappl.org/spec) and
[Part 3, compiler specification](https://openappl.org/compiler).

## Compilers

A compiler turns a blueprint into a running system. The standard is written so that
there can be many: template compilers, AI code generators and hybrids. They are free in
technology (languages, databases, topology) and bound to the same observable behaviour
and interfaces, which Part 3 specifies.

**Genesis**, built by [Mindbricks Labs](https://mindbricks.com), is the first OpenAPPL
compiler and today the reference implementation. See [docs/compilers.md](docs/compilers.md).

## Stewardship and governance

OpenAPPL is stewarded by [Mindbricks Labs](https://mindbricks.com), where the language
originated. The steward maintains the specification, approves changes and publishes
the releases in this repository. The language is vendor-neutral: anyone may implement
it, build tools on it or write a compiler for it.

- [GOVERNANCE.md](GOVERNANCE.md): roles, how changes are decided, the steward's
  commitments (openness, neutrality, continuity) and conformance claims.
- [rfcs/](rfcs/README.md): how to propose a change, with the RFC template.
- [CONTRIBUTING.md](CONTRIBUTING.md): issues, fixes, examples and RFCs.

## Licence and patents

- The specification text is licensed under **CC-BY-4.0**; the schema, its versions and
  the example blueprints under **Apache-2.0**. See [LICENSE.md](LICENSE.md).
- Mindbricks Labs promises not to assert its patents against conforming implementations.
  See [PATENTS.md](PATENTS.md).
- Blueprints you write are yours; the licences of the standard do not extend to them or
  to the code a compiler generates from them.

> The owner of the standard took the governance decisions on 2026-11-13. The licence and
> patent texts take effect once counsel has reviewed them.

Contact: questions and proposals in this repository's issues and discussions;
sponsorship, private matters and conduct reports at openappl@mindbricks.com.

---

OpenAPPL is developed and maintained by [Mindbricks Labs](https://mindbricks.com).
