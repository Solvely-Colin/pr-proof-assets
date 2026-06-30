# OpenClaw PR 98023 iOS Chat Return Proof

Proof for https://github.com/openclaw/openclaw/pull/98023.

## Artifact Files

- `activity-chat-return.gif` - simulator GIF proof.
- `activity-chat-return.mp4` - simulator MP4 proof.
- `activity-chat-return-contact.png` - contact sheet sampled from the recording.

## Scenario

Captured on the iPhone 17 simulator using the OpenClaw iOS screenshot fixture:

```sh
--openclaw-screenshot-mode --openclaw-initial-tab control --openclaw-initial-destination activity
```

The recording starts on the Activity Control detail, taps `Chat`, shows the Chat screen with the contextual return affordance, taps the affordance, and lands back on Activity.

Runtime snapshot targets from the same flow:

- Before: `e53|tap|button|Chat`.
- Chat: `e18|tap|button|Back to Activity||OpenClawChatBackToControlDetailButton`.
- After return: Activity screen restored with Control selected.

Sessions-specific behavior uses the same implementation path. The local screenshot fixture only exposes the default `main` chat, and the app filters that out of recent sessions, so there is no non-default session row to tap in this fixture recording.
