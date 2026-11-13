# Get started

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

There are two ways into OpenAPPL: writing blueprints, and writing compilers. Pick the
path that fits you. Both start from the same three documents and the same schema file,
`openappl.json`.

## For authors

You describe a system; a compiler builds it. You can write blueprints by hand, have an AI
agent write them with you, or both.

1. **Learn the shape.** Read [How it works](how-it-works.md) for the blueprint tree:
   project, services, data objects, business APIs and their settings.
2. **Learn the vocabulary.** Browse [the ontology](https://openappl.org/ontology). Each pattern
   page shows where the pattern sits in the tree, what it contains and what it refers to.
3. **Look up the rules.** When you write a pattern, open its page in
   [the language specification](https://openappl.org/spec) for every property, its type, its
   default and its constraints, plus examples.
4. **Validate early and often.** Check every change against the schema before you
   compile. Errors come back with the exact path of the problem, so fixing them is quick.
5. **Compile.** Pick a [compiler](compilers.md), choose the language and database of each
   service in the compile request, and build. When requirements change, change the
   blueprint and compile again; never edit the generated code.

### Working with an AI agent

General-purpose coding agents can author blueprints directly; no special editor is
needed. What helps them most:

- Give the agent access to `openappl.json`, or to the per-pattern pages, so it can look up
  the exact patterns it is about to write instead of guessing.
- Ask it to follow a simple loop: look up the patterns, draft a change, validate it,
  repair what the validator reports, and only then save the blueprint.
- Review the blueprint diff, not the generated code. That is where the decisions are.

### Good habits

- Start from the data: objects, properties and relations first, APIs second.
- Declare every API you need. Nothing is generated that the blueprint does not declare.
- Prefer a pattern to an extension point. Reach for expressions, library functions or
  edge endpoints only where no pattern fits, and keep them small.
- Keep the blueprint in version control. It is the source of truth of your system.

## For compiler writers

You want to turn blueprints into running systems with a technology stack of your choice.

1. **Understand the contract.** Read the conformance model on the
   [Compilers](compilers.md) page: same behaviour, same interface, documented deviations
   with adapters, and free choice of everything below the interface.
2. **Load the language.** Download [openappl.json](../openappl.json). It holds every
   pattern with its properties, types, defaults, validation rules and documentation, so
   you can generate your parser and validator from it rather than writing them by hand.
3. **Read the compiler specification.** [Part 3](https://openappl.org/compiler) states, pattern by
   pattern, what a conforming compiler must produce: the API lifecycle for each kind of
   API, the data layer, the authorisation model, the event contract and the system
   services.
4. **Choose your profile.** Decide which pattern families you support at first, declare
   it, and refuse blueprints outside it at compile time. A smaller honest profile is
   better than a large one that silently drops features.
5. **Make your technology choices.** Topology, language, database engine, message broker,
   cache, search and storage are yours to pick. Where a choice forces a visible
   difference, document the deviation and ship an adapter.
6. **Test against the reference.** Run the reference blueprints and the black-box test
   suite of the conformance kit against your output, and compare with the reference
   implementation. The conformance kit is being prepared and will be published on this
   site.
7. **Get listed.** Send your profile, deviation register and conformance results to be
   added to the [Compilers](compilers.md) page.

A tip from experience: in a compiler with several targets, the test suite is the
semantics. Keep your behaviour pinned by tests that run the same blueprints against every
target you support.

## Where to go next

- [Why OpenAPPL](why-openappl.md) - the problems the language is built to solve.
- [Vision and mission](vision-and-mission.md) - where the standard is heading.
- [Policy](policy.md) - governance, versioning and licences.
