# Compilers

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

A compiler is what turns an OpenAPPL blueprint into a running system. The standard is
written so that there can be many of them: deterministic template compilers, AI code
generators that read the blueprint as a complete model of the system, and hybrids of the
two. They compete on technology, speed and quality. The blueprint stays the same.

## Genesis

**Genesis, the first OpenAPPL compiler, built by [Mindbricks Labs](https://mindbricks.com).**

Genesis is a deterministic template compiler and today the reference implementation of
the standard. It compiles one blueprint into production services in six programming
languages:

| Target | Generated stack |
|---|---|
| Node.js | TypeScript, Express |
| Python | FastAPI |
| Java | Spring Boot |
| C# / .NET | ASP.NET Core |
| Go | standard library `net/http` |
| Rust | Axum and Tokio |

The language and the database of each service are chosen in the compile request.
Generation is deterministic per target: the same blueprint gives the same source tree on
every run. Genesis also ships an optional converter that translates expressions written
in JavaScript into the other target languages; the converter is a Genesis feature, not a
requirement of the standard.

The test obligations of the compiler specification are currently defined against Genesis.
Its behaviour is the reference that other compilers are compared with.

## What conformance means

A compiler conforms to OpenAPPL when a user cannot tell, from the outside, which
conforming compiler built their system. The compiler specification states this in detail;
in short:

**Same behaviour.** For a given blueprint, the generated system behaves the same way:
the same validation outcomes, authorisation decisions, state transitions, events, error
classes and HTTP statuses.

**Same interface.** A frontend written against one compiler's output runs against
another's: the same routes, request and response envelopes, authentication and session
protocol, pagination, error body, realtime frames and event payload shapes.

**Documented deviations, with adapters.** Sometimes a technology forces a difference, for
example an ID format or a platform-specific header. A compiler may deviate, but it must
document the deviation in the registered form and ship an adapter that still accepts the
reference interface.

**Free technology choice.** Everything below the interface is yours to decide:

- deployment topology: microservices, a modular monolith or a function per API;
- programming language and frameworks;
- database engine: relational, document, a managed store, or a subset of these;
- message broker: the event bus in the ontology is a logical bus, so Kafka, NATS,
  RabbitMQ, SNS and SQS, or Pub/Sub all conform;
- cache, search engine and object storage.

**Profiles.** A compiler does not have to support every pattern family. It may declare a
profile, for example "single database" or "no search engine". It must then refuse, at
compile time, a blueprint that falls outside its profile. It must never emit code that
silently drops a feature.

## Getting a compiler listed

We want this page to list every conforming compiler. To be listed, a compiler needs:

1. **A public description**: name, maintainer, licence, and the OpenAPPL version or
   versions it supports.
2. **A declared profile**: the pattern families it supports and the ones it refuses.
3. **Its deviation register**: every documented deviation and the adapter that covers it.
4. **Conformance evidence**: results of running the published reference blueprints and
   black-box test suite against the compiler's output. The conformance kit is being
   prepared; until it is published, listings are reviewed case by case.

The listing process and where to submit a compiler will be announced together with the
governance details on the [Policy](policy.md) page.

## Listed compilers

| Compiler | Maintainer | Kind | Targets | OpenAPPL version |
|---|---|---|---|---|
| Genesis | Mindbricks Labs | Deterministic templates | Node.js, Python, Java, .NET, Go, Rust | 1.x |

Building one? Start with [Get started for compiler writers](get-started.md#for-compiler-writers).
