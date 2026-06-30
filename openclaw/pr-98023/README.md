# OpenClaw PR 98023 iOS Chat Return Proof

Proof for https://github.com/openclaw/openclaw/pull/98023.

## Artifact Files

- `activity-chat-return.gif` - simulator GIF proof.
- `activity-chat-return.mp4` - simulator MP4 proof.
- `activity-chat-return-contact.png` - contact sheet sampled from the recording.
- `control-tab-root-chat-back.gif` - corrected simulator GIF proof for Control-tab root reset plus Chat detail back.
- `control-tab-root-chat-back.mp4` - corrected simulator MP4 proof.
- `control-tab-root-chat-back-contact.png` - contact sheet sampled from the corrected recording.

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

The corrected `control-tab-root-chat-back` recording covers the follow-up UX requirement:

1. Activity detail -> detail-level `Chat` button shows Chat with `Back to Activity`.
2. Tapping the bottom `Control` tab from Chat lands on the main Control hub, not the Activity detail.
3. Opening Activity again, tapping the detail-level `Chat` button, then tapping `Back to Activity` returns one level to the Activity detail.

Runtime snapshot targets from the corrected flow:

- Activity detail: `e53|tap|button|Chat`.
- Chat return affordance: `e18|tap|button|Back to Activity||OpenClawChatBackToControlDetailButton`.
- Control tab: `e47|tap|tab|Control|0|`.
- Main Control hub row: `e53|tap|button|Activity, Gateway, session, and device activity.`
- Final return: Activity screen restored with Control selected.

Sessions-specific behavior uses the same implementation path. The local screenshot fixture only exposes the default `main` chat, and the app filters that out of recent sessions, so there is no non-default session row to tap in this fixture recording.
