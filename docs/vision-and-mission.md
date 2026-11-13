# Vision and mission

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

## Vision

Software should be designed in the language of the business and built by machines, with
the design, not the code, as the thing people review, version and trust.

We think the next generation of application development will not be "AI writes all the
code" or "low-code tools hide the code". It will be a layer in between: a precise,
shared description of what a system does, which humans and AI agents author together and
which any number of compilers turn into running software. OpenAPPL is our proposal for
that layer.

In that future:

- a product decision is one readable line in a blueprint, not a hunt through handler code;
- changing a system is a normal, everyday act, because the whole codebase is derived again
  from one consistent design instead of patched by hand;
- security, tenancy and data-protection questions are answered by looking at the design;
- the choice of language, database and deployment shape is made late, and can be made
  again, without redesigning anything;
- no single vendor owns the knowledge of how a backend is described.

## Mission

Our mission is to make OpenAPPL a dependable, open standard for describing application
backends, and to make it easy for others to build on it.

Concretely, we commit to:

1. **Publish the language openly.** The ontology, the language specification, the compiler
   specification and the machine-readable schema `openappl.json` are public and versioned.
2. **Keep it business-level.** Every pattern describes what the system does. How it is
   realised stays with the compiler.
3. **Keep it closed and typed.** A blueprint uses only the declared vocabulary, so every
   mistake can be found by a validator before any code exists.
4. **Specify compilers, not just blueprints.** The compiler specification states what a
   conforming compiler must produce, so a third party can build one without reading
   anyone else's source code.
5. **Grow by evidence.** New patterns are added when a recurring need is proven in real
   systems, and every change is released as a new version of the language.
6. **Welcome other compilers and tools.** Editors, validators, governance tools,
   deployment platforms and further compilers are all first-class consumers of the
   standard. See [Compilers](compilers.md).

## Where we are today

OpenAPPL grew out of industrial use. Its catalogue already holds several hundred typed
patterns covering data modelling, access control, querying, storage, integrations and
behaviour, and it is close to covering most recurring business logic. The
[first compiler](compilers.md) already compiles one blueprint to six programming
languages. The work
ahead is to publish the standard in a form that others can implement, test and extend.
