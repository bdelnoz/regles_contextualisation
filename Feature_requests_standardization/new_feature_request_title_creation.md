# New Feature Request Title Creation Prompt

Use this prompt inside any existing feature request chat when you want to extract either:

- the best title for the current chat, if it contains one feature request;
- or multiple clean, ready-to-paste feature request blocks if the chat contains several independent feature requests.

## Prompt to copy

```text
Analyze this entire conversation as a feature request chat.

Your job:
Determine whether this conversation contains one single feature request or several distinct feature requests.

Definition:
A feature request is a request for a new product feature, UI or UX improvement, setting, option, workflow, behavior change, automation, notification behavior, project behavior, chat behavior, or export/import improvement.

Decision rules:
- If all requests concern the same central product problem, merge them into one feature request.
- If the conversation contains several independent product problems or requested behaviors, split them.
- Do not force one generic title when several independent feature requests are present.
- Be strict: if one chat should realistically become several clean feature request chats, say so.

Title rules:
- Titles must be in English.
- Maximum 5 words.
- No “ChatGPT” in the title unless strictly necessary.
- No useless punctuation.
- The title must describe the requested feature, not the surrounding discussion.
- The title must be directly usable as the title of the new chat.

CASE 1 — Single feature request:

Respond with exactly one markdown block and nothing else.

The block must be ready to paste into a new project chat if needed.

Required output format:

```markdown
# <Short English Title>

Use this title for this chat:
<Short English Title>

## Feature request

<Clear and complete description of the requested feature in English.>

## Problem

<The user problem solved by this feature.>

## Expected behavior

<Clear, actionable expected product behavior.>

## Notes from original chat

<Only useful context from the original conversation. No filler.>
```

CASE 2 — Multiple feature requests:

First write exactly:

Multiple feature requests detected.
Number of feature requests detected: <N>

Then provide one separate markdown block per feature request.

Each markdown block must be directly ready to paste into a new project chat.

Each block must already contain the correct final title for that new chat.

Required output format for each feature request:

```markdown
# <Short English Title>

Use this title for the new chat:
<Short English Title>

## Feature request

<Clear and complete description of this specific requested feature in English.>

## Problem

<The user problem solved by this feature.>

## Expected behavior

<Clear, actionable expected product behavior.>

## Notes from original chat

<Only useful context from the original conversation. No filler.>
```

Hard constraints:
- Do not use tables.
- Do not mix several feature requests in the same block.
- Do not add explanations outside the required output.
- Do not invent product behavior not present in the original conversation.
- Each block must be self-contained.
- Each block must be usable directly in a new chat of the same project.
- Each block must include the exact title to use for that new chat.
- If there are multiple feature requests, the current chat should not receive a single title; it should be split.
```
