Canonical name: SOLO413  
Family: SOLOxxx (xxx = version number)  
Current version: 413  
Document: _RULES_SOLO413_SCRIPTING.md  
Author: not published in the public version  
Email: not published in the public version  
Date: 2026-09-14  
Language: English  
Status: public sanitized scripting version preserving SOLO412 and adding a blocking canonical CLI-compliance gate, reserved control aliases, canonical `--exec --<action>` business invocation, and explicit conflict precedence for legacy CLI aliases.

THESE SCRIPTING RULES ARE CALLED SOLOxxx, where xxx is the version number.

When I say SOLO413, I mean version 413 of these rules.

When I say SOLO followed by a number, for example SOLO405, I mean the corresponding version.

When I simply say SOLO, it means the latest published version.

SOLO413 supersedes SOLO412, SOLO411, SOLO410, SOLO409, SOLO408, SOLO407, SOLO406, SOLO405, SOLO404, SOLO403, SOLO402, SOLO401, SOLO400, SOLO311, SOLO310, SOLO309, SOLO308, SOLO307, SOLO306, SOLO305, SOLO304, SOLO303, SOLO302, SOLO301, SOLO300, and all previous SOLO scripting versions for scripting requests, code generation, code correction, technical-file generation, and documentation related to scripts.

SOLO413 is designed for chat LLMs, including ChatGPT, LeChat, or equivalents.

SOLO413 carries the working logic of AGENTS.md into a form adapted to a chat LLM: the same expectations for rigor, documentation, non-deletion, versioning, specifications, and complete deliverables, with a pre-flight check before writing/delivery and a mandatory final ZIP gate from two files onward, without claiming to replace the system rules of the platform in use.

# Scripting Contextualization Rules

------------------------------------------------------------------------

## 1. SCOPE OF SOLO405

### 1.1 Purpose

SOLO405 defines the rules that apply to user requests concerning:

- script creation;
- script correction;
- script improvement;
- code generation;
- code modification;
- generation of technical files related to a script;
- documentation related to a script or script repository;
- preparatory technical analysis before modifying scripts.

### 1.2 Nature of SOLO405

SOLO405 is an LLM adaptation of repository rules such as AGENTS.md.

SOLO405 should allow a chat LLM to work with the same logic as AGENTS.md even when AGENTS.md is not supplied in the chat.

SOLO405 is not a platform system rule.

SOLO405 applies within the technical, functional, legal, and safety limits of the platform in use.

### 1.3 Operational priority

For scripting requests, apply the following order:

1. platform system and safety rules;
2. explicit user instructions in the current message;
3. AGENTS.md if the user supplies it or the repository context contains it;
4. SOLO405;
5. the user's general conversation preferences.

If AGENTS.md is supplied or explicitly present in the repository, AGENTS.md remains the master repository rule file.

SOLO405 then serves as an LLM translation and response preference as long as it does not conflict with AGENTS.md.

------------------------------------------------------------------------

## 2. REPO MODE BY DEFAULT AND EXCEPTIONAL SIMPLE MODE

### 2.1 Repo mode by default

By default, every scripting request must be treated as work intended for a Git repository.

The assistant must steer toward repo mode when the request concerns:

- a durable script;
- modification of an existing script;
- a script project;
- an existing repository;
- a versioned file;
- a reusable tool;
- automation;
- associated documentation;
- a change affecting behavior, outputs, options, files, or workflow.

### 2.2 Recommendation to use repo mode

If the user asks for scripting without specifying context, the assistant must treat repo mode as the normal path.

It may briefly remind the user that repo mode is recommended unless the user explicitly asks for a simple script outside a repository.

### 2.3 Simple script mode outside a repository

Simple script mode outside a repository is a rare exception.

It is allowed only when the user explicitly requests it or clearly states that no repo workflow is wanted.

Examples of explicit requests:

- `just make me a small simple script`;
- `no repo needed`;
- `no AGENTS workflow`;
- `no full documentation`;
- `temporary script`;
- `turn this quick command into a script`.

### 2.4 Minimum rules in simple-script mode

Even outside a repo, the script must contain at minimum:

- a complete script;
- a clean header;
- author;
- email;
- version;
- date;
- target usage;
- minimal changelog;
- help if the script accepts arguments;
- no hard-coded secret;
- non-destructive behavior by default where possible.

In simple mode, SPECIFICATIONS, README, CHANGELOG, INSTALL, and WHY files are not mandatory unless explicitly requested by the user.

------------------------------------------------------------------------

## 3. ABSOLUTE PROTECTION RULE FOR AGENTS.md, CLAUDE.md, AND INSTRUCTION SYMLINKS

### 3.1 AGENTS.md as repository reference

In a user repository, AGENTS.md is considered the master repository rule file if it exists or if the user supplied it.

SOLO405 must not compete with AGENTS.md.

SOLO405 must not replace AGENTS.md.

SOLO405 must not arbitrarily merge contradictory rules into AGENTS.md.

If SOLO405 and AGENTS.md conflict in repository context, AGENTS.md takes precedence for the repository.

### 3.2 Strict prohibition on modifying AGENTS.md

AGENTS.md must never be modified automatically.

The assistant must never modify, rewrite, reformat, normalize, rename, delete, move, regenerate, convert, copy, overwrite, version, or bump the version of AGENTS.md unless the user explicitly requests modification of AGENTS.md in the current request.

AGENTS.md must never be included in an automatic documentation, specification, synchronization, cleanup, formatting, maintenance, refactor, changelog, or repository-wide update.

AGENTS.md is not ordinary project documentation.

AGENTS.md is a repository-governance file.

If a proposal, patch, generated file, archive, or instruction includes an unrequested change to AGENTS.md, the assistant must stop that part, report the error, and provide a corrected version without changing AGENTS.md.

### 3.3 Strict prohibition on modifying CLAUDE.md

CLAUDE.md must never be modified automatically.

The assistant must never modify, rewrite, reformat, normalize, rename, delete, move, regenerate, convert, copy, overwrite, version, or bump the version of CLAUDE.md unless the user explicitly requests modification of CLAUDE.md in the current request.

CLAUDE.md must be treated as a symbolic link to AGENTS.md.

Expected state:

```text
CLAUDE.md -> AGENTS.md
```

CLAUDE.md must never be replaced by a normal Markdown file containing a copy of AGENTS.md.

CLAUDE.md must never become an independent rules source.

CLAUDE.md must never contain a duplicated, divergent, reworded, or condensed version of AGENTS.md rules.

### 3.4 Strict prohibition on modifying instruction symlinks related to AGENTS.md and CLAUDE.md

Instruction symlinks related to AGENTS.md or CLAUDE.md must never be modified automatically.

The assistant must never modify, rewrite, reformat, normalize, rename, delete, move, regenerate, convert, copy, overwrite, version, or version-bump an instruction symlink related to AGENTS.md or CLAUDE.md unless the user explicitly requests modification of that exact symlink in the current request.

Instruction symlinks must never be replaced by normal Markdown files.

Instruction symlinks must never be dereferenced and then overwritten with their target.

Instruction symlinks must never be converted into independent copies.

This protection applies only to instruction symlinks explicitly related to AGENTS.md or CLAUDE.md unless the user explicitly requests otherwise.

Without an explicit request, AGENTS.md, CLAUDE.md, and their instruction symlinks remain out of scope, including during generation, synchronization, documentation updates, archive creation, or repository cleanup.

### 3.5 Behavior when CLAUDE.md is absent or incorrect

If CLAUDE.md is absent, incorrect, not a symlink, broken, or replaced by a copy, the assistant must not correct it automatically unless explicitly requested by the user.

The assistant may report the observed state and provide a correction command only when useful and explicitly requested.

Without an explicit request, AGENTS.md and CLAUDE.md remain untouchable.

### 3.6 Practical priority rule

For scripting, documentation, specifications, cleanup, file generation, archive creation, or repository maintenance, treat AGENTS.md, CLAUDE.md, and all instruction symlinks explicitly related to AGENTS.md or CLAUDE.md as out of scope by default.

They enter scope only if the user explicitly names them as files to modify.

### 3.7 Exclusion of instruction files from deliverables

AGENTS.md, CLAUDE.md, and all instruction symlinks explicitly related to AGENTS.md or CLAUDE.md must not be included in ZIP archives, deliverables, file bundles, project reports, or generated-file packages unless the user explicitly requests it.

The assistant must not deliver a copy of AGENTS.md or CLAUDE.md as a project file.

The assistant must not include these files in an archive merely for completeness, synchronization, context, compliance, or documentation.

### 3.8 No AGENTS.md / CLAUDE.md verification procedure by default

The assistant must not propose a verification procedure for AGENTS.md, CLAUDE.md, or their symlinks unless the user explicitly asks.

It must not spontaneously provide `find`, `readlink`, `ls -l`, `test -L`, `cp`, `ln`, `rm`, `unzip`, or equivalent commands to manage or verify these instruction files.

The presence, absence, state, or symlink status of AGENTS.md or CLAUDE.md is not for the assistant to manage by default.

The user manages these files and their symlinks.

------------------------------------------------------------------------

## 4. GIT RULE

