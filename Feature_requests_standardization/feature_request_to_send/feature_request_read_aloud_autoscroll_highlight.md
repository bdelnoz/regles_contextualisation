# Feature Request: Read Aloud Auto-Scroll and Text Highlighting

## Title

Improve ChatGPT Web Read Aloud with auto-scroll and live text highlighting.

## Summary

The current Read Aloud behavior in ChatGPT Web is difficult to follow during long answers. When ChatGPT reads a response aloud, the page does not reliably scroll along with the spoken text, and the currently spoken sentence or paragraph is not highlighted.

Please improve Read Aloud so that it works more like dedicated browser read-aloud extensions: auto-scroll the response and visually highlight the text currently being spoken.

## Current behavior

When the user clicks the Read Aloud button on a ChatGPT response:

- ChatGPT reads the message aloud.
- The chat view does not clearly follow the spoken position.
- The current sentence or paragraph is not highlighted.
- The user must manually scroll to find where the voice currently is.
- For long technical responses, this makes the feature hard to use.

In some cases, when code is present, the experience is also poor because the reader may skip or summarize code instead of making it clear how code blocks are handled.

## Requested behavior

When Read Aloud is active:

1. Automatically scroll the chat response as the audio progresses.
2. Highlight the sentence, paragraph, or block currently being read.
3. Keep the highlighted text visible in the viewport.
4. Provide a clear visual indicator of reading progress.
5. Handle code blocks more predictably.

## Proposed interaction

When the user clicks Read Aloud:

```text
Start reading -> Highlight current sentence/paragraph -> Auto-scroll as reading progresses
```

The user should be able to pause, resume, or stop reading without losing the current position.

## Code block handling

For code blocks, ChatGPT Web should offer a clear behavior, for example:

- Read code normally.
- Skip code blocks.
- Summarize code blocks.
- Announce: “Code block skipped” or “Code block available in the chat.”

The key point is that the behavior should be explicit and controllable, not confusing.

## Why this matters

Read Aloud is useful for accessibility, fatigue, multitasking, and reviewing long technical answers. Without auto-scroll and highlighting, the user has to manually track the spoken position, which defeats much of the benefit.

Dedicated browser Read Aloud extensions already provide this kind of side-window or highlighting behavior. ChatGPT Web should provide a comparable native experience.

## Acceptance criteria

- Read Aloud auto-scrolls the current ChatGPT response.
- The currently spoken sentence, paragraph, or block is highlighted.
- The highlighted text remains visible while reading progresses.
- The user can pause, resume, and stop reading.
- Reading progress remains understandable in long responses.
- Code block behavior is explicit and configurable.
- The feature works on desktop ChatGPT Web.
- The feature improves accessibility and reduces manual scrolling.

## User impact

This would make Read Aloud practical for long answers, technical explanations, accessibility workflows, and users who prefer listening while following visually.
