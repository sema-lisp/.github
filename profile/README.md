<h1 align="center">Sema</h1>

<p align="center">
  A Lisp where LLM agents are language primitives, not an SDK —<br>
  compiled to a fast bytecode VM, shipped as a single binary.
</p>

<p align="center">
  <a href="https://sema.run"><img src="https://img.shields.io/badge/try_it-sema.run-c8a855?style=flat" alt="Playground"></a>
  <a href="https://sema-lang.com/docs/"><img src="https://img.shields.io/badge/docs-sema--lang.com-c8a855?style=flat" alt="Docs"></a>
  <a href="https://github.com/HelgeSverre/sema"><img src="https://img.shields.io/badge/source-HelgeSverre%2Fsema-c8a855?style=flat" alt="Source"></a>
</p>

---

**Stop rewriting the agent loop.** Every LLM script grows the same scaffolding — retries, caching, cost caps, rate limits, tool dispatch, conversation state. Sema makes that scaffolding the runtime: your script stays the size of its idea, ships as a single binary, and your coding agent already speaks the language.

Sema is a Scheme-like Lisp where **prompts are s-expressions**, **conversations are persistent data structures**, and **LLM calls are just another form of evaluation**.

```scheme
(defagent coder
  {:system "You are a coding assistant."
   :tools  [read-file edit-file run-command]
   :max-turns 20})

(llm/with-budget {:max-cost-usd 0.50}
  (lambda () (agent/run coder "Fix the failing test in src/parser.rs")))
```

### Explore

- **[Playground](https://sema.run)** — run Sema in the browser, no install
- **[Documentation](https://sema-lang.com/docs/)** — language guide, stdlib, internals
- **[For Agents](https://sema-lang.com/docs/for-agents)** — orienting a coding agent in a Sema codebase
- **[Source & releases](https://github.com/HelgeSverre/sema)** — the core language, VM, and toolchain

### What lives here

This org is the home for the Sema ecosystem. The core language and runtime (bytecode VM, stdlib, LLM providers, LSP, DAP, notebook, formatter) live in the main repository; editor integrations and shared tooling are being broken out into their own repos here so each can ship on its own cadence.

<sub>MIT licensed · built in Rust · <a href="https://sema-lang.com">sema-lang.com</a></sub>