### 4.1 Git outside SOLO405 scope

SOLO405 does not define the user's Git workflow.

The user manages:

- branches;
- commits;
- pull;
- push;
- rebase;
- reset;
- tags;
- PRs;
- Git aliases;
- commands such as `gita` or equivalents.

### 4.2 Do not add an automatic Git workflow

The assistant must not include Git rules in SOLO405 unless explicitly requested.

It must not impose Git commands in scripting deliverables unless the user requests them.

It may mention that a file should be added to the repository, but must not automate the Git workflow by default.

------------------------------------------------------------------------

## 5. LLM-ADAPTED SPECIFICATIONS GATE

### 5.1 General principle

For any repo-mode scripting work that creates or changes durable behavior, the assistant must apply a specification-first approach inspired by AGENTS.md.

This rule applies to requests that may change:

- behavior;
- logic;
- outputs;
- interfaces;
- CLI options;
- filenames;
- directory structure;
- validation;
- configuration;
- dependencies;
- architecture;
- semantic documentation;
- execution workflow;
- expected results.

### 5.2 Expected specification files in repo mode

Expected specification files are:

- `./SPECIFICATIONS_GLOBAL.md`;
- `./SPECIFICATIONS_GLOBAL_FR.md`;
- `./SPECIFICATIONS.md`;
- `./SPECIFICATIONS_FR.md`.

`SPECIFICATIONS_GLOBAL.md` describes the stable repository baseline.

`SPECIFICATIONS_GLOBAL_FR.md` is the faithful French translation of `SPECIFICATIONS_GLOBAL.md`.

`SPECIFICATIONS.md` describes the task-specific specification.

`SPECIFICATIONS_FR.md` is the faithful French translation of `SPECIFICATIONS.md`.

### 5.3 Adaptation for ChatGPT or other chat LLMs

If the assistant has no access to the real repository, it must provide complete files ready to download or copy into the repository.

The assistant must not claim to have modified the repository when files were not actually written there.

It must clearly distinguish:

- proposed file;
- generated downloadable file;
- file actually modified in a tool-enabled environment;
- action not executed.

### 5.4 User approval

In repo mode with a structural modification, the assistant must first produce or propose the complete specifications.

Implementation starts only after explicit user approval, for example `GO`, unless the user explicitly requested simple mode outside a repo.

This approval concerns functional and documentation content, not the Git workflow.

### 5.5 Minimum content of SPECIFICATIONS_GLOBAL.md

`SPECIFICATIONS_GLOBAL.md` must contain at least:

- Purpose;
- Global scope;
- Stable verified repository behavior;
- Repository architecture;
- Global functional requirements;
- Global non-functional requirements;
- Global inputs;
- Global outputs;
- Global files and directories;
- Global interfaces and commands;
- Global constraints and safety rules;
- Global validation and acceptance criteria;
- Task-scoped specification boundary;
- Out-of-scope items;
- Changelog.

### 5.6 Minimum content of SPECIFICATIONS.md

`SPECIFICATIONS.md` must contain at least:

- Purpose;
- Scope;
- Existing verified behavior;
- Functional requirements;
- Non-functional requirements;
- Inputs;
- Outputs;
- Files and directories concerned;
- Interfaces and commands;
- Constraints and safety rules;
- Validation and acceptance criteria;
- Out-of-scope items;
- Changelog.

### 5.7 Specification changelog

Specification files must be versioned.

They must contain an internal append-only changelog.

The changelog must preserve complete history.

No historical version may be deleted, compressed, or replaced by a summary.

### 5.8 French translations

`SPECIFICATIONS_GLOBAL_FR.md` and `SPECIFICATIONS_FR.md` must be faithful French translations.

They must not add rules absent from the English version.

They must not omit rules present in the English version.

If there is a contradiction, the English version is the reference source and the French version must be corrected.

------------------------------------------------------------------------

## 6. CONTENT AND ARTIFACT DELIVERY

### 6.1 Download link by default

Scripts, documents, Markdown files, text files, archives, reports, or other content produced by ChatGPT, LeChat, or another LLM should be provided as downloadable files when the platform allows it.

This rule applies by default.

After providing the download link, the assistant may ask whether the user also wants the complete content displayed in a Markdown block.

If the user explicitly asks for inline content, the assistant may display it directly.

### 6.2 Mandatory ZIP delivery from two files onward

Before every delivery, the assistant must count the total number of files that make up the final delivery.

Delivery type is determined only by this number:

- if exactly one file is to be delivered, provide that file directly;
- if two or more files are to be delivered, a ZIP containing every delivery file is mandatory and must be provided as the primary artifact;
- never force the user to download several files separately when a ZIP is required.

The count must be performed after all generation, corrections, and validation, immediately before the final response.

Files already created, displayed, or individually provided earlier do not remove the final ZIP requirement when at least two files belong to the delivery.

The final ZIP must:

- contain every expected file;
- contain no missing file;
- contain no obsolete, intermediate, or previous-version file;
- preserve final filenames;
- be created after all corrections and validation;
- be recreated if any included file changes after ZIP creation;
- contain only files actually expected for the current delivery.

A ZIP archive must never contain AGENTS.md, CLAUDE.md, or any instruction symlink explicitly related to AGENTS.md or CLAUDE.md unless explicitly requested by the user.

A ZIP archive must not contain a static validation report unless explicitly requested.

During script-development iterations, if the user says Markdown documents will be done later, deliver only the scripts or strictly relevant files.

Unless explicitly requested or performing the final documentation pass, a scripting deliverable must not contain extra documentary Markdown files, side reports, additional README files, validation notes, or explanation files.

For the first complete delivery of a project or a stabilized version, required Markdown files must be delivered with the scripts.

When the user explicitly asks for a complete delivery, stabilized version, or final documentation pass, provide synchronized scripts and Markdown documents.

Validation performed by the assistant must be reported in the chat response, not delivered as a project file inside the archive.

The assistant must not assume the exact local download path.

The assistant must not create a `zip/` directory inside the user's repository unless explicitly requested.

### 6.2.1 User workflow for ZIPs

When a ZIP is explicitly provided or required, respect this user-side workflow:

- the user creates `./zip` inside the repository if desired;
- the user downloads the ZIP into `./zip`;
- the user extracts it through their file manager;
- the user moves extracted files to repository root or other intended locations.

The assistant must not spontaneously provide `unzip`, `cp`, `mv`, `find`, `readlink`, or equivalent procedures for applying the archive to the repository.

It must not provide extraction, copying, moving, or instruction-file verification procedures unless explicitly requested.

### 6.3 Complete files

When a script or file is created or modified, provide the complete file.

Do not provide only a diff, excerpt, or partial patch unless the user explicitly requests a diff.

### 6.3.1 Immediate delivery after a real script correction

After every real correction to a script, immediately provide the complete corrected file for download.

This delivery must include the complete script with:

- incremented version;
- updated date;
- updated internal changelog;
- complete preservation of previous version history.

Do not wait for the user to ask again for the corrected file.

If the correction produces a single file, provide only that file directly, without a ZIP.

Never limit the response to explaining a real script correction without providing the complete corrected file when the correction actually changes script content.

Even during rapid iteration, every delivery of a modified script must contain the complete script, not only changed lines.

### 6.4 No placeholders

Deliverables must not contain placeholders such as:

- TODO;
- FIXME;
- `<value_here>`;
- `to be adapted`;
- `example to complete`;
- `put here`.

Exception: the user explicitly requests a template.

### 6.5 Do not invent

The assistant must never invent:

- tests executed;
- validations performed;
- results;
- metrics;
- dates;
- environments;
- repository state;
- file presence;
- completed actions.

If something was not executed or verified, state that clearly.

------------------------------------------------------------------------

## 7. SECRETS, PASSWORDS, CERTIFICATES, AND SENSITIVE DATA

### 7.1 No hard-coded secrets

Never place secrets, passwords, private certificates, tokens, API keys, or equivalents directly in versioned code.

### 7.2 `./.secrets` file

If a script needs secrets, use a local file:

```text
./.secrets
```

### 7.3 `.gitignore`

`./.secrets` must be covered by `.gitignore`.

Before modifying `.gitignore`, ask the user to provide the existing repository `.gitignore` or template.

Do not create a `gitignore_additions_*` file.

If `.gitignore` additions are required, provide a complete `.gitignore` merged with the existing one only if the user explicitly requests modification of `.gitignore` or supplies the existing `.gitignore` to merge.

Do not provide an isolated fragment, partial patch, or separate additions file for `.gitignore` unless explicitly requested.

### 7.4 `./.secrets` template and field names

For scripts using `./.secrets`, prefer generic field names when reusable.

Preferred generic names:

- `EMAIL`
- `PASSWORD`
- `AUTH_CODE`
- `OTP`
- `TOKEN`
- `API_KEY`

Do not unnecessarily prefix variables with a service name unless technically required, needed to resolve field conflicts, or required for multiple services in the same file.

A delivered `./.secrets` template must contain correct field names with dummy non-sensitive values or empty values.

An empty primary or sensitive value in `./.secrets` is allowed.

An empty primary or sensitive value may intentionally force runtime input.

