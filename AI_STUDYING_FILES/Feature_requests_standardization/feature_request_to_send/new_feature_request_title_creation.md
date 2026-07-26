# Feature Request: Voice Transcription Auto-Send Toggle

## Title

Add an Auto-Send Yes/No toggle for voice transcription input in ChatGPT Web.

## Summary

When using voice transcription in ChatGPT Web, the current flow requires the user to click once to stop or validate transcription, then click again to send the message. This creates unnecessary friction, especially for users who dictate many messages in a row.

Please add a simple **Auto-Send: Yes/No** toggle for voice-to-text transcription.

## Current behavior

When the user records or dictates a message:

1. The user starts voice input.
2. The user validates or stops the transcription.
3. The transcribed text is inserted into the message box.
4. The user must manually click Send or press Enter again.

This is annoying in fast voice workflows because the user already gave a clear intent by validating the transcription.

## Requested behavior

Add an option near the voice transcription interface:

```text
Auto-Send: Yes / No
```

### If Auto-Send is enabled

After the user validates the voice transcription, ChatGPT should automatically send the transcribed message.

Flow:

```text
Record voice -> Validate transcription -> Message is sent automatically
```

### If Auto-Send is disabled

After the user validates the transcription, ChatGPT should only insert the text into the input box, allowing the user to edit it, add more text, or decide manually when to send.

Flow:

```text
Record voice -> Validate transcription -> Text stays in input box
```

## Why this matters

Voice transcription is often used when the user wants to reduce keyboard and mouse interactions. Requiring an extra click after validating transcription partially defeats the purpose.

This is especially frustrating for long technical conversations, accessibility workflows, tired users, and users who dictate many short corrections or follow-up messages.

## Proposed UI

A small persistent toggle near the voice input controls:

```text
Auto-Send: On / Off
```

or:

```text
Send after transcription: Yes / No
```

The setting should persist across the session, and ideally across ChatGPT Web sessions.

## Acceptance criteria

- The user can enable or disable automatic sending after voice transcription.
- When enabled, validating transcription sends the message immediately.
- When disabled, validating transcription only inserts text into the input field.
- The setting is visible and easy to change.
- The setting persists at least during the current browser session.
- The feature works consistently on desktop ChatGPT Web.
- The behavior does not affect normal typed messages.

## User impact

This would remove repeated unnecessary clicks, improve voice-first workflows, and make ChatGPT Web significantly more comfortable for users who rely heavily on dictation.
