---
title: Mission Offsets
---

## Information

* All offsets are for files from the official 1.1 patch.
* Numbers are in hexadecimal, or suffixed to indicate their type:

| Suffix | Type    | Size                 |
| ------ | ------- | -------------------- |
| f      | float   | 4 bytes              |
| d      | double  | 8 bytes              |
| i      | integer | 4 bytes              |
| b      | byte    | 1 byte (-128 to 127) |

A value like "0F 85 -> 90 E9" means replace the original bytes on the left with the new bytes on the right. (The bytes are given in file order, they don't represent a number like the offset.)

### Scripted Missions

| Default Value  | File        | Offset | By    | Description                                                                      |
| -------------- | ----------- | ------ | ----- | -------------------------------------------------------------------------------- |
| 74 -> EB       | server.dll  | 03A03E | M0tah | Bypass mission check on player invite (beware, may bug up RandomMissions).       |
| 74 -> EB       | server.dll  | 03A438 | M0tah | Remove mission check on group invite accept (beware, may bug up RandomMissions). |
| 75 17 -> EB 0E | content.dll | 019A59 | M0tah | Prevent mission failures due to attacking a neutral/friendly object.             |

### Random Missions

| Default Value                                                                                                                                                                                                                                          | File        | Offset | By    | Description                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | ------ | ----- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 34 -> 00                                                                                                                                                                                                                                               | content.dll | 0518C7 | adoxa | Allow fc_n_grp for randommissions (Part 1).                                                                                                                                                      |
| 34 -> 00                                                                                                                                                                                                                                               | content.dll | 0519B7 | adoxa | Allow fc_n_grp for randommissions (Part 2).                                                                                                                                                      |
| 2500f                                                                                                                                                                                                                                                  | content.dll | 11C2C4 | Vital | Distance at which NPC mission target ships in randommissions are created.                                                                                                                        |
| 2625f                                                                                                                                                                                                                                                  | content.dll | 0F17D9 | Vital | Distance at which NPC wave ships in randommissions are created.                                                                                                                                  |
| 7500f                                                                                                                                                                                                                                                  | content.dll | 11C2B0 | Vital | Distance at which mission target solars in randommissions are created.                                                                                                                           |
| 6000f                                                                                                                                                                                                                                                  | content.dll | 11CBCC | Vital | Distance from 1st mission waypoint that second waypoint (and ships at it) in randommissions are created.                                                                                         |
| 3500f                                                                                                                                                                                                                                                  | content.dll | 11C2C8 | Vital | Core retreat distance from randommission waypoint, modified by below offset.                                                                                                                     |
| 250f                                                                                                                                                                                                                                                   | content.dll | 11CAB4 | Vital | Amount to add to the core retreat distance (above) to work out a real retreat distance, and amount to subtract from the core retreat distance (above) to work out a real back-in-range distance. |
| 2000f                                                                                                                                                                                                                                                  | content.dll | 11C2CC | Vital | Max range at which randommission NPCs will engage enemies; outside of this range, their behavior will be strange (fly around in circles, ignore fire, etc).                                      |
| 300f                                                                                                                                                                                                                                                   | content.dll | 117608 | adoxa | Multiplier for zone distance; increase to allow randommissions further from base.                                                                                                                |
| 30f                                                                                                                                                                                                                                                    | content.dll | 12E778 | adoxa | Return to battle time (SP).                                                                                                                                                                      |
| 45f                                                                                                                                                                                                                                                    | content.dll | 11C2DC | adoxa | Return to battle time (MP).                                                                                                                                                                      |
| 5f                                                                                                                                                                                                                                                     | content.dll | 0ECED5 | adoxa | Return to battle update interval.                                                                                                                                                                |
| 89 44 E4 04 D9 44 E4 20 D8 64 E4 1C EB 04 66 B8 FB 06 DB 44 E4 04 D8 0D D0 97 39 06 DE C9 D8 44 E4 1C 5E 83 C4 10 C3<br />-><br />99 B9 03 00 00 00 F7 F9 85 D2 74 33 D9 05 30 B2 FB 06 DD 5C 24 04 FF D6 99 DD 44 24 04 B9 03 00 00 00 F7 F9 8D 54 12 | content.dll | 0AAD7A | adoxa | Make MP job difficulty exactly between min and max difficulty in [mbases.ini](../../ini-editing/hardcoded-inis/data/missions/mbases.ini.md).                                                   |
| FF10 -> 9090                                                                                                                                                                                                                                             | common.dll  | 0995B6 | adoxa | disable `ArchDB::Get` random mission spew warning. (Part 1)                                                                                                                                      |
| FF10 -> 9090                                                                                                                                                                                                                                             | common.dll  | 0995FC | adoxa | disable `ArchDB::Get` random mission spew warning. (Part 2)                                                                                                                                      |