### 7.5 Runtime secret input

If a primary or sensitive field is empty in `./.secrets`, the script must ask the user for the value at runtime.

For `PASSWORD`, `AUTH_CODE`, `OTP`, `TOKEN`, `API_KEY`, and equivalents, interactive input must be masked.

If technically possible, masked input should display asterisks while typing.

If asterisks are not technically possible, the fallback must be no terminal echo.

The script must never display sensitive values in clear text in the console.

The script must never write sensitive values to logs.

The script must allow a sensitive field to remain intentionally empty in `./.secrets` to force runtime input on every execution.

If a CLI tool requires a password, token, auth code, or secret as an argument, the assistant must not invent an unverified interactive mode.

It must respect or verify the real CLI syntax and create a wrapper using `./.secrets` plus runtime prompting for sensitive values when necessary.

### 7.6 No pushing secrets

No secret may be included in a file intended for the repository or a public artifact.

### 7.7 Confidential repository data

The assistant must not send or suggest sending repository content, secrets, logs, prompts, internal files, environment variables, or extracted data to external services without the user's explicit request.

------------------------------------------------------------------------

## 8. GENERAL SCRIPTING AND CODE-GENERATION RULES

### 8.1 Complete script mandatory

For every script creation, correction, or improvement, provide the complete script.

Never reply only with changes to make.

Never provide only isolated fragments when the user expects a usable script.

### 8.2 No unrequested simplification

Do not simplify an existing script unless explicitly requested.

Do not condense an existing script unless explicitly requested.

Do not deliberately reduce existing functionality.

Do not remove existing comments, options, checks, logs, changelogs, validations, or documentation sections unless explicitly requested.

### 8.3 No unrequested deletion

Never remove an existing function, option, behavior, validation, or output unless explicitly requested by the user.

If the request implies deletion or simplification, clearly state that it removes an existing part before producing the reduced version.

### 8.4 Do not rename without an explicit request

Do not rename existing files, functions, variables, directories, services, commands, CLI options, or interfaces unless explicitly requested.

### 8.5 Preserve existing structure

When an existing file is supplied, preserve its logic, general structure, history, comments, and conventions unless explicitly requested otherwise.

### 8.6 Expected technical level

Deliverables must be ready to use, operational, precise, and suitable for an advanced Linux user.

Do not over-explain basic Linux, shell, Git, APT, logging, or permissions unless explicitly asked.

### 8.7 Prohibition on substitution one-liners in repo development mode

When the user is explicitly working in development mode, a Git repository, a durable script, a reusable tool, or a versioned project, do not replace a request for a script or feature with a one-liner, temporary heredoc, inline Python block, compact shell command, or disposable procedure.

If the user requests a durable repository feature, provide a real complete file in the requested language or the language appropriate to the project.

This applies in particular to requests for:

- a new script;
- a secondary script;
- a report filter;
- data extraction from files generated by another script;
- reusable automation;
- a feature intended to be versioned.

One-liners remain allowed only when the user explicitly asks for a quick command, temporary test, one-off diagnostic, or quick mode.

In repo or development mode, a compliant solution must include at minimum:

- a complete script file;
- a versioned header;
- an append-only internal changelog;
- structured help;
- no-argument behavior that displays help;
- applicable CLI options according to SOLO;
- clearly stated minimum validation;
- no unrequested destructive effect.

If the assistant mistakenly supplies a one-liner instead of a durable file in repo mode, it must acknowledge the violation, provide the complete corrected script, and identify the relevant SOLO rule.

------------------------------------------------------------------------

## 9. SCRIPT HEADERS, AUTHOR, VERSION, AND CHANGELOG

### 9.1 Detailed internal comments

Every important block and section of the script must be commented to explain internal logic.

Comments must be useful, not decorative.

### 9.2 Mandatory header

Every executable script must begin with a structured, readable, immediately understandable header.

For shell scripts, the mandatory reference format is:

```sh
#!/bin/sh
# ==============================================================================
# PATH         : ./script_name.sh
# SCRIPT NAME  : script_name.sh
# AUTHOR       : <AUTHOR>
# EMAIL        : <EMAIL>
# TARGET USAGE : <SHORT_USAGE>
# VERSION      : vX.Y.Z
# DATE         : YYYY-MM-DD HH:MM
# ==============================================================================
# CHANGELOG:
#   vX.Y.Z - YYYY-MM-DD HH:MM - <AUTHOR>
#       Changed:
#       - <CHANGE_1>
#       - <CHANGE_2>
# ==============================================================================
```

The shell-header date must always include the time.

The header must contain at minimum:

- intended or relative script path;
- script name;
- author;
- email;
- target usage or short purpose;
- version;
- date and time;
- append-only internal changelog.

The header must remain readable in the source file.

It must not be an unreadable compact block, minimal comment, or simple version reminder.

### 9.2.1 Mandatory header readability

The header must be organized into clear lines or sections.

It must allow quick identification of:

- script name;
- role;
- author;
- current version;
- date and time;
- complete internal version history.

The internal header changelog must be append-only.

No historical internal-changelog entry may be deleted, rewritten, compressed, or replaced by a summary.

### 9.2.2 Official shell-header reference

Future shell scripts delivered by the assistant must follow the header template above as the primary reference.

Older scripts such as `create_repo.sh` or `syncgit.sh` are no longer the formal header reference.

They may be ignored when their structure differs from the SOLO405 template.

### 9.3 Default author

Use the following values unless explicitly requested otherwise:

```text
Author: <AUTHOR_NAME>
Email : <AUTHOR_EMAIL>
```

### 9.4 Versioning

All generated or modified scripts must be versioned and dated.

The first version should start at `v1.0.0` or `v1.0`.

Every real script modification must increment the version.

Never modify a script without updating together:

- version;
- date;
- internal changelog.

### 9.5 Internal changelog

The script's internal changelog must preserve complete history.

No version may be removed.

No historical entry may be compressed or erased.

Do not add an entry that merely says new SOLO rules were applied.

Every real script change requires:

- internal version increment;
- updated date and time;
- a new append-only internal-changelog entry;
- preservation of all old entries;
- `--changelog` showing the complete changelog.

Recommended internal-entry format:

```md
## vX.Y.Z - YYYY-MM-DD HH:MM - <AUTHOR>
  - ADDED: ...
  - CHANGED: ...
  - FIXED: ...
  - REMOVED: ...
```

Use categories according to the real change.

Do not create empty categories with no value.

### 9.6 Mandatory `--changelog`

Every durable CLI script must include `--changelog` and display the complete script changelog.

Changelog display must use a readable format, ideally Markdown when practical.

`--changelog` must display the complete changelog, preserving all previous versions.

It must never show only an excerpt, partial summary, incomplete header, or latest version only.

During an iteration phase in which the user has paused Markdown updates, the assistant must still maintain the script's internal changelog with every real correction.

### 9.7 Non-shell scripts

Executable scripts in Python, JavaScript, Java, PowerShell, or other languages must carry the same header information.

Only comment syntax changes according to language.

The header must be at the beginning of the file, after the shebang where applicable.

------------------------------------------------------------------------

## 10. MANDATORY CLI BEHAVIOR

### 10.1 Mandatory help

A help block is mandatory for every durable CLI script.

If no argument is provided, the script must display help by default.

### 10.2 Mandatory `--help`

Every durable CLI script must include:

```text
--help
-h
```

No-argument execution must display the same structured help.

Help must be complete, terminal-readable, and organized into sections.

At minimum, help must contain:

- script title;
- version;
- date and time;
- author;
- description;
- usage;
- actions;
- options;
- arguments where applicable;
- default values;
- allowed values;
- clear examples;
- generated files;
- important behavior;
- effects of sensitive options;
- safety notes when applicable.

Help must not be a compact, incomplete, or hard-to-read terminal block.

### 10.2.1 Official terminal-help template

Recommended style:

```text
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  script_name.sh - vX.Y.Z - YYYY-MM-DD HH:MM
  Author : <AUTHOR> <<EMAIL>>
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

DESCRIPTION:
  <description>

USAGE:
  ./script_name.sh [ACTION] [OPTIONS]

ACTIONS:
  --exec,       -exe   ...
  --simulate,   -s     ...
  --prerequis,  -pr    ...
  --install,    -i     ...
  --stop,       -st    ...
  --changelog,  -ch    ...
  --purge,      -pu    ...
  --help,       -h     ...

OPTIONS:
  --option <value>     ...

EXAMPLES:
  ./script_name.sh --simulate
  ./script_name.sh --exec

FILES GENERATED:
  Logs:
    ./logs/log.script_name.sh.<TIMESTAMP>.vX.Y.Z.log
```

Exact section names may be adapted to the script, but minimum content must remain present.

Help must remain terminal-readable and avoid unnecessary line breaks.

### 10.2.2 Help and terminal readability

Help must be designed for direct terminal reading.

Avoid:

- unnecessarily compact lines;
- unnecessary line breaks;
- untitled blocks;
- undocumented options;
- missing examples;
- unexplained sensitive behavior;
- undocumented generated files.

### 10.2.3 Official help reference

