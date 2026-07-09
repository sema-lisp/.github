# Contributing to Sema

Thanks for your interest in Sema — a Lisp where LLM agents are language primitives. Contributions of all sizes are welcome, from typo fixes to new stdlib functions to editor integrations.

## Ground rules

- **No CLA, no sign-off required.** Contributions are accepted under the project's [MIT license](https://github.com/sema-lisp/sema/blob/main/LICENSE). By opening a pull request, you agree that your contribution may be distributed under those terms.
- **Be respectful.** This project follows a [Code of Conduct](CODE_OF_CONDUCT.md).
- **Discussion happens in Issues.** Open an issue to report a bug or propose a feature before investing in a large change, so we can agree on the approach.

## AI-assisted contributions are welcome

Sema is an agent-native language — it ships an [`AGENTS.md`](https://github.com/sema-lisp/sema/blob/main/AGENTS.md) precisely so coding agents can work in this codebase. Using an AI coding assistant to write, review, or explore a contribution is explicitly encouraged. Point your agent at `AGENTS.md`; it's the canonical build/test/architecture guide.

What we ask in return, so AI assistance raises quality instead of noise:

- **You understand and stand behind every line you submit.** You are the author, not the tool. Be ready to explain how it works and why, and to revise it in review.
- **It actually runs.** Build, tests, lint, and any relevant examples pass locally before you open the PR (see below). "The model said it works" is not verification.
- **It's scoped and genuine.** No mass-generated, speculative, or low-effort PRs (e.g. sweeping "refactors", drive-by reformatting, or generated changes you haven't read). These are closed without review.
- **Follow the house rules.** The conventions in `AGENTS.md` — naming, comment style (comment the code as it stands, not what changed), error constructors, testing patterns — apply to AI-written code exactly as to hand-written code.

We don't require you to disclose tool use, and we don't treat AI-assisted PRs differently — they're held to the same bar as any other contribution.

## Development workflow

The canonical guide is [`AGENTS.md`](https://github.com/sema-lisp/sema/blob/main/AGENTS.md). In short:

```bash
make build      # dev build
make test       # run the test suite
make lint       # fmt-check + clippy -D warnings
make fmt        # apply formatting
make all        # lint + test + build
```

Before opening a pull request:

1. **Add a test.** New builtins, special forms, and bug fixes should come with a test — see the testing section in `AGENTS.md` for where each kind lives.
2. **Run `make all`** (or at least `make lint && make test`) and confirm it's green.
3. **Keep the change focused.** One logical change per PR; write a clear description of what and why.
4. **Update docs** if you changed user-facing behavior (stdlib docs live in `crates/sema-docs/entries/`).

## Where things live

- **Language / VM / stdlib:** `crates/` (see the architecture overview in `AGENTS.md`).
- **Editor plugins:** `editors/` (being broken out into their own repos in this org).
- **Docs & website:** `website/`; **playground:** `playground/`.
- **Examples:** `examples/` and `playground/examples/`.

## Questions

Open an issue on the relevant repository. For security reports, follow [SECURITY.md](SECURITY.md) instead of filing a public issue.
