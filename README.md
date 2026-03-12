# gemini-subagent

A Claude Code plugin that teaches Claude to use [Gemini CLI](https://github.com/google-gemini/gemini-cli) as a local subagent for delegating tasks.

## Why?

Claude Code spends expensive tokens (especially output tokens on Opus) generating boilerplate, writing tests, and analyzing files. Gemini CLI runs locally for free and handles these tasks well.

**Real savings:** ~55% tokens per delegated task, with the main benefit being context window preservation.

## What gets delegated?

- Code generation (functions, classes, configs)
- Test suite generation
- Single-file and multi-file refactoring
- Document analysis (.docx, .pdf — Gemini has 1M token context)
- Code review and bug finding
- Writing regex, SQL, shell commands
- Explanations and documentation drafts

## What stays in Claude Code?

- Multi-file architectural decisions
- Security-critical reviews
- Tasks requiring conversation context
- Anything needing Claude Code tools (Edit, Grep, etc.)

## Prerequisites

Install Gemini CLI:

```bash
npm install -g @google/gemini-cli
gemini  # First run: authenticate with Google account
```

## Install

```bash
claude plugin install <github-url>
```

## Usage

Once installed, Claude Code automatically delegates appropriate tasks to Gemini. No manual invocation needed — the skill triggers when Claude identifies a task that fits the delegation criteria.

You can also explicitly ask: *"use gemini to generate tests for this file"*

## License

MIT