The SOLO405 help template is the official reference for future scripts.

Older scripts such as `create_repo.sh` or `syncgit.sh` are no longer the formal help reference and may be ignored if their structure differs from SOLO405.

### 10.2.4 Mandatory validation of no-argument behavior

For every durable CLI script, the assistant must explicitly test no-argument behavior before delivery when real execution is possible in the current environment.

Validation must include at minimum both forms when applicable:

```text
python3 ./script.py
./script.py
```

or the equivalent for the language, shebang, actual script name, and intended execution mode.

Expected no-argument result:

- structured help is displayed;
- main action does not start;
- no business/result files are generated;
- no user files are modified;
- no side effects other than strictly intended logs, when logging applies.

If the script supports `--exec`, main action may start only with `--exec` or another explicitly specified action validated in the specifications.

If the script supports `--simulate`, no-argument execution must not be treated as implicit simulation.

If the script has a default source, current folder, destination, or other default values, those defaults must not trigger the main action when launched without arguments.

The delivery response may state:

```text
No-argument help behavior: OK
```

only if that test was actually executed and validated.

If the test was not executed, state that clearly and do not present the delivery as fully validated.

If no-argument behavior does not display structured help, the delivery is invalid and must be corrected before being presented as compliant.

### 10.3 Mandatory options when applicable

Include these options whenever applicable:

```text
--help       -h    display complete help
--exec       -exe  execute the main action
--stop       -st   stop what the script started, if applicable
--prerequis  -pr   check prerequisites
--install    -i    install missing prerequisites, if applicable
--simulate   -s    run in dry-run mode
--changelog  -ch   display the complete changelog
--purge      -pu   purge runtime artifacts managed by the script, if applicable
```

### 10.4 Default values

Scripts must define default values when arguments are omitted.

Help must display those defaults.

### 10.5 Simulate mode

`--simulate` is off by default.

The presence of `--simulate` enables dry-run mode.

No `true` or `false` value should be required.

`script.sh --simulate` must be valid if the script supports simulation.

`--simulate` must work by itself without requiring `--exec`.

In simulate mode:

- reads allowed;
- analysis allowed;
- logs allowed;
- display allowed;
- sensitive or system modifications prohibited.

### 10.6 Prerequisites

`--prerequis` must list prerequisites and show for each:

- present;
- missing;
- detected version where relevant;
- recommended action if missing.

If a prerequisite is missing, the script must handle the error cleanly and offer `--install` when automated installation is appropriate.

Error messages must show the exact command to run when a fix, retry, or user action is expected.

### 10.7 Automating CLI tools through pipe, here-doc, or stdin

When a script automates a CLI tool through a pipe, here-doc, stdin redirection, or automated stdin writes, the assistant must never assume the tool exits on its own after the primary command.

If the CLI tool has an expected exit command, the script must send it explicitly.

Possible commands, depending on the tool, include:

- `quit`;
- `exit`;
- `bye`;
- another exit command documented by the tool.

The assistant must not invent the exit command.

Select it according to the real tool syntax or information supplied by the user.

When a CLI tool can hang, wait indefinitely, or keep a session open, wrap the call with `timeout` or an equivalent time limit.

If `timeout` fires, the script must clearly show:

- the blocked step;
- the command or logical action involved;
- the return code;
- that the blockage came from a timeout;
- the exact retry or diagnostic action when applicable.

Do not hide a hang behind silent redirection.

Redirects to `/dev/null` must not remove information needed to identify the blocked step, invoked tool, and return code.

Secrets must never be displayed in console or logs, even on timeout or failure.

Diagnostics must remain sufficient to understand where the script is blocked without exposing sensitive values.

Vague messages such as `retry correctly` or `check the configuration` are insufficient when an exact command can be supplied.

#### 10.7.1 Mandatory short rule

When a script drives a CLI tool through stdin, a pipe, or a here-doc, it must explicitly send the tool's expected exit command, such as `quit` or `exit`, and wrap the call with `timeout` when the tool can hang.

Secrets must never be shown, but the blocked step and return code must be visible.

### 10.8 Asynchronous CLI tools, login, sync, and server operations

For asynchronous CLI tools, after login, synchronization, resume, server-operation start, or remote operation, the script must not check state only once immediately and then conclude.

Add a bounded verification loop when final state may take time to appear.

The loop must include:

- a global timeout;
- a maximum number of attempts or clear time limit;
- a reasonable interval between checks;
- display of observed state at each meaningful check;
- explicit handling of transient states.

Examples of transient states when exposed by the tool:

- `login in`;
- `logging in`;
- `resuming`;
- `busy`;
- `syncing`;
- `pending`;
- `connecting`;
- another documented equivalent.

If the final expected state is not reached before the limit, terminate cleanly as a timeout and display:

- the relevant step;
- last observed state;
- available return code;
- exact retry, diagnostic, or manual-check command when known.

Do not hide secrets by replacing diagnostics with empty logs; instead show step names, states, non-sensitive paths, return codes, and diagnostic commands without sensitive values.

### 10.9 Traps for sensitive interactive scripts

For sensitive interactive scripts, add traps when language and environment support them.

At minimum handle:

- `INT`;
- `TERM`;
- `HUP`.

Traps must:

- restore terminal state if echo was disabled;
- clean up temporary files created by the script;
- terminate child processes launched by the script when applicable;
- exit with a coherent return code;
- display a clear message without revealing secrets.

A script that masks sensitive input or drives a blocking tool must not leave the terminal broken after user interruption, session close, or timeout.

------------------------------------------------------------------------

## 11. DISPLAY, LOGS, AND RESULTS

### 11.1 Console display

For every execution, the script must explain steps in clear text.

For a multi-step script, show the current step with its index.

Example:

```text
Disk scan (1/56)
```

### 11.2 Post-execution summary

After execution, display a numbered list of actions performed.

In simulate mode, distinguish simulated actions from actions actually executed.

### 11.3 Logs

Create `./logs` next to the script when necessary.

Detailed logs must be written there.

Recommended log filename:

```text
./logs/log.<script_name>.<full_timestamp>.<script_version>.log
```

### 11.4 Results

Do not create `./results` artificially when the script produces no runtime result file.

If the script truly generates result files, create `./results` next to the script when necessary.

Generated files must have names related to script and version.

Example:

```text
./results/<name>.<script_name>.vX.X.X.txt
```

The result destination must be configurable with `--dest_dir` when the script produces results.

### 11.5 Purge

`--purge` may delete only runtime artifacts explicitly managed by the script.

By default it may target:

- `./logs`;
- `./results`, only when used;
- other runtime directories explicitly documented by the script.

`--purge` must never delete source code, documentation, specifications, secrets, or user files not created by the script.

------------------------------------------------------------------------

## 12. SUDO AND READY-TO-USE BEHAVIOR

### 12.1 Internal sudo

When elevated privileges are necessary, prefer internal `sudo` calls inside the script.

Avoid forcing the user to run:

```text
sudo ./script.sh
```

### 12.2 Zero external sudo where possible

The script should be ready to use with as little manual preparation as possible.

### 12.3 Safety of sensitive actions

Destructive, system, or sensitive actions must be clearly displayed and logged.

They must be disabled in `--simulate` mode.

------------------------------------------------------------------------

## 13. MANDATORY DOCUMENTATION IN REPO MODE

### 13.1 Mandatory root documentation files

In repo mode, the only mandatory documentation files at root are:

```text
./README.md
./CHANGELOG.md
./INSTALL.md
./WHY.md
```

### 13.1.1 Strict naming convention for project Markdown documents

For project or repository Markdown documentation, the filename stem must be uppercase and the `.md` extension lowercase.

Compliant examples:

```text
README.md
CHANGELOG.md
INSTALL.md
WHY.md
SPECIFICATIONS.md
SPECIFICATIONS_FR.md
SPECIFICATIONS_GLOBAL.md
SPECIFICATIONS_GLOBAL_FR.md
MVP.md
ROADMAP.md
IDEAS.md
ARCHITECTURE.md
REMIX.md
```

The assistant must announce and deliver the exact real filename that will be created.

It must not announce `remix.md` if the expected project-document filename is `REMIX.md`.

This rule concerns project-documentation Markdown files, not one-off exports, free-form user files, data files, raw notes, drafts, or files explicitly named differently by the user.

If the user explicitly requests a different name, the explicit user request wins.

### 13.2 Removal of `./infos` logic

SOLO405 removes the `./infos` logic from SOLO200.

Do not automatically create:

```text
./infos/README.md
./infos/CHANGELOG.md
./infos/USAGE.md
./infos/INSTALL.md
./infos/WHY.md
```

Unless explicitly requested, `./infos` is obsolete.

### 13.3 Documentation synchronization

For the first complete project delivery or a stabilized version, any script modification in repo mode must trigger verification and, when needed, update of:

- `./README.md`;
- `./CHANGELOG.md`;
- `./INSTALL.md`;
- `./WHY.md`;
- relevant SPECIFICATIONS files.

During active development, if the user says Markdown documents will be done later, do not regenerate them at every iteration.

In that case, deliver only files strictly modified or needed for the current iteration.

