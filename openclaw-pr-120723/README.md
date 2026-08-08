# OpenClaw PR 120723 — iOS composer keyboard proof

Source head: `462270da87e`

Device: iPhone 17 Pro simulator, iOS 26.2 (`23C54`)

Both images come from `OpenClawSnapshotUITests.testChatComposerReturnInsertsNewlineWithoutSending`:

- `before-mic-only-no-keyboard.png`: current `main` fails after tapping the composer; no software keyboard appears and the empty-draft mic remains visible.
- `after-keyboard-and-send.png`: the PR head accepts a multiline draft, retains the software keyboard, and replaces the mic with Send.

SHA-256:

```text
f35641576b6a732681c1687c58a9588b7dad35a6a414cc1888ef3423e68067df  before-mic-only-no-keyboard.png
6cd7fb84fbc5910c986b16d24f6a2f6d2177e136e5c8739e269ce0ba9e000909  after-keyboard-and-send.png
```
