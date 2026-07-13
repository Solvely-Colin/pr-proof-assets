# PR 72 admin message delete proof

Generated against local ClickClack server http://127.0.0.1:18083. User IDs and message IDs are omitted from screenshots.

- 01-author-self-delete.png: author deletes own channel message through browser-origin DELETE; app shows deleted marker.
- 02-owner-channel-delete.png: workspace owner deletes another member channel message through browser-origin DELETE; app shows deleted marker.
- 03-moderator-blocked.png: moderator cannot delete another member channel message; browser DELETE returns 403.
- 04-member-blocked.png: member cannot delete another member channel message; browser DELETE returns 403.
- 05-owner-dm-denied.png: workspace owner cannot delete a DM message they did not author; browser DELETE returns 403.
