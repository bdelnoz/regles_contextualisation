<!--
Document : README.md
Author : Bruno DELNOZ
Version : V4.5
Date : 2026-08-07
Repository : regles_contextualisation
-->

# Regles Contextualisation

Public Markdown repository for reusable SOLO operating rules used to guide AI-assisted work, especially with ChatGPT-style assistants.

The repository keeps reusable rules, custom-instruction helpers, AI working notes, and feature-request material in plain Markdown so they can be reviewed, versioned, shared, and reused across AI sessions.

## Active public SOLO rule files

| File | Version | Purpose |
|---|---:|---|
| `_RULES_SOLO232_CONTEXTUALISATION.md` | V232 | Global contextualization rules including automatic repository detection, immutable AGENTS/CLAUDE safeguards, additive `.gitignore` protection, permanent investigation reports, modes and public-safe interaction conventions. |
| `_RULES_SOLO410_SCRIPTING.md` | SOLO410 | Scripting workflow with automatic repository-mode activation, immutable AGENTS/CLAUDE protection, mandatory additive `.gitignore` baseline, artifacts, versioning, packaging, validation, documentation and non-regression controls. |
| `_RULES_SOLO117_RULESOPERATOR.md` | SOLO117 | Rules-operator workflow synchronizing CTX232 and SCRIPT410 global repository protections, the verified Custom Instructions limit, GitHub version reporting, resilient loading, packaging and public-safe controls. |

## Stable SOLOLAST aliases

| Stable file | Points to |
|---|---|
| `_RULES_SOLOLAST_CONTEXTUALISATION.md` | latest contextualisation rule |
| `_RULES_SOLOLAST_SCRIPTING.md` | latest scripting rule |
| `_RULES_SOLOLAST_RULESOPERATOR.md` | latest rules-operator rule |

The `SOLOLAST` files are public copies of the latest active version for each family. They do not create separate rule families.

## Custom Instructions

`_CUSTOM_INSTRUCTIONS.md` contains the compact ChatGPT Custom Instructions profile used to load the public SOLO rules from GitHub.

It defines:

- first-message bypass behavior;
- default contextualization loading;
- complete three-family loading for unqualified requests to read or apply the SOLO rules;
- later activation of contextualisation, scripting, or operator rules;
- authorized fallback methods when an initial public GitHub read fails;
- protection against claiming that a remote file was read when it was not actually read.

## Public repository structure

```text
.
├── AGENTS.md
├── CLAUDE.md -> AGENTS.md
├── README.md
├── _CUSTOM_INSTRUCTIONS.md
├── _RULES_SOLO232_CONTEXTUALISATION.md
├── _RULES_SOLO410_SCRIPTING.md
├── _RULES_SOLO117_RULESOPERATOR.md
├── _RULES_SOLOLAST_CONTEXTUALISATION.md
├── _RULES_SOLOLAST_SCRIPTING.md
├── _RULES_SOLOLAST_RULESOPERATOR.md
└── AI_STUDYING_FILES/
```

`AI_STUDYING_FILES/` is intentionally public. It may contain reusable AI study material, feature-request templates, question/answer documents, and related Markdown or PDF resources.

## Local-only material

Typical local-only paths and patterns include:

```text
.docs/
.old/
.private/
.zip/
.tmp/
*.zip
_RULES_PRIVATE_*
```

The generic `_RULES_PRIVATE_*` pattern is allowed in public documentation because it describes a generic exclusion rule.

Public documentation must not expose the real full names of private rule modules.

## Public-safe policy

Public rule files must not contain:

- personal case details;
- private health or family details;
- secrets, tokens, credentials, or private paths;
- exact private module names;
- private archive content;
- local-only ZIP payloads;
- historical changelogs that belong in local documentation.

When private context exists locally, it must remain ignored by Git and outside public packages.

## How to use the rules

1. Start with `_RULES_SOLOLAST_CONTEXTUALISATION.md`.
2. Add `_RULES_SOLOLAST_SCRIPTING.md` for scripts, code, shell commands, repositories, packaging, file generation, or technical documentation.
3. Add `_RULES_SOLOLAST_RULESOPERATOR.md` only when creating, modifying, merging, versioning, packaging, or auditing SOLO rule files.

Example:

```text
Load _RULES_SOLOLAST_CONTEXTUALISATION.md.
For scripting work, also load _RULES_SOLOLAST_SCRIPTING.md.
For SOLO rule maintenance, also load _RULES_SOLOLAST_RULESOPERATOR.md.
```

## Chat title convention

```text
000. <type lisible> +++<TYPE_TECH>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

Examples:

```text
000. operator +++OP117_CTX232_S410_20260807
000. scripting +++SCRIPT_FIREWALL_CTX232_S410_20260807
000. docs +++README_REPO_CONTEXT_RULES_20260802
```

## Versioning

New rule changes create a new numbered version.

The stable `SOLOLAST` copies must be updated whenever the active version changes.

## Markdown-first design

Markdown is used because it is easy to inspect, diff, reuse, archive, and review publicly.

## Important note

These files are workflow and behavior instructions for AI-assisted work. They are not a security product, legal framework, medical guideline, or official AI benchmark.

## License

No license has been selected.

Add a `LICENSE` file if public reuse terms need to be defined explicitly.