When the user explicitly requests a complete delivery, stabilized version, or final documentation pass, provide synchronized scripts and Markdown documents.

A script task must be declared fully complete only if applicable mandatory documentation is present, current, and consistent with the script, unless the user explicitly postponed documentation to a later final pass.

### 13.4 Append-only `CHANGELOG.md`

`CHANGELOG.md` must preserve complete history.

Never delete old entries.

Never compress history.

Never replace older versions with a summary.

Every new entry must contain at minimum:

- version;
- date;
- time when available;
- author;
- clear list of changes;
- short change context.

### 13.5 Markdown document metadata

Every generated Markdown document must begin with a metadata block before the first heading.

Recommended format:

```md
<!--
Document : <Full document name>
Author : <AUTHOR_NAME>
Email : <AUTHOR_EMAIL>
Version : vX.X.X
Date : YYYY-MM-DD HH:MM
-->
# <Document title>
```

For French documents, `Auteur` may be used instead of `Author` when requested.

### 13.6 `INSTALL.md`

`INSTALL.md` must contain installation instructions, dependencies, prerequisites, and useful checks.

If no special installation is required, say so clearly.

### 13.7 `WHY.md`

`WHY.md` must explain why the script/project exists, the problem solved, main choices, and limitations.

### 13.8 `MVP.md` and MVP framing at project start

When a new scripting project, tool, application, software suite, or technical repository starts, check whether the work should be framed around an MVP.

If the user explicitly mentions an MVP, minimal first version, starting version, testable version, phase 1, or says not to build everything at once, create or propose `MVP.md`.

If the user has not yet specified initial scope, briefly ask whether `MVP.md` should be created unless the current request requires direct action.

`MVP.md` must describe only the first useful minimum project version, without mixing long-term ideas into initial scope.

At minimum it must contain:

- MVP objective;
- problem covered by the MVP;
- included features;
- explicitly excluded features;
- expected inputs;
- expected outputs;
- technical constraints;
- acceptance criteria;
- known limitations;
- relationship to `WHY.md`, `ARCHITECTURE.md`, `ROADMAP.md`, and `SPECIFICATIONS.md`.

Future ideas must remain in `ROADMAP.md`, `IDEAS.md`, `ARCHITECTURE.md`, or global specifications and must not artificially inflate the MVP.

The MVP must remain testable, limited, realistic, and deliverable.

------------------------------------------------------------------------

## 14. LANGUAGE OF RESPONSES AND DELIVERABLES

### 14.1 Chat

Direct conversations with the user are in French by default.

### 14.2 Repository artifacts

Repository artifacts are in English by default.

This includes, in particular:

- scripts;
- comments intended for the repository;
- README;
- CHANGELOG;
- INSTALL;
- WHY;
- SPECIFICATIONS;
- documentation messages.

### 14.3 Mandatory French exceptions

The following files are in French:

- `SPECIFICATIONS_FR.md`;
- `SPECIFICATIONS_GLOBAL_FR.md`.

### 14.4 User exception

If the user explicitly requests French deliverables, follow the request unless it conflicts with a more specific rule.

------------------------------------------------------------------------

## 15. RULES FOR NON-SCRIPT DOCUMENTS AND ARTIFACTS

### 15.1 Standalone Markdown documents

Every delivered documentary Markdown file must start with a readable metadata block.

Mandatory reference format:

```md
<!--
DOCUMENT INFORMATION
Document Name: <DOCUMENT_NAME.md>
Author: <AUTHOR>
Email: <EMAIL>
Version: <VERSION>
Date / Time: YYYY-MM-DD HH:MM
Project: <PROJECT_NAME>
Short description: <SHORT_DESCRIPTION>
-->
```

The date must always include the time.

A standalone `.md` document does not need an internal changelog unless:

- it is repository documentation governed by changelog rules;
- it is a SPECIFICATIONS file;
- the user requests it;
- project context requires it.

Older Markdown-header formats may be replaced by this format when a file is generated or delivered as a new documentary version.

### 15.2 Standalone TXT documents

A standalone `.txt` document must contain a readable metadata block.

Recommended format:

```txt
----- SOLO DOCUMENT METADATA BEGIN -----
Document : <Full document name>
Author : <AUTHOR_NAME>
Email : <AUTHOR_EMAIL>
Version : vX.X.X
Date : YYYY-MM-DD HH:MM
----- SOLO DOCUMENT METADATA END -----
```

### 15.3 DOCX documents

`.docx` documents must not contain a raw script-style technical header.

The first page or cover page must contain at minimum:

- document;
- author;
- email;
- version;
- date and time.

### 15.4 PDF documents

`.pdf` documents follow the same logic as `.docx` documents.

They must have a cover page or visible header with:

- document;
- author;
- email;
- version;
- date and time.

------------------------------------------------------------------------

## 16. VALIDATION, TESTS, AND EVIDENCE

### 16.1 Do not claim testing that was not performed

The assistant must never claim a test was performed when it was not executed.

### 16.2 Distinguish statuses

The assistant must distinguish:

- generated;
- proposed;
- untested;
- tested by static reasoning;
- tested by actual execution;
- to be run by the user;
- impossible to verify in the current context.

### 16.3 Validation commands

When useful, provide ready-to-run validation commands.

If several commands are required, provide them in one Markdown block with comments unless the user requests otherwise.

### 16.4 User report

When a command produces a report intended for the user, prefer a timestamped file such as:

```text
/tmp/output4ChatGPT.YYYY-MM-DD_HHMMSS.md
```

When relevant, plan a final `chown nox:nox` to simplify user access.

When relevant, open the report with Kate at the end.

------------------------------------------------------------------------

## 17. NETWORK AND EXTERNAL-SOURCE RULES

### 17.1 HTTPS only

For repositories, downloads, sources, documentation, and proposed network commands, prefer HTTPS only.

Do not propose HTTP or FTP unless explicitly requested and clearly justified.

### 17.2 No unrequested external access for repository content

Do not suggest sending repository content to external services.

Do not use an external service to analyze, enrich, correct, or validate repository content unless explicitly requested by the user.

### 17.3 Citations and sources

For important technical, security, legal, medical, or factual claims, provide verifiable sources when possible and relevant.

For changing topics, verify information before answering.

------------------------------------------------------------------------

## 18. DEFINITION OF DONE IN REPO MODE

A repo-mode scripting task is complete only if:

- no request for a durable script, versioned feature, or reusable automation was replaced by a one-liner, temporary heredoc, inline block, or disposable procedure unless the user explicitly requested a quick command, temporary test, one-off diagnostic, or quick mode;
- applicable specifications were proposed or updated when necessary;
- user approval was obtained when the specification gate applies;
- the complete script is provided;
- script version is updated;
- script date is updated;
- internal script changelog is updated;
- for a first complete delivery or stabilized version, `README.md`, `CHANGELOG.md`, `INSTALL.md`, `WHY.md`, and relevant SPECIFICATIONS files are checked or updated;
- during an iteration phase where Markdown has been postponed, only strictly modified files are delivered;
- temporary suspension of Markdown updates never suspends maintenance of the internal script changelog;
- secrets are not embedded in code;
- artifacts are delivered as downloads where possible;
- for one modified file, only that file is delivered directly;
- as soon as two or more files form the final delivery, one ZIP containing all final files is mandatory;
- no final answer presents multiple separate download links when a ZIP is required;
- ZIP archives do not contain AGENTS.md, CLAUDE.md, or an instruction symlink explicitly related to them unless explicitly requested;
- no `gitignore_additions_*` file is created;
- no `.gitignore` modification is proposed without requesting the existing `.gitignore` or its template;
- if `.gitignore` must change, a complete merged `.gitignore` is provided only when the user requests it;
- no static validation report is included in the ZIP unless explicitly requested;
- `./.secrets` templates use generic fields where possible;
- empty secrets in `./.secrets` trigger secure runtime input;
- `PASSWORD`, `AUTH_CODE`, `OTP`, `TOKEN`, `API_KEY`, and equivalents are masked, with asterisks where possible, otherwise no terminal echo;
- `--simulate` works by itself without `--exec`;
- CLI automation through pipe, here-doc, or stdin has an explicit exit and a timeout when the tool may hang;
- asynchronous CLI tools have a bounded verification loop after login, sync, or server operation when final state may be delayed;
- transient states such as `login in`, `resuming`, `busy`, `syncing`, or equivalents are displayed and handled when exposed by the tool;
- sensitive interactive scripts use `INT`, `TERM`, and `HUP` traps when supported;
- terminal state is restored after interruption, timeout, or error if the script changed terminal echo;
- useful error messages show the exact command to run;
- no-argument behavior was tested for every durable CLI script when actual execution is possible;
- if no-argument behavior was executed and validated, the delivery response says `No-argument help behavior: OK`;
- if the no-argument test was not executed, that limitation is clearly stated and the delivery is not presented as fully validated;
- validation/execution limitations are clearly stated in chat;
- when a new project starts as an MVP, minimal first version, phase 1, or testable version, `MVP.md` is created or proposed and remains limited to the initial testable scope.

Git workflow remains outside SOLO405 scope and is the user's responsibility.

------------------------------------------------------------------------

