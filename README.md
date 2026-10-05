# SOLO Rules — Contextualisation, Scripting & Operator

Repository containing the public SOLO rule set used with ChatGPT.

## Current public baseline

```text
CTX236 / SCRIPT417 / OP128
```

The public working baseline uses these files:

```text
.gitignore
CHANGELOG.md
README.md
_CUSTOM_INSTRUCTIONS.md
_RULES_SOLO236_CONTEXTUALISATION.md
_RULES_SOLO417_SCRIPTING.md
_RULES_SOLO128_RULESOPERATOR.md
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
```

## `_CUSTOM_INSTRUCTIONS.md`

This file contains the text to place in the **ChatGPT account Personalization / Custom Instructions section**.

Its purpose is to tell ChatGPT how to load and use the SOLO rules.

In particular, it defines:

- the public RAW URLs used to read the current SOLO rules;
- automatic loading of the general Contextualisation rules at the start of a new chat, unless explicitly bypassed;
- activation of Scripting only when requested or when the chat clearly becomes a scripting/repository task;
- activation of Operator only when explicitly requested;
- idempotent loading inside the same chat, so already-loaded rule families are not repeatedly fetched;
- explicit reload behavior when the user asks to reload or reapply the rules.

`_CUSTOM_INSTRUCTIONS.md` is therefore **not a rule family itself**. It is the configuration text used in ChatGPT Personalization to tell ChatGPT when and how to load the SOLO rule families.

## Contextualisation — CTX236

Active file:

```text
_RULES_SOLO236_CONTEXTUALISATION.md
```

Stable alias:

```text
_RULES_SOLOLAST_CONTEXTUALISATION.md
```

The Contextualisation file is the **general SOLO rule set**.

It defines the default behavior of ChatGPT for normal conversations and contains the global rules that apply across chats.

It covers, among other things:

- response style and directness;
- preservation of context already established in the chat;
- anti-repetition and anti-loop behavior;
- Read Aloud behavior;
- voice/text interaction rules;
- reporting and technical investigation behavior;
- handling of long chats and continuity;
- general public modes and interaction rules;
- public/private separation principles.

CTX is the general foundation. Specialized behavior that does not need to be part of the global public rules can be externalized into separate private modules.

## Scripting — SCRIPT417

Active file:

```text
_RULES_SOLO417_SCRIPTING.md
```

Stable alias:

```text
_RULES_SOLOLAST_SCRIPTING.md
```

The Scripting file contains the rules used when working on:

- scripts;
- source code;
- repositories;
- browser extensions;
- applications;
- debugging;
- command-line tools;
- technical documentation related to code;
- versioning and delivery of code artifacts.

Its purpose is to make scripting work reproducible and safe.

It defines rules for areas such as:

- repository handling;
- preserving existing functionality;
- anti-regression checks;
- versioning;
- changelogs;
- testing;
- CLI behavior;
- stdout/stderr handling;
- documentation;
- ZIP delivery;
- file naming;
- Git hygiene;
- secrets and sensitive files;
- validation before delivery.

Scripting is **not loaded for every normal chat**. It is added when the conversation actually concerns scripting/code/repository work or when the user explicitly activates it.

## Operator — OP128

Active file:

```text
_RULES_SOLO128_RULESOPERATOR.md
```

Stable alias:

```text
_RULES_SOLOLAST_RULESOPERATOR.md
```

The Operator file contains the rules used to **maintain the SOLO rules themselves**.

Operator is used when creating, correcting, restructuring, versioning or packaging Contextualisation, Scripting, Operator or related SOLO rule files.

Its purpose is to prevent careless rule changes and uncontrolled duplication.

It defines rules for:

- checking whether an existing rule already covers a reported problem;
- deciding whether the real issue is a missing rule, a vague rule, a rule not applied, or a misinterpretation;
- proposing the smallest useful correction;
- waiting for GO when required;
- incrementing versions correctly;
- preserving unchanged rule families;
- updating the matching `SOLOLAST` aliases;
- validating packages before delivery;
- maintaining changelogs and manifests;
- identifying files that must be moved to `.old/`;
- preventing private-rule leakage into public packages;
- maintaining consistency between the active CTX / SCRIPT / OP versions.

Operator is **not loaded for normal use**. It is activated when the user explicitly works on the SOLO rules themselves.

## `SOLOLAST` files

The three stable aliases are:

```text
_RULES_SOLOLAST_CONTEXTUALISATION.md
_RULES_SOLOLAST_SCRIPTING.md
_RULES_SOLOLAST_RULESOPERATOR.md
```

They always represent the currently active public versions.

For the present baseline:

```text
_RULES_SOLOLAST_CONTEXTUALISATION.md = CTX236
_RULES_SOLOLAST_SCRIPTING.md        = SCRIPT417
_RULES_SOLOLAST_RULESOPERATOR.md    = OP128
```

The versioned files provide traceability. The `SOLOLAST` files provide stable filenames and stable RAW URLs for the Custom Instructions.

---

Current public baseline:

```text
CTX236 / SCRIPT417 / OP128
```
