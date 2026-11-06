# The first five

This is the whole project until a dead node can say why it stopped.

Places are not chosen. Boards are not bought. One person pays for the travel and the parts. There is no funder. The nodes stay outside until they die. The result is the diary, not a press release.

## Roles

- **N01** reads the river. It does not raise an alert on its own.
- **N02** reads it again. A surge is an alert only after both agree, so debris on one sensor is not a flood.
- **N03** is a radio on a ridge. No sensor. It stores frames and forwards them. If N02 is silent, N01 addresses N03 directly, slower.
- **N04** keeps the log and originates network time. A laptop is enough while a person is there. After that, the flash on the node is the record. Starlink or cellular, if it exists, is a copy of that record. The alarm does not wait for it.
- **N05** is the end of the valley. On the first five this is a buzzer and a log. A siren stays off unless a person who lives there asks for it.

## What has to be true of the box

- **Power.** LiFePO4 and a small panel. A power bank is a weekend, not a season. Five watts of panel is a target, not a part that has been bought.
- **Place.** Above the flood. The sensor looks at the water.
- **Box.** Gasket and screws. Not potted. A dead node that cannot be opened teaches nothing.
- **Diary.** The last heartbeats stay in flash: voltage, time awake, and why it last restarted.

## Before they are left

1. A bucket at N01 reaches N05 with no phone in the path.
2. Pull the battery on N02. The frame still arrives, the long way, and the missing node is noted.
3. A laminated note on the box, in the language spoken there: what it is, that it is not a bomb, and how to reach the person who left it. That language is not chosen yet.
4. A siren only if a person who sleeps near it asks for the sound.

## Radio

Packets are meant to ride on [MeshCore](https://github.com/meshcore-dev/MeshCore). How N01–N05 map onto MeshCore's companion, repeater, and sensor roles is still open. The 12-byte flood frame is a separate draft: [frame.md](frame.md).

## Repair rules, not facts about a built unit

- Keyed connectors so the panel plug cannot seat in the sensor socket. Blue for level and rain, amber for the panel, red for the pack. The connector itself is not chosen.
- A swap should not need a compiler. The first firmware may be dumber than that. If a swap needs a laptop, the rule has failed.
- One button, no screen. Green: leave it. Amber: pack. Blue: sensor lead. Red: radio.
- A picture drawing in the lid, so the instructions are not a language.

The household watch (solar, one button, no screen, LTO cell, potted) is a later idea. It is not one of the five.