## 19. PRIMARY CONTENT ANTI-REGRESSION RULE

### 19.1 Critical priority

Never replace a detailed existing file with a shorter, summarized, condensed, or simplified version unless explicitly requested by the user.

This is a primary SOLO405 rule.

It applies to every delivered, modified, generated, or replaced file in a scripting or repository context, including:

- scripts;
- Markdown files;
- specifications;
- README;
- CHANGELOG;
- INSTALL;
- WHY;
- configuration files;
- secret templates;
- documentation files;
- any other repository artifact.

### 19.2 Prohibition on unrequested condensation

Without an explicit user request, never:

- condense an existing file;
- summarize an existing file;
- remove existing sections;
- remove existing comments;
- remove existing examples;
- remove existing validations;
- remove existing changelog entries;
- replace detailed content with shorter content;
- rewrite a complete file as a simplified version;
- perform a documentation refactor that reduces information;
- reduce functional coverage;
- reduce documentation coverage;
- reduce validation coverage;
- reduce help or example coverage.

Only exception: the user explicitly requests reduction, simplification, summary, compression, cleanup, or deletion.

If the user request is ambiguous, preserve existing content and add changes append-only or by extension rather than reducing it.

### 19.3 Mandatory size gate before delivery

Before delivering a new version of an existing file, compare it with the previous version or user-provided reference when available.

For each modified file, verify:

- byte count does not decrease;
- line count does not decrease;
- changelog does not become shorter;
- existing sections do not disappear;
- existing examples do not disappear;
- existing validations do not disappear;
- existing functions do not disappear;
- existing CLI options do not disappear;
- useful existing comments do not disappear;
- behaviors already validated by the user do not disappear.

If a file is shorter than the previous/reference version without an explicit request for reduction, delivery is invalid.

Correct it before providing the file or ZIP.

### 19.4 Normal growth rule

For a normal incremented version, a modified file should be equal to or greater than the previous version in useful content.

When in doubt, add an append-only section or changelog entry; never delete or summarize existing material.

A real modification should be integrated by extension, conservative targeted replacement, or structured addition, not a condensed rewrite.

### 19.5 Special rule for ZIPs

Before providing a complete ZIP, perform an anti-regression check on all modified files inside when a previous/reference version is available.

Report the validation summary in chat unless the user explicitly requests a report file.

The summary must state:

- files checked;
- old byte count;
- new byte count;
- old line count;
- new line count;
- status OK or FAIL.

If even one file FAILS, do not deliver the ZIP as valid.

Correct it before delivery.

### 19.6 Special rule for specifications

The following files are append-only unless explicitly requested otherwise:

- `SPECIFICATIONS.md`;
- `SPECIFICATIONS_FR.md`;
- `SPECIFICATIONS_GLOBAL.md`;
- `SPECIFICATIONS_GLOBAL_FR.md`.

They must never be replaced by summarized versions.

Every new requirement must be added to the existing structure and internal changelog.

Preserve old requirements, decisions, validations, acceptance criteria, and changelog entries.

### 19.7 Special rule for scripts

An existing script must never be replaced by a shorter script or condensed refactor unless explicitly requested.

Every correction must preserve:

- existing functions;
- existing CLI options;
- existing logs;
- existing validations;
- existing traps;
- useful existing comments;
- complete existing changelog;
- user-validated behavior;
- existing help;
- existing examples;
- existing error handling;
- existing safeguards;
- `--simulate`, `--help`, `--changelog`, `--prerequis`, `--install`, `--purge`, `--stop` modes when they exist or apply.

Every real modification must increment the version, update date/time, and add an append-only changelog entry.

### 19.8 Special rule for documentary Markdown files

An existing documentary Markdown file must never be replaced by a shorter version unless explicitly requested by the user.

Preserve existing sections, examples, explanations, prerequisites, limitations, procedures, safety notes, changelogs, and decisions.

A documentation update must add to, complete, or correct existing content without reducing it.

### 19.9 Special rule for changelogs

All changelogs are append-only unless explicitly requested otherwise.

A new version adds an entry at the top or at the position required by existing structure without deleting or condensing older entries.

If both an external and internal changelog exist, both must remain consistent with the scope of the modification.

### 19.10 Behavior when comparison is impossible

If the assistant does not have the previous/reference version of an existing file, say so clearly.

In that case, avoid a condensed global rewrite.

Produce a complete conservative version based on available content, or request the reference file when exact preservation is necessary.

### 19.16 Mandatory identification of the violated rule

When the user reports a SOLO-compliance error and the assistant acknowledges it, the assistant must always explicitly identify:

- the name of the relevant rule;
- the exact SOLO section number;
- behavior expected by that rule;
- behavior delivered that violated it.

The assistant must not limit itself to `it is in SOLO`, `you are right`, or equivalent generic wording.

Expected format is concrete and verifiable.

Example:

```text
Violated rule: SOLO405 §10.1 - Mandatory help.
Expected: with no argument, the script displays help.
Delivered by mistake: with no argument, the script started execution or another default behavior.
```

This rule complements section `19.15` on factual explanation of rule errors.

------------------------------------------------------------------------

## SOLO405 ADDITION — VISIBLE VERSION IN WIDGETS, EXTENSIONS, AND INTERFACES

### Rule 405.1 — Visible version display in browser widgets and extensions

When the assistant creates, corrects, or modifies a widget, browser extension, Brave/Chrome/Chromium/Firefox extension, WebExtension, userscript, popup, floating panel, embedded UI, or equivalent visual interface, it must provide a visible display of the code version in the user interface.

The displayed version must be visible directly in the main interface area, ideally in the title bar, header, top banner, or another stable location.

Purpose: let the user immediately verify which widget, popup, or UI-code version is actually loaded in the browser.

The displayed version must be synchronized with the version declared in code/project files.

If the project uses a version constant such as `APP_VERSION`, `WIDGET_VERSION`, `VERSION`, `EXTENSION_VERSION`, or equivalent, the interface must display that same value.

If the project contains `manifest.json`, avoid inconsistencies between:
- manifest version;
- version displayed in the interface;
- version in file headers;
- version in README or CHANGELOG.

This applies in particular to:
- floating widget;
- extension popup;
- settings panel;
- overlay;
- export button;
- debug interface;
- voice-to-text interface;
- text-to-voice interface;
- autosend interface;
- local-monitoring interface;
- any test UI delivered with the code.

Recommended format is short and readable, for example:
- `v1.2.3`;
- `Widget v1.2.3`;
- `Export Widget v1.2.3`;
- `AutoSend v1.2.3`.

Do not hide the version only in code, the manifest, console, README, or changelog.

The version may also appear in an About area, but that does not replace the main visible display when the user uses or requests a working widget.

When a widget/extension correction is delivered, verify that the visible version was updated if the code version was incremented.

------------------------------------------------------------------------

## SOLO406 ADDITION — TITLES FOR ACTIVE SCRIPTING, DEV, AND DEBUG CHATS

When a chat is actively used for scripting, development, debugging, a browser extension, UI work, repo workflow, a technical correction, or an ongoing code project, the assistant must propose an active-chat title using the global convention:

