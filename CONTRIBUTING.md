# Contributing to OpenAPPL

Thank you for helping improve OpenAPPL.

- **Found a mistake or an unclear sentence?** Open an issue, or a pull request with the
  fix. Editorial changes go in directly.
- **Want to change the language?** New patterns, properties, changed rules and anything
  that affects compilers go through the RFC process: read
  [rfcs/README.md](rfcs/README.md) and start from
  [rfcs/0000-template.md](rfcs/0000-template.md).
- **Want to add an example blueprint?** Add it to `examples/`, describe it in
  [examples/README.md](examples/README.md), and make sure it validates with no errors
  against the current schema version.
- **Building a compiler or a tool?** Tell us in an issue; implementers are consulted on
  every change that affects the compiler specification.

## AI and automated contributions

Everything sent to this repository is reviewed by people, and review time is the scarcest
resource the project has. It cannot keep up with contributions produced at machine speed.
So, for every pull request, RFC and issue:

- **A person is responsible.** You may use AI tools to help, but you write the
  contribution, you understand every line of it, and you can explain and defend it in
  review. "The tool wrote it" is not an answer to a review question.
- **Say so.** If an AI tool helped produce the content (text, schema changes, examples,
  RFC sections), state it in the pull request or issue description, in one line: which
  tool, and for what. Spelling and grammar help needs no mention.
- **No autonomous submissions.** Pull requests, issues and RFCs opened by an agent or a
  bot on its own, without a person who wrote and stands behind them, are not accepted.
- **Low-effort submissions are closed.** Maintainers may close, without a detailed review,
  a contribution that looks generated and unreviewed: invented facts, rules the
  specification does not have, changes that do not build or validate, or text that does
  not answer the reviewer.
- **The sign-off is personal.** The Developer Certificate of Origin below is a statement
  made by you about your own contribution; do not sign off work you could not have
  certified yourself.

This rule is about contributing to the standard. Using AI to *use* the language is a
different matter: writing your own blueprints with AI agents, for example with the
mind-set skills, is welcome.

## Sign your commits

Every commit needs a Developer Certificate of Origin sign-off
(https://developercertificate.org). Add it with `git commit -s`; it appends a line like:

```
Signed-off-by: Ada Lovelace <ada@example.com>
```

By signing off you certify that you have the right to submit the contribution under the
terms in [LICENSE.md](LICENSE.md) and [PATENTS.md](PATENTS.md).

## How decisions are made

The steward decides on the recommendation of the Editors, after public review; see
[GOVERNANCE.md](GOVERNANCE.md). Everyone taking part follows the
[code of conduct](CODE_OF_CONDUCT.md).

## Contact

Questions and proposals: the issues and discussions of this repository. Sponsorship,
private matters and conduct reports: openappl@mindbricks.com.
