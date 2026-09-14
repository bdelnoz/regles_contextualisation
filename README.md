<!--
Document : README.md
Author : Bruno DELNOZ
Version : V6.1
Date : 2026-09-14
Repository : ai-context-rules
-->

# AI Context Rules

Public Markdown repository for reusable SOLO operating rules used to guide AI-assisted work, especially with ChatGPT-style assistants.

The repository keeps reusable rules, lightweight bootstrap Custom Instructions, AI working notes, and feature-request material in plain Markdown so they can be reviewed, versioned, shared, and reused across AI sessions.

The public repository is maintained in English so the framework can be reviewed, reused, and discussed internationally.

## Active public SOLO rule files

| File | Version | Purpose |
|---|---:|---|
| `_RULES_SOLO234_CONTEXTUALIZATION.md` | V234 | Global contextualization rules: general SOLO behavior, Read Aloud, acquired-context/delta control, Employment/JOBS mode, repository detection and immutable AGENTS/CLAUDE safeguards. |
| `_RULES_SOLO413_SCRIPTING.md` | SOLO413 | Scripting workflow with blocking canonical CLI compliance, reserved control aliases, `--exec --<action>` invocation, pre-flight validation, and mandatory multi-file ZIP delivery. |
| `_RULES_SOLO125_RULESOPERATOR.md` | SOLO125 | Rules-operator workflow with anti-overlap/non-regression controls, idempotent loaded-rule state, and commit-pinned CORE + FULL post-push validation. |

## Stable SOLOLAST aliases

| Stable file | Points to |
|---|---|
| `_RULES_SOLOLAST_CONTEXTUALIZATION.md` | latest contextualization rule |
| `_RULES_SOLOLAST_SCRIPTING.md` | latest scripting rule |
| `_RULES_SOLOLAST_RULESOPERATOR.md` | latest rules-operator rule |

Each `SOLOLAST` file is an exact active copy of its current numbered rule file.

## Custom Instructions = bootstrap only

`_CUSTOM_INSTRUCTIONS.md` is intentionally small. It does not duplicate the SOLO rule bodies.

Its job is only to bootstrap/route the public SOLO families:

- on the first message of a normal new chat, before answering, read CTX from its direct RAW GitHub URL;
- activate Scripting or Operator by reading only the family that is still missing when CTX is already loaded;
- clear repository evidence activates Scripting once; repeated repository evidence does not repeatedly reload the same file;
- ordinary mentions of `scripting`, continued code work, or questions about already-loaded rules do not trigger remote rereads;
- explicit `reload`, `reapply`, `refresh`, `load latest/current rules`, or a stated rules/repository update triggers the appropriate real reread;
- reload in an already specialized chat rereads CTX + the active family/families;
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
├── _RULES_SOLO234_CONTEXTUALIZATION.md
├── _RULES_SOLO413_SCRIPTING.md
├── _RULES_SOLO125_RULESOPERATOR.md
├── _RULES_SOLOLAST_CONTEXTUALIZATION.md
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

1. Start with `_RULES_SOLOLAST_CONTEXTUALIZATION.md`.
2. Add `_RULES_SOLOLAST_SCRIPTING.md` when Scripting is explicitly activated or repository evidence activates Scripting repo.
3. Add `_RULES_SOLOLAST_RULESOPERATOR.md` when Operator is explicitly activated.
4. Use `read all SOLO rules` only when all three public families are deliberately required.

## Versioning and delivery

New rule changes create a new numbered version and update the matching `SOLOLAST` alias.

SCRIPT413 requires a final pre-flight compliance check before delivery, including the blocking CLI parser/help/example contract when a durable CLI is in scope. A delivery containing two or more files must be packaged into one ZIP containing the final versions only; if any included file changes, the ZIP must be rebuilt.


## Canonical SOLO CLI contract

SCRIPT413 makes the durable CLI contract blocking and unambiguous.

For operational scripts, the canonical pattern is:

```text
./script.sh --exec --<business-action> [OPTIONS]
./script.sh --simulate --<business-action> [OPTIONS]
```

Canonical control aliases are reserved when applicable:

```text
-h   --help
-exe --exec
-s   --simulate
-pr  --prerequis
-i   --install
-st  --stop
-ch  --changelog
-pu  --purge
```

Business options must not reuse active reserved aliases. Legacy alias conflicts preserve the business long option/behavior while only the conflicting short alias is removed or remapped. Positional business actions such as `script.sh CAPTURE` are not canonical unless explicitly requested.

Before delivery, SCRIPT413 requires parser/help/example consistency checks; syntax-only validation is insufficient.

## Mandatory post-push SOLO validation

SOLO125 preserves the delivery acceptance gate and adds idempotent loaded-rule-state validation so already-active families are not repeatedly fetched during normal follow-up work.

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


## Full acceptance validation

After a successful commit-pinned CORE CHAIN test, changes affecting Operator, bootstrap, routing, reload, delivery, packaging, aliases, old-version handling or post-push validation require a second validation layer: FULL ACCEPTANCE.

FULL ACCEPTANCE combines:
- observable repository checks;
- one-copy/paste behavioral checks;
- anti-overlap behavior;
- single-file vs multi-file delivery rules;
- archive/SOLOLAST decisions;
- repository protection invariants;
- commit-pinned post-push behavior.

The final release verdict reports both CORE CHAIN and FULL ACCEPTANCE.


## Canonical 20-check FULL ACCEPTANCE

After CORE CHAIN validation, releases affecting Operator/bootstrap/routing/reload/delivery use the canonical 20-check FULL ACCEPTANCE.

The behavioral block is a single copy/paste and covers:
- routing/real reads;
- anti-memory;
- anti-overlap;
- delivery/ZIP behavior;
- version archiving and SOLOLAST;
- repository protection;
- commit-pinned post-push workflow.

Repository-observable checks remain a separate Operator-side layer. Non-observable local checks must be reported as NON OBSERVABLE, never invented as PASS.

## Chat title convention

```text
000. <readable type> +++<TYPE_TECH>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

Examples:

```text
000. operator +++OP125_CTX234_S413_20260914
000. scripting +++SCRIPT_REPO_CTX234_S413_20260914
000. docs +++README_REPO_CONTEXT_RULES_20260914
```

## Markdown-first design

Markdown is used because it is easy to inspect, diff, reuse, archive and review.

## Important note

These files are workflow and behavior instructions for AI-assisted work. They are not a security product, legal framework, medical guideline or official AI benchmark.

## License

No license has been selected.

Add a `LICENSE` file if public reuse terms need to be defined explicitly.
