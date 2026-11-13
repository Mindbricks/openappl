# Why OpenAPPL

> This page is mirrored from the [OpenAPPL website](https://openappl.org/), where the full ontology and specifications live.

Ask an AI system for "a meeting backend with organisations, members, agendas and action
items, where only organisation admins can close an action item" and you can get tens of
thousands of lines of working code in minutes. That is impressive. It is also where the
trouble starts, because the system now has no specification other than its own code.

The requirements live in prose. The implementation lives in code. Nothing in between is
at the same time precise enough to compile, small enough to review and stable enough to
diff, version and govern. OpenAPPL puts that missing artifact back. Below are the five
problems it targets.

## 1. Direct generation gives you no reviewable contract

When code is generated straight from a prompt, the unit of review is the generated line.
The one sentence "only admins can close an action item" turns into an access check
somewhere inside handler code, and someone has to find it and confirm it is right. Review
effort grows with the size of the output, not with the number of decisions made.

It gets worse when requirements change. "Members may also close items they created" is
one new decision, but regenerating from prose produces a new codebase whose diff is full
of renamed identifiers, reordered files and reformatted code. Teams end up either
re-prompting until it looks right or hand-patching code that the next generation will
overwrite.

**With OpenAPPL** the decision lives in the blueprint. The first rule is a role on one
API; the change is one conditioned permission check. Both are a few lines, reviewable in
seconds, and the compiler derives everything else. Because a deterministic compiler gives
the same output for the same blueprint, a small change to the blueprint produces a
correspondingly small change in the code.

## 2. Backend knowledge is locked into one vendor

Every code generator, framework and low-code platform carries its own idea of what a
backend is made of: objects, permissions, APIs, events. That knowledge usually lives in
private templates or a proprietary runtime. Moving away means describing your system all
over again.

**With OpenAPPL** the description of the system is an open, versioned standard. The
blueprint is a plain JSON document that conforms to a published schema, `openappl.json`.
Any tool can read it, any compiler can implement it, and the knowledge of how your
backend is described belongs to you, not to the tool that happened to produce it.

## 3. AI authors better in a closed, typed vocabulary

When a model writes free code, nothing stops it from inventing a field, an endpoint or a
framework call. The invention is discovered late: by a failing test, or by a user.

An OpenAPPL blueprint can only use the properties the patterns declare. The validator
rejects anything else, with a typed message and the exact path of the mistake, before a
single line of code exists. Hallucination is not prevented, but it is turned from a
runtime defect into an instant validation error that the agent can repair on its own.

The language is also built to be read by agents. Every pattern carries its documentation
inside the schema, so an agent can fetch exactly the patterns it is about to write, draft
a change, check it, and only then commit it. The output is measured in decisions, not in
lines of code, which keeps authoring cheap and keeps review focused on what the agent
actually decided.

The honest trade-off: models do not yet know OpenAPPL from their training data the way
they know mainstream programming languages, so an agent has to look up the vocabulary as
it works. That lookup is targeted and cheap, and it shrinks as the open standard and its
public examples become part of what models learn from.

## 4. Governance needs answers, not audits

"Which services touch personal data?" "Which endpoints have no permission check?" "Which
APIs can send email?" Over arbitrary code, questions like these need program analysis,
and in general they cannot be decided with certainty at all. Over generated code it is
no different.

OpenAPPL is designed so that these questions become simple queries over the blueprint
tree. Two rules make that possible:

- **Everything is explicit.** No endpoint exists unless the blueprint declares it, so the
  blueprint lists the whole behaviour and attack surface of the system.
- **Workflows are flat.** There is no generic "if" action. Each step carries an optional
  condition instead, so the set of things an API can do is visible in the blueprint, and
  conditions only decide when a step runs, never which steps exist.

The result is that "what can this system do?" is answered by lookup, in time proportional
to the size of the blueprint. Credential fields are marked in the schema, authentication
settings are visible on every API, and every change to them shows up in a blueprint diff.

## 5. One blueprint, many targets

The business does not care whether an event travels over Kafka, an in-process bus or a
cloud queue, or whether a service runs as a microservice, a module of a monolith or a set
of serverless functions. Those are engineering choices, and they change over time.

An OpenAPPL blueprint states what the system does and leaves how it is realised to the
compiler. Language, database, message broker, deployment topology and frameworks are
chosen when you compile, not when you design. The same blueprint can be compiled to
different stacks without being edited, and a compiler can even be a mix of deterministic
templates and AI synthesis. Whatever the back end, the blueprint stays the reviewed and
governed artifact.

## The idea in one picture

OpenAPPL splits application generation into two halves that can each be checked on their
own:

- **Upstream, intent to blueprint.** People and AI agents turn requirements into a
  blueprint. This half is creative, but its output is mechanically checked against the
  schema.
- **Downstream, blueprint to code.** A compiler turns the blueprint into a running system.
  This half can be fully deterministic, AI-assisted or a hybrid; the blueprint does not
  change.

Authors may only write blueprints. They cannot change the schema. An agent cannot extend
the vocabulary, only compose it, and that is what makes the AI loop safe.

Next: [How it works](how-it-works.md).