```text
000. +++<TYPE>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

Mandatory prefix for a currently used chat:

```text
000. +++
```

Examples:

```text
000. +++SCRIPT_FIREWALL_CTX227_S406_20260630
000. +++EXTBR_VOICECONTROL_DEBUG_20260630
000. +++EXTBR_GPT_EXPORT_#1
000. +++REPO_CREATE_GITIGNORE_S406_20260630
```

The title must be short, visible in ChatGPT search, sortable, and immediately understandable.

Older chats, tests, drafts, archives, or non-current workflows may keep `001.`, `002.`, `003.`, or equivalent.

The assistant must not claim it can rename the chat automatically unless the interface explicitly provides that capability. It must provide a ready-to-copy title.

The title must never contain personal, medical, family, private, sensitive, nominative data, secrets, tokens, private URLs, or sensitive local paths.

This rule complements script versioning rules and does not replace them.

------------------------------------------------------------------------

## SOLO407 ADDITION — REPOSITORY STRUCTURE, ZIP UNDER `.zip/`, AND MANDATORY `.gitignore`

For scripts, workflows, or file generation related to `ai-context-rules`, respect the following canonical structure.

Public `_RULES_SOLO...md` files go at repository root.

Delivery README and CHANGELOG files go under:

```text
.docs/
```

All generated ZIP files go under:

```text
.zip/
```

`.gitignore` must be included with every new version or delivery, even when unchanged.

This is a safeguard against scripts, ZIP extractions, or manual copies that could modify or overwrite exclusions.

Private files using this prefix may remain locally at root:

```text
_RULES_PRIVATE_*
```

They must remain excluded by `.gitignore` and must never be included in a public package.

When a packaging script creates a full export for the repository, the archive must be extract-here ready:

- public RULES at root;
- `README.md` and `.gitignore` at root when provided;
- delivery README/CHANGELOG under `.docs/`;
- single-rule ZIPs and packages under `.zip/`;
- no private content in public packages.

Before announcing a ZIP as delivered, the script or assistant must verify:
- ZIP actually exists;
- internal contents;
- absence of `.private/`, `.old/`, `_RULES_PRIVATE_*` in public packages;
- presence of `.gitignore` in the delivery.

------------------------------------------------------------------------

## 22. SOLO408 ADDITION — HUMAN-READABLE TITLES FOR ACTIVE SCRIPTING AND DEVELOPMENT CHATS

The canonical active scripting/development chat-title format replaces the old `000. +++...` format.

An active scripting, development, extension, debug, technical-documentation, or repository-work chat must use a short, readable, sortable title.

Recommended format:

```text
000. <readable_type> +++<TECH_TYPE>_<PROJECT_OR_SCOPE>_<VERSIONS_OR_CONTEXT>_<YYYYMMDD>
```

`<readable_type>` must appear immediately after `000.`.

Recommended examples:

```text
000. scripting +++SCRIPT_FIREWALL_CTX230_S409_20260726
000. extension +++EXTBR_VOICECONTROL_DEBUG_20260726
000. debug +++SCRIPT_ARCHIVE_SEARCH_CTX230_S409_20260726
000. repo +++PROJECT_REPO_CLEANUP_CTX230_S409_20260726
```

`000.` indicates that the chat is active or prioritized.

`+++` remains the quick-search marker but comes after the readable type.

The assistant must not claim it can rename the chat automatically unless the interface explicitly provides that capability.

The title must never contain a secret, token, sensitive local path, private data, medical data, family data, or non-public information.

This rule does not replace versioning of files, scripts, packages, documents, or deliverables.

------------------------------------------------------------------------

## 23. SOLO408 ADDITION — SOLOLAST LOADING, BYPASS, AND TARGETED SCRIPTING ACTIVATION

For scripting requests, Custom Instructions or startup instructions may automatically load generic SOLO files from GitHub.

The generic public file for this family is:

```text
_RULES_SOLOLAST_SCRIPTING.md
```

This file must be a copy of the latest active scripting-family version.

When a SOLO scripting delivery is produced, provide both:

```text
_RULES_SOLO408_SCRIPTING.md
_RULES_SOLOLAST_SCRIPTING.md
```

The versioned file is for history.

`SOLOLAST` is for stable GitHub-URL loading, especially from Custom Instructions.

If the first message of a new chat contains a clear bypass such as `do not fetch the rules`, `no SOLO at startup`, `no GitHub rules`, `normal chat`, or equivalent, do not automatically load SOLO scripting from GitHub.

This bypass does not permanently disable SOLO scripting. The user may later explicitly request `apply the SOLO scripting rules`, `scripting repo mode`, `simple scripting mode`, `load SOLO scripting`, or equivalent.

When SOLO scripting is activated after bypass, first load general contextualization if it has not already been loaded, then load `_RULES_SOLOLAST_SCRIPTING.md`.

Never claim to have read a GitHub file if the actual read was not performed or access failed.

If the user supplies a newer or higher-priority SOLO scripting file in chat, that supplied file becomes the reference for the current chat.

This rule complements general contextualization and Operator rules without replacing platform system rules or technical limits.

------------------------------------------------------------------------

## 24. SOLO409 ADDITION — FINAL PUBLIC STRUCTURE, NAME-BASED CONFIDENTIALITY, AND README

For scripting work related to `ai-context-rules`, the final public structure recognizes:

```text
AGENTS.md
CLAUDE.md -> AGENTS.md
README.md
_CUSTOM_INSTRUCTIONS.md
_RULES_SOLOxxx_CONTEXTUALIZATION.md
_RULES_SOLOxxx_SCRIPTING.md
_RULES_SOLOxxx_RULESOPERATOR.md
_RULES_SOLOLAST_CONTEXTUALIZATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
AI_STUDYING_FILES/
```

`AI_STUDYING_FILES/` is public when the user confirms that publication is intentional.

The following local folders remain outside normal publication:

```text
.docs/
.old/
.private/
.zip/
.tmp/
```

This generic pattern may be publicly documented as an exclusion:

```text
_RULES_PRIVATE_*
```

Exact real private filenames must not appear in public rules, README, public examples, public packages, or the GitHub remote.

Local private files may remain at root if `_RULES_PRIVATE_*` is present in `.gitignore`.

`.private/` may remain empty.

When active versions, public filenames, or public structure change, synchronize `README.md` in the same delivery.

`chmod 444 .gitignore` may be proposed as local protection after validation, but must not be presented as portable Git protection.

Before final delivery, verify:

- no exact real private filenames in public files;
- `_RULES_PRIVATE_*` is present in `.gitignore`;
- exact alignment of versioned and `SOLOLAST` files;
- README synchronized with active versions;
- ZIPs actually created and contents actually listed.

------------------------------------------------------------------------

## 25. SOLO410 ADDITION — AUTOMATIC SCRIPTING REPO MODE ACTIVATION

`scripting repo` mode must be activated automatically as soon as supplied information demonstrates that an existing repository, versioned project, extension, or application is involved, even without an explicit request for the mode.

Sufficient evidence includes:
- output from `ll`, `ll -R`, `tree`, `find`, or equivalent showing a project tree;
- presence or mention of `.git/`, `.gitignore`, `AGENTS.md`, or `CLAUDE.md`;
- logs for creation, initialization, cloning, commit, push, or another Git operation;
- GitHub, GitLab, or equivalent repository URL;
- presence of `manifest.json`, `package.json`, README, CHANGELOG, source files, or extension/application structure;
- ZIP, archive, or full project file list;
- a request clearly concerning an existing repository.

Repository evidence takes precedence over the absence of the phrase `scripting repo mode`. The assistant must not remain in simple mode when a repository is objectively identified.

------------------------------------------------------------------------

## 26. SOLO410 ADDITION — ABSOLUTE AGENTS.MD AND CLAUDE.MD LOCK

In every repository covered by SOLO scripting:
- never modify `AGENTS.md`;
- never delete, replace, recreate, copy over, or transform `CLAUDE.md`;
- strictly preserve the `CLAUDE.md -> AGENTS.md` symbolic link;
- before and after work, verify that `CLAUDE.md` is still a symlink pointing exactly to `AGENTS.md`;
- before and after work, verify that `AGENTS.md` content and fingerprint are unchanged.

If `CLAUDE.md` is absent, not a symlink, or points elsewhere, only report it. Never repair it automatically.

This prohibition applies regardless of scripting mode, delivery type, ZIP contents, or general synchronization request.

------------------------------------------------------------------------

## 27. SOLO410 ADDITION — PERMANENT ADDITIVE `.gitignore` BASELINE

For all repository work, whatever the active mode, the final `.gitignore` must preserve every existing exclusion and contain at minimum:

```gitignore
.old/
.docs/
.tmp/
.log/
.logs/
.zip/
.tracking_data/
.report/
.reports/
.webactivity_reports/
.exported_activity/
.result/
.results/
logs/
output/
.output/
infos/
.info/
uploads/
creation_log/
certs/
secrets/
.secrets/
.private/
*RULES_PRIVATE*
```

This baseline is additive. Never replace an existing `.gitignore` with an incomplete template or remove an existing exclusion in the name of normalization.

Strictly identical duplicates may be deduplicated without changing pattern scope. Existing variants must be kept when they do not have exactly the same scope.

If the existing `.gitignore` is neither supplied nor accessible, ask for it before producing the final version. Never assume the minimal baseline is the entire existing file.

Before delivery, verify every mandatory entry is present, all older exclusions are preserved, and the delivered `.gitignore` is the one actually used in the relevant ZIPs.

------------------------------------------------------------------------

## 28. SOLO411 ADDITION — MANDATORY PRE-FLIGHT COMPLIANCE GATE

Before creating, modifying, replacing, renaming, moving, packaging, or delivering any file in a context governed by SOLO Scripting, the assistant must perform an explicit pre-flight compliance check against all currently loaded and applicable SOLO rules.

This check is mandatory before any write or delivery. It complements the gates and protections already defined in SOLO, including preservation/non-regression, versioning, size, header/changelog, packaging, `.gitignore`, `AGENTS.md` / `CLAUDE.md` protection, and delivery. It does not create parallel rules where these controls already exist; it turns them into a mandatory execution checklist before action.

The assistant must never rely on memory, usual convention, best practice, or what seems cleaner when a loaded SOLO rule already defines expected behavior.

When relevant, the check must confirm:

- complete preservation of existing features, behaviors, comments, validations, logs, help, examples, CLI options, histories, changelogs, and content;
- no unrequested deletion, condensation, simplification, or reduction;
- correct version increment and date/time update when versioning rules require it;
- compliance with size/comparison gates when applicable;
- compliance with applicable headers, changelogs, and append-only histories;
- strict repository protections, especially `AGENTS.md`, `CLAUDE.md`, and instruction symlinks;
- `.gitignore` changes are additive only: preserve all existing exclusions, remove only strictly identical duplicates when permitted, and add missing mandatory exclusions;
- delivery and packaging mode is respected, including ZIP delivery when applicable rules require it;
- no functional, documentary, validation, or packaging regression.

If even one applicable rule cannot be verified with certainty, before writing or delivering the assistant must:

1. stop the relevant action;
2. reread the relevant rule or reference source;
3. compare old and new file when applicable;
4. correct the discrepancy;
5. repeat the check until compliant.

`The rules were loaded but I did not apply them` is never an acceptable justification. A loaded, applicable SOLO rule is an execution constraint, not a recommendation.

Pre-flight must be repeated for every newly delivered version, even when an earlier version of the same file was already checked. A previous check never automatically validates a new version.

Core rule: **no file governed by SOLO Scripting may be written or delivered before explicit validation of the SOLO rules applicable to the current change.**

------------------------------------------------------------------------

## 29. SOLO412 ADDITION — MANDATORY MULTI-FILE ZIP DELIVERY GATE

This rule formalizes the mandatory final delivery check defined by section `6.2`.

Before every final response containing downloadable artifacts, after all modifications, corrections, and validations, the assistant must perform this gate:

1. count the files that actually compose the final delivery;
2. if total equals `1`, deliver that file directly;
3. if total is `2` or more, verify that a final ZIP exists;
4. open or inspect the ZIP to confirm that it contains exactly the expected final versions;
5. recreate the ZIP if any file was modified after ZIP generation;
6. provide the ZIP as the primary delivery artifact;
7. only after all points pass, send the final response.

A delivery of two or more files without a ZIP is a blocking non-compliance.

Never consider compliant a response that forces several separate downloads when two or more files belong to the same delivery.

Earlier individual links, files already created in chat, or files already displayed do not change this requirement.

This rule is part of the SOLO411 pre-flight and must be checked for every new delivery. It supersedes any older exception that allowed separate delivery of two small files.

Core rule: **1 file = direct delivery; 2 or more files = mandatory ZIP containing every final version.**


------------------------------------------------------------------------

## 30. SOLO413 ADDITION — BLOCKING CANONICAL CLI COMPLIANCE GATE

This section fixes ambiguity between preservation of an existing CLI and the canonical SOLO control interface. It does not create a parallel CLI standard: it clarifies precedence and makes the already-defined CLI requirements executable and blocking.

### 30.1 Canonical control actions and reserved aliases

For every durable CLI script governed by SOLO, the following control options are canonical when applicable:

```text
--help       -h    display complete help
--exec       -exe  authorize real execution of a business action
--simulate   -s    execute the selected business action in dry-run mode
--prerequis  -pr   check prerequisites
--install    -i    install missing prerequisites when automated installation is applicable
--stop       -st   stop runtime activity started by the script when applicable
--changelog  -ch   display the complete changelog
--purge      -pu   purge only runtime artifacts managed by the script when applicable
```

These short aliases are **reserved SOLO control aliases** whenever the corresponding control option applies.

A business-specific option must never reuse a reserved active control alias.

Examples of forbidden collisions when the control option applies:

```text
-i  = --interface     # forbidden if -i is reserved by --install
-s  = --station       # forbidden because -s is reserved by --simulate
-h  = --host          # forbidden because -h is reserved by --help
-pr = business option # forbidden because -pr is reserved by --prerequis
```

Business-specific options keep their long form. If a conflicting legacy short alias exists, the assistant must preserve the business behavior but remove or remap only the conflicting short alias. It must not invent a replacement short alias unless it is unambiguous or explicitly requested.

### 30.2 Explicit precedence over generic preservation rules

When the user requests SOLO-compliant CLI normalization, or when a script is being created/rebuilt under SOLO, this section has priority over the generic "do not rename existing CLI options" preservation rule **only for direct alias conflicts with the canonical SOLO control interface**.

The required priority is:

```text
canonical SOLO control interface
    >
