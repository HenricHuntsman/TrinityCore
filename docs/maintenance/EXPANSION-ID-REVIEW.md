# Expansion ID correction — 18 October 2026

The earlier Legion Remix patch inserted an event as expansion ID 7 and shifted Battle for Azeroth, Shadowlands, Dragonflight and The War Within. This disagrees with the upstream expansion mapping and can misinterpret numeric expansion values. The patch's numeric compatibility claim was unsupported.

Restored the existing branch's canonical values: BFA 7, Shadowlands 8, Dragonflight 9, The War Within 10. Removed the invented standalone Legion Remix expansion constant and its level case. Representing Remix as an event requires a separate design; no replacement event system is implemented here. The previous patch is preserved in legacy-legion-remix.patch and Git history.

Validation: a C++17 syntax-only harness compiled the actual enum and level function with static assertions for these IDs and The War Within maximum level 80. The current upstream version was separately checked for Midnight ID 11 / level 90. This is a targeted contract check, not a full TrinityCore build, database migration or game-server runtime test.

The fork was 1,542 upstream commits behind at review time. Full upstream synchronisation remains a separate candidate and must retain this note.
