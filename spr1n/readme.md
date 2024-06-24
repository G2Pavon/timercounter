# spr1n Timer - Information and Installation Guide (v1 and v1-d)

## Introduction

This timer is based on *Sadpuppy*'s timer idea (sprite digits usage and game_counter toggle method with cycle),
tho its pretty diferent and has many advantages. I discovered that Sadpuppy's timer has pretty nice system
and started this project (~a year ago), but due to a lot of bugs stopped. Few months ago finished with stable
versions and today just adjusted some few last things (had no much time/motivation to complete it faster).
The aim was to make certain timer with decimal and less entities comparing to *Kreedz* timer (it was a long
before Xtreme-Jumps.eu started to use decimals). Even its not that important now with the current situation on XJ, the aim
was reached , and I belive such timer can be useful for some fast/short maps or in case you want to save
entities.

## Description

The timer consists of the following parts:
1. **Start Button** (target and master must not be changed)
2. **Stop Button** (target and master must not be changed)
3. **Group of 1XX Entities** (do not change)
4. **Box for Digits** (feel free to edit it)
5. **Digits (Group of Sprites)** (do not edit unless you know what you are doing)

> **Note:** Since timer uses sprites as digits - you cant just rotate timer with Transformation tool, new angles should
be set for all sprites.

### Accuracy and Compatibility
- **Timer accuracy:** ~0.01 seconds
- **Timer bug:** may appear with low FPS (<10-20/cs minimize) for decimal timer. Not tested for
timer without decimals (in theory timerbug shouldnt appear(or go big) even with high uptime).
- **Compatibility:** Not compatible with Kreedz and Sadpuppy's timers (in the same map).

## Comparison

| Timer              | Precache | Entities (ZHTL entdata) | Timerbug |
|--------------------|----------|----------|----------|
| **spr1n timer v1-d [59:59.9]** | 13/512 (2.5%) | 219 (28291/524288 5.3%) | @low fps, better than kreedz timer |
| **spr1n timer v1 [59:59]**    | 13/512 (2.5%) | 173 (22935/524288 4.4%) | High uptime?, less than kreedz timer |
| **kreedz timer [59:59]**      | 39/512 (7.6%) | 236 (41511/524288 7.9%) | Uncertain digit change, random timer bugs, +1hr uptime |
| **Sadpuppy timer [3:59:59]**  | 14/512 (2.7%) | 159 (22442/524288 4.3%) | Constant delays due to system architecture |

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
  - There is a group of 1XX entities (timer engine) in the center of timers – copy that anywhere into your map
(prefereably  near the timer digits, so you allways know what are those entities and where)

### Timer Digits
  - Since you cant “just” rotate the digits – choose timer layout that suits you and your map. This layout
consists of BOX and digit-sprites. If you want to remove the box or you have your own layout for the timer
– ungroup the object once, get rid of the box, select sprites and move them where you need. Note that
sprite thickness is 32 units, but digits are drawn right in the middle

### Files
- Make sure you include above mentioned files (sprites) to your map, according to digits you will use.

> **NB!** To avoid unexpected bugs - its recommended you compile your map without VIS and RAD (because its faster
and doesnt affect the timer) to verify timer work.

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

Original source:
- [spr1n.kz-baltic.eu](https://web.archive.org/web/20170401043000/http://spr1n.kz-baltic.eu/mapping/timer/spr1n_timer_readme.html)
- [XJ Forum Thread](https://web.archive.org/web/20130925074830/http://xtreme-jumps.eu/e107_plugins/forum/forum_viewtopic.php?225302)
  
Author: [spr1n](https://xtreme-jumps.eu/profile/6200)

## Showcase

###### *old sprite above, kznum middle and kzblt below*
![Screenshot 1](https://github.com/G2Pavon/kreedztimercounter/assets/14117486/9b43c2f2-ff5c-4f2a-88e2-96da9f776c66)

![Screenshot 2](https://github.com/G2Pavon/kreedztimercounter/assets/14117486/a303e318-3f8f-41b7-b1a4-76c6afec23bd)


###### *custom texture*
![Screenshot 4 (custom)](https://github.com/G2Pavon/kreedztimercounter/assets/14117486/3ef72ffd-cf0c-46dc-aeb2-c64cf1bbe06e)



