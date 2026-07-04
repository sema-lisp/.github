# Security Policy

## Reporting a vulnerability

**Please do not report security vulnerabilities through public GitHub issues, pull requests, or discussions.**

Report privately using **GitHub's private vulnerability reporting**:

1. Go to the affected repository's **Security** tab.
2. Click **Report a vulnerability**.
3. Fill in the advisory form with as much detail as you can.

This opens a private channel visible only to the maintainers. If you cannot use GitHub's reporting form, you may reach the maintainer directly at **helge.sverre@gmail.com** — but the GitHub advisory flow is strongly preferred, as it keeps the report private and tracked until a fix ships.

### What to include

- A description of the vulnerability and its impact.
- Steps to reproduce (a minimal Sema program or command is ideal).
- The affected version (`sema --version`) and platform.
- Any suggested remediation, if you have one.

### What to expect

- We aim to acknowledge a report within a few days.
- We'll work with you privately to confirm, fix, and coordinate disclosure.
- We'll credit you in the release notes and advisory unless you ask us not to.

Please give us a reasonable window to release a fix before any public disclosure.

## Supported versions

Sema is under active development. Security fixes are made against the **latest released version**. Please confirm an issue reproduces on the most recent release before reporting.

## Scope

The core language, VM, standard library, and first-party tooling (LSP, DAP, notebook, MCP server, editor plugins) in this organization are in scope. Because Sema can execute arbitrary code and shell commands by design, "a Sema program can read files or run commands" is expected behavior, not a vulnerability — reports should concern flaws that let untrusted input escape the intended execution model (e.g. sandbox escapes, memory-safety bugs, or supply-chain issues in the toolchain).
