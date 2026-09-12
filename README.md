<!--
Document : README.md
Author : Bruno DELNOZ
Version : V5.4
Date : 2026-09-12
Repository : regles_contextualisation
-->

# Regles Contextualisation

Public Markdown repository for reusable SOLO operating rules used to guide AI-assisted work, especially with ChatGPT-style assistants.

The repository keeps reusable rules, lightweight bootstrap Custom Instructions, AI working notes, and feature-request material in plain Markdown so they can be reviewed, versioned, shared, and reused across AI sessions.

## Active public SOLO rule files

| File | Version | Purpose |
|---|---:|---|
| `_RULES_SOLO234_CONTEXTUALISATION.md` | V234 | Global contextualization rules: general SOLO behavior, Read Aloud, acquired-context/delta control, Emploi/JOBS mode, repository detection and immutable AGENTS/CLAUDE safeguards. |
| `_RULES_SOLO412_SCRIPTING.md` | SOLO412 | Scripting workflow with mandatory pre-flight compliance and blocking multi-file ZIP delivery: one file direct; two or more files in one final ZIP. |
| `_RULES_SOLO122_RULESOPERATOR.md` | SOLO122 | Rules-operator workflow with anti-overlap/non-regression controls and mandatory post-push new-chat validation prompt delivered with every GitHub RULES package. |

## Stable SOLOLAST aliases

| Stable file | Points to |
|---|---|
| `_RULES_SOLOLAST_CONTEXTUALISATION.md` | latest contextualisation rule |
| `_RULES_SOLOLAST_SCRIPTING.md` | latest scripting rule |
| `_RULES_SOLOLAST_RULESOPERATOR.md` | latest rules-operator rule |

Each `SOLOLAST` file is an exact active copy of its current numbered rule file.

## Custom Instructions = bootstrap only

`_CUSTOM_INSTRUCTIONS.md` is intentionally small. It does not duplicate the SOLO rule bodies.

Its job is only to bootstrap/route the public SOLO families:

- on the first message of a normal new chat, before answering, read CTX from its direct RAW GitHub URL;
- explicit Scripting request: CTX + Scripting;
- clear repository evidence: activate Scripting repo at that moment;
- explicit Operator request: CTX + Operator;
- explicit request for all SOLO rules: CTX + Scripting + Operator;
- reload in an already specialized chat: CTX + the family/families already active;
- never claim a rule file was loaded without a real read.

`_CUSTOM_INSTRUCTION_1500.md` is the reduced bootstrap variant for environments with a 1500-character Custom Instructions limit. It follows the same routing logic with less wording.

Private/business-specific modes are not routed by these public Custom Instructions. Their dependencies and activation logic belong in their own private rule modules.

## Public repository structure

```text
.
├── AGENTS.md
├── CLAUDE.md -> AGENTS.md
├── README.md
├── _CUSTOM_INSTRUCTIONS.md
├── _CUSTOM_INSTRUCTION_1500.md
├── _RULES_SOLO234_CONTEXTUALISATION.md
├── _RULES_SOLO412_SCRIPTING.md
├── _RULES_SOLO122_RULESOPERATOR.md
├── _RULES_SOLOLAST_CONTEXTUALISATION.md
├── _RULES_SOLOLAST_SCRIPTING.md
├── _RULES_SOLOLAST_RULESOPERATOR.md
└── AI_STUDYING_FILES/
```

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

Older numbered RULES are moved to `.old/` when superseded. Private modules stay local and ignored by Git.


## Archive naming convention

Before replacing a root Custom Instructions file, archive the current file in `.old/` **under a unique versioned filename**.

Required pattern:

```text
.old/_CUSTOM_INSTRUCTIONS_YYYY-MM-DD_VNN_<size>chars.md
.old/_CUSTOM_INSTRUCTION_1500_YYYY-MM-DD_VNN_<size>chars.md
```

Rules:

- archive first, replace second;
- never store an archived Custom Instructions file under its active root filename;
- never reuse an existing archive filename;
- never overwrite a previous archive;
- increment `VNN` for every archived revision on the same history line;
- keep all previous revisions for rollback.

## Public-safe policy

Public files must not contain personal case details, health/family details, secrets, credentials, sensitive local paths, exact private-module names, private archives or local ZIP payloads.

`AGENTS.md` is preserved. `CLAUDE.md` must remain the symlink `CLAUDE.md -> AGENTS.md`.

## How to use the rules

1. Start with `_RULES_SOLOLAST_CONTEXTUALISATION.md`.
2. Add `_RULES_SOLOLAST_SCRIPTING.md` when Scripting is explicitly activated or repository evidence activates Scripting repo.
3. Add `_RULES_SOLOLAST_RULESOPERATOR.md` when Operator is explicitly activated.
4. Use `lis toutes les règles SOLO` only when all three public families are deliberately required.

## Versioning and delivery

New rule changes create a new numbered version and update the matching `SOLOLAST` alias.

SCRIPT412 requires a final pre-flight compliance check before delivery. A delivery containing two or more files must be packaged into one ZIP containing the final versions only; if any included file changes, the ZIP must be rebuilt.


## Mandatory post-push SOLO validation

SOLO122 adds a delivery acceptance gate for public RULES updates.

After the user performs the local commit/push (`gita` may be the user's local alias) and confirms that the push is complete, the Operator must immediately print the ready-to-run post-push test prompts directly in the chat. No persistent `POST_PUSH_TEST_PROMPT.md` file is created or shipped.

For a full three-family validation the canonical sequence is:

1. new chat -> CTX only;
2. repository evidence -> CTX + Scripting;
3. explicit Operator activation -> CTX + Scripting + Operator;
4. reload -> the same active families, with no extra family.

A RULES update is not considered post-push validated until the prompts printed in chat have been run and the observed versions match the expected published versions.


## Commit-pinned post-push chain test

After a Git push is confirmed, the Operator must generate the acceptance test directly in chat as one copy/paste block.

The test must:
- use the exact pushed commit SHA;
- build RAW GitHub URLs pinned to that commit, never `main`;
- perform the full sequence CTX -> Scripting -> Operator -> Reload automatically;
- require a real read at every step;
- return PASS/FAIL per step and one final verdict.

No persistent post-push prompt file is created.

## Chat title convention

```text
000. <type lisible> +++<TYPE_TECH>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

Examples:

```text
000. operator +++OP122_CTX234_S412_20260912
000. scripting +++SCRIPT_REPO_CTX234_S412_20260912
000. docs +++README_REPO_CONTEXT_RULES_20260912
```

## Markdown-first design

Markdown is used because it is easy to inspect, diff, reuse, archive and review.

## Important note

These files are workflow and behavior instructions for AI-assisted work. They are not a security product, legal framework, medical guideline or official AI benchmark.

## License

No license has been selected.

Add a `LICENSE` file if public reuse terms need to be defined explicitly.
