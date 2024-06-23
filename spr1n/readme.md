# spr1n Timer - Information and Installation Guide (v1 and v1-d)

## Introduction

This timer is based on Sadpuppy's timer idea (sprite digits usage and game_counter toggle method with cycle),
tho its pretty diferent and has many advantages. I discovered that Sadpuppy's timer has pretty nice system
and started this project (~a year ago), but due to a lot of bugs stopped. Few months ago finished with stable
versions and today just adjusted some few last things (had no much time/motivation to complete it faster).
The aim was to make certain timer with decimal and less entities comparing to kreedz timer (it was a long
before XJ started to use decimals). Even its not that important now with the current situation on XJ, the aim
was reached , and I belive such timer can be useful for some fast/short maps or in case you want to save
entities.

## Description

The timer consists of the following parts:
1. **Start Button** (target and master must not be changed)
2. **Stop Button** (target and master must not be changed)
3. **Group of 1XX Entities** (do not change)
4. **Box for Digits** (feel free to edit it)
5. **Digits (Group of Sprites)** (do not edit unless you know what you are doing)

> **Note:** Since the timer uses sprites as digits, you cannot rotate the timer with the Transformation tool. New angles should be set for all sprites.

### Accuracy and Compatibility
- **Timer accuracy:** ~0.01 seconds
- **Known issue:** Timer bug may appear with low FPS (<10-20)
- **Compatibility:** Not compatible with kreedz and Sadpuppy's timers on the same map

## Comparison

| Timer              | Precache | Entities | Timerbug |
|--------------------|----------|----------|----------|
| **spr1n timer v1-d [59:59.9]** | 13/512 (2.5%) | 219 (5.3%) | @low fps, better than kreedz timer |
| **spr1n timer v1 [59:59]**    | 13/512 (2.5%) | 173 (4.4%) | High uptime, less than kreedz timer |
| **kreedz timer [59:59]**      | 39/512 (7.6%) | 236 (7.9%) | Uncertain digit change, random bugs |
| **Sadpuppy timer [3:59:59]**  | 14/512 (2.7%) | 159 (4.3%) | Constant delays due to system architecture |

## Files

- **spr1n_timer_v1-d.rar:** Timer with decimal [59:59.9]
- **spr1n_timer_v1.rar:** Timer without decimal [59:59]

**Sprite Directories:**
- Top digits (old style): `sprites\spr1n\digits\kzold\`
- Middle digits: `sprites\spr1n\digits\kznum\`
- Bottom (white): `sprites\spr1n\digits\kzblt\`

> **NB!** Do not modify these files.

## Installation

### Buttons
1. Copy both buttons to your map. They use standard textures from `timecounter.wad`.
2. If you want to use your own buttons, copy the "target" and "master" key values to them.

### Entities
1. Copy the group of 1XX entities (timer engine) to your map. Place them near the timer digits.

### Timer Digits
1. Choose a timer layout that suits your map. This layout consists of a box and digit-sprites.
2. If you want to remove the box or have your own layout, ungroup the object, remove the box, select sprites, and move them as needed.

### Files
1. Include the relevant sprite files in your map according to the digits you use.

> **NB!** To avoid unexpected bugs, compile your map without VIS and RAD to verify the timer's functionality.

## Quick Comparison

**Advantages of spr1n timer:**
- Saves precache resources
- Has decimal precision
- Less timerbug

**Disadvantages:**
- Requires sprite files
- Digits cannot be easily changed, replaced, or rotated

---

## Information on v1-d_nosprites Timer

**NEW! v1-d_nosprites Timer:**
- Sprites are changed to brush entities.
- No need to include sprite files.
- Easily change digit textures and rotate the timer.
- Decimals are still included.
- Precache count raised from 13 to 45 (use VLUZACN compiler to keep it at 13).

### Steps for VLUZACN Compiler:
1. Copy digits, buttons, and the "group of 178 entities" to your map.
2. Ungroup timer with digits.
3. Select all digit groups except seconds [59:5_.9] and use `Ctrl+X` and `Ctrl+V` to remove and return digits.
4. Select the "group of 178 entities" and use `Ctrl+X` and `Ctrl+V`.
5. Fix or ignore the 32 errors (ALT+P): Entity (func_wall_toggle) has unused keyvalues if not using zhlt_usemodel feature.

### Changing Textures Correctly:
1. Name your textures `<name>num#` (e.g., spr1n_num0).
2. Include your textures into a wad.
3. Use the texture tool and press Replace.
4. Replace `kznum#` with `<name>num#`.

For information from the original source, visit:
- [spr1n.kz-baltic.eu](https://web.archive.org/web/20170401043000/http://spr1n.kz-baltic.eu/mapping/timer/spr1n_timer_readme.html)
- [XJ Forum Thread](https://web.archive.org/web/20130925074830/http://xtreme-jumps.eu/e107_plugins/forum/forum_viewtopic.php?225302)
