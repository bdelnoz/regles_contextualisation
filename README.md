# Regles Contextualisation

Public repository for a set of structured SOLO rules used to guide AI-assisted work, especially with ChatGPT-style assistants.

The goal of this repository is simple: keep reusable operating rules in plain Markdown files so they can be reviewed, versioned, shared, and reused across different AI sessions.

## What this repository contains

This repository currently exposes three public SOLO rule files:

| File | Purpose |
|---|---|
| `_RULES_SOLO226_CONTEXTUALISATION.md` | Global contextualization rules. Defines general behavior, response structure, reporting behavior, Read Aloud compatibility, public-safe handling, and interaction conventions. |
| `_RULES_SOLO405_SCRIPTING.md` | Scripting and technical-work rules. Defines how the assistant should handle scripts, repositories, command blocks, file modifications, validation, safety, and reproducible technical workflows. |
| `_RULES_SOLO105_RULESOPERATOR.md` | Rules operator rules. Defines how SOLO rules themselves must be created, modified, versioned, packaged, reviewed, and kept safe for public publication. |

These files are meant to be read as instruction layers. They are not application code.

## Why these rules exist

General-purpose AI assistants can behave inconsistently across long projects, technical tasks, and multi-step workflows.

These SOLO rules are designed to improve:

- continuity between sessions;
- safer technical execution;
- clearer reporting;
- cleaner Markdown output;
- better handling of long-running projects;
- stricter separation between public and local-only material;
- repeatable packaging and versioning of rule files.

## Public-safe repository policy

Only public-safe rule files are intended to be published here.

The public rule files must not contain:

- personal data;
- private case details;
- medical information;
- family information;
- secrets, tokens, credentials, or private paths;
- embedded changelog history that should live outside the public rules;
- private modules or local-only working files.

The public repository is intentionally limited to reusable, generic rules and documentation.

## Repository structure

Public files and folders may include:

```text
.
├── AGENTS.md
├── CLAUDE.md -> AGENTS.md
├── Feature_requests_standardization/
├── 350_QUESTIONS_TO_GET_AI_WORKING_INFOS/
├── VISUALS/
├── _RULES_SOLO104_RULESOPERATOR.md
├── _RULES_SOLO226_CONTEXTUALISATION.md
└── _RULES_SOLO405_SCRIPTING.md
```

The active operator rule may later be incremented, for example from `SOLO104` to `SOLO105`, while keeping the same role and naming logic.

## How to use the rules

A typical use is to provide one or more rule files to an AI assistant at the beginning of a session.

Recommended usage:

1. Start with the contextualization rules.
2. Add the scripting rules when the task involves code, shell commands, repositories, packaging, or file operations.
3. Add the rules operator file only when modifying the SOLO rule system itself.

Example session setup:

```text
Use `_RULES_SOLO226_CONTEXTUALISATION.md` as the global behavior layer.
Use `_RULES_SOLO405_SCRIPTING.md` for all scripting, repository, packaging, and command-line work.
Use `_RULES_SOLO105_RULESOPERATOR.md` only when creating or modifying SOLO rule files.
```

## Rule families

### Contextualisation

The contextualization rule file defines the general operating behavior expected from the assistant.

It covers areas such as:

- response style;
- session context handling;
- reporting mode;
- Read Aloud compatibility;
- Markdown formatting expectations;
- public-safe handling;
- interaction rules for long technical workflows.

### Scripting

The scripting rule file defines stricter behavior for technical work.

It covers areas such as:

- shell scripts;
- repository changes;
- ZIP packaging;
- file validation;
- command blocks;
- avoiding unnecessary refactors;
- preserving working baselines;
- producing copy-paste-ready commands when needed.

### Rules Operator

The rules operator file defines how the rule system must be maintained.

It covers areas such as:

- version increments;
- naming conventions;
- README and changelog handling;
- package creation;
- rule-only ZIP creation;
- anti-regression checks;
- privacy cleanup before publication;
- keeping public rules free from private or sensitive content.

## Versioning

SOLO files use explicit version numbers in their filenames.

Examples:

```text
_RULES_SOLO226_CONTEXTUALISATION.md
_RULES_SOLO405_SCRIPTING.md
_RULES_SOLO105_RULESOPERATOR.md
```

The version number is part of the file identity. New rule changes should create a new version rather than silently replacing the previous rule content.

## Markdown-first design

The repository intentionally uses Markdown because it is:

- easy to inspect;
- easy to diff;
- easy to reuse in AI sessions;
- readable without a dedicated application;
- suitable for public review.

## Important note

These rules are workflow and behavior instructions for AI-assisted work.

They are not a security product, legal framework, medical guideline, or official AI benchmark. They are a practical rule system designed to make AI collaboration more consistent, safer, and easier to audit.

## License

No license has been selected in this README.

If this repository is meant to be reused publicly by others, add an explicit license file such as `LICENSE`.