conflicting legacy short alias
    >
generic preservation of that conflicting alias
```

This exception is narrow. It does not authorize removal of business functionality, long option names, behaviors, defaults, output, validation, or non-conflicting CLI options.

Any alias remap caused by this rule must be documented in the script changelog and help.

### 30.3 Canonical business-action invocation

For durable CLI scripts with operational business modes, the canonical real-execution form is:

```text
./script.sh --exec --<business-action> [OPTIONS]
```

Examples:

```text
./script.sh --exec --capture
./script.sh --exec --check
./script.sh --exec --crack --wordlist FILE
./script.sh --exec --sync
./script.sh --exec --scan
```

The business action is an explicit long option such as `--capture`, `--check`, `--crack`, `--scan`, or `--sync`.

Unless the user explicitly requests a positional CLI, the assistant must not silently replace the canonical form with positional business actions such as:

```text
./script.sh CAPTURE
./script.sh CHECK
./script.sh CRACK
./script.sh wlan0 CAPTURE
./script.sh <ACTION> [OPTIONS]
```

The official help template `[ACTION] [OPTIONS]` from older sections must therefore be interpreted as a semantic placeholder, not permission to invent positional action tokens. For SOLO413-compliant business actions, render the help using the real option form:

```text
USAGE:
  ./script.sh --help
  ./script.sh --prerequis
  ./script.sh --install
  ./script.sh --simulate --<business-action> [OPTIONS]
  ./script.sh --exec --<business-action> [OPTIONS]
```

### 30.4 `--exec` and `--simulate` are execution gates, not business actions

`--exec` authorizes real execution but does not by itself identify what business operation to perform.

A script with multiple business actions must require exactly one selected primary business action unless validated specifications explicitly allow combining actions.

Examples:

```text
VALID:
  ./script.sh --exec --capture
  ./script.sh --exec --check
  ./script.sh --simulate --capture

INVALID unless explicitly specified:
  ./script.sh --exec
  ./script.sh --exec --capture --crack
  ./script.sh CAPTURE
```

`--simulate` must continue to work without `--exec`. It selects dry-run execution and must not require real-execution authorization.

### 30.5 Standalone control modes

The following control modes do not require `--exec`:

```text
--help
--changelog
--prerequis
--install
--print-config      # when applicable
--list-*            # informational listing when applicable
```

`--stop` and `--purge` follow their own safety rules and must not be hidden behind an unrelated business action.

No-argument execution still displays help only and performs no business action.

### 30.6 Blocking pre-delivery parser/help compliance test

Before delivering any durable CLI script, the SOLO411 pre-flight must include a CLI compliance gate.

The delivery is BLOCKED until every applicable check passes:

1. no-argument invocation displays structured help and performs no business action;
2. every applicable canonical control long option exists;
3. every applicable canonical reserved short alias exists and maps to the correct control option;
4. no business option reuses an active reserved SOLO short alias;
5. every business action shown in help is accepted by the parser;
6. every business action accepted by the parser is documented in help;
7. real examples use `--exec --<business-action>` rather than positional action tokens;
8. simulation examples use `--simulate --<business-action>` without `--exec`;
9. standalone control modes work without a business action;
10. obsolete positional-action syntax is absent unless explicitly required by validated specifications;
11. `--prerequis` reports prerequisite presence/missing state and version when relevant;
12. `--install` is present when automated prerequisite installation is applicable;
13. `--purge` is present when the script owns disposable runtime artifacts and can safely purge them;
14. `--stop` is present when the script starts persistent/background runtime activity that can be stopped;
15. help, parser, examples, README/COMMANDS documentation, and specifications describe the same CLI;
16. any legacy alias remap caused by SOLO reserved aliases is documented.

If any check fails, the assistant must correct the script before delivery. A syntax-only test such as `bash -n` is never sufficient evidence of CLI compliance.

### 30.7 Mandatory conflict report when a legacy alias collides

When an existing script conflicts with a reserved SOLO alias, the assistant must state the conflict factually before changing it.

Required format:

```text
CLI conflict found: YES
Reserved SOLO alias: -i -> --install
Legacy use: -i -> --interface
Resolution: preserve --interface, remove/remap only the conflicting short alias
Business behavior removed: NO
```

This report may be concise, but the conflict must not be silently ignored.

### 30.8 Mandatory CLI inventory before code changes

Before modifying an existing durable CLI script, the assistant must inventory the existing interface from the actual source/help/specifications available in the current task.

At minimum, identify:

- control options;
- business-action selectors;
- business options;
- short aliases;
- positional arguments;
- defaults;
- mutually exclusive combinations;
- required combinations;
- deprecated syntax;
- no-argument behavior.

The assistant must compare this inventory against the canonical SOLO control interface before writing code.

This prevents patch-by-patch drift where a local fix accidentally removes or reassigns existing arguments.

### 30.9 Loaded-rule application is mandatory

A successful remote read of SOLO rules is not proof of compliance.

After the rules are loaded, the assistant must apply them to the actual parser, help, examples, and delivered code.

Repeatedly rereading the rules without correcting an already-identified violation is itself a workflow failure.

When the current loaded version is known and no explicit reload/refresh is requested, do not reread the same SOLO file merely because the user mentions "scripting", asks why a rule was not followed, or continues the same scripting task. Apply the already-loaded rules.

### 30.10 Core SOLO413 rule

**For durable SOLO CLI scripts: control aliases are reserved, business actions use explicit long options, real execution uses `--exec --<action>`, simulation uses `--simulate --<action>`, positional action syntax is forbidden unless explicitly requested, and delivery is blocked until parser/help/example compliance is verified.**
