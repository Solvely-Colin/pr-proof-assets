# OpenClaw PR 132689 exact-head evidence

Evidence for stacked OpenClaw head
`907a7f561959ae280c0b95f47e794767d8c921ce` on parent
`814e0bac9d5e872e4fc388e122b736d1feb40dab`.

`exact-head-validation.log` records:

- native localization inventory verification with 4,406 entries and no drift;
- exact parent Gateway authority and steering checks;
- qualified/unqualified model-selection matching;
- a legacy NULL settings row fenced before claim or retry;
- candidate-to-older-reader-to-candidate database reopen and claim fencing;
- old-Gateway structured replay parking terminally without a retry or health loop;
- a full generic iOS Simulator build ending in `BUILD SUCCEEDED`.

The log is redacted for local paths. Its provider and transport surfaces are deterministic
fixtures; it is not presented as a live external-provider run.
