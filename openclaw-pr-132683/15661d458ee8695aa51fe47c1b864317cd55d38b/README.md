# OpenClaw PR 132683 final-head manifest

Final OpenClaw head: `15661d458ee8695aa51fe47c1b864317cd55d38b`.

The full UI video, contact sheet, authority suites, and SQLite proof remain in the
[runtime-equivalent bundle](../eb19e297d4ab35a82dc8b9aeffa0dc5f9ad8c0c6/README.md).
The final commit is a net-negative dead-code cleanup: it removes unused shared API and
moves a retained synchronization helper from production into the test target.

`final-head-validation.log` records native i18n, the full unused-export guard, complete
Swift test discovery/compilation, and diff checks at this final head. The generic iOS
Simulator build also passed after the cleanup.
