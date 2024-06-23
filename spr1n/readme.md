http://spr1n.kz-baltic.eu/mapping/timer/spr1n_timer_readme.html

---

INTRODUCTION

This timer is based on Sadpuppy's timer idea (sprite digits usage and game_counter toggle method with cycle),
tho its pretty diferent and has many advantages. I discovered that Sadpuppy's timer has pretty nice system
and started this project (~a year ago), but due to a lot of bugs stopped. Few months ago finished with stable
versions and today just adjusted some few last things (had no much time/motivation to complete it faster).
The aim was to make certain timer with decimal and less entities comparing to kreedz timer (it was a long
before XJ started to use decimals). Even its not that important now with the current situation on XJ, the aim
was reached , and I belive such timer can be useful for some fast/short maps or in case you want to save
entities.


DESCRIPTION

Timer consists of following parts:
1. start button (target and master must not be changed)
2. stop button (target and master must not be changed)
3. group of 1XX entities (don not change)
4. box for digits (feel free to edit it)
5. digits, group of sprites (do not edit unless you know what you are doing)

Since timer uses sprites as digits - you cant just rotate timer with Transformation tool, new angles should
be set for all sprites.

Timer accuracy ~0.01. Timer bug appear with low fps (<10-20/cs minimize) for decimal timer. Not tested for
timer without decimals (in theory timerbug shouldnt appear(or go big) even with high uptime).

NB! timer is uncompatable with kreedz and sadpuppy's timers (in the same map)


COMPARISON

-spr1n timer v1-d [59:59.9]-
precache: 13/512 (2.5%)
entities: 219 (ZHTL entdata: 28291/524288    5.3%)
timerbug: @low fps, with average-high fps better than kreedz timer

-spr1n timer v1 [59:59]-
precache: 13/512 (2.5%)
entities: 173 (ZHTL entdata: 22935/524288    4.4%)
timerbug: high uptime?, but much less than kreedz timer (by old tests)

-kreedz timer [59:59]-
precache: 39/512 (7.6%)
entities: 236 (ZHTL entadata: 41511/524288    7.9%)
timerbug: uncertain digitchange, sometimes random timerbugs, +1hr uptime

-sadpuppy timer [3:59:59]-
precache: 14/512 (2.7%)
entities: 159 (ZHTL entadata: 22442/524288    4.3%)
timerbug: much constant delays caused by system architecture.

Sadpuppy's timer has nearly no timerbug compared to kreedz timer, it just has offset at start (~1 second)
caused by system architecture - delays (thats why I tried to develop this timer's idea).


FILES

spr1n_timer_v1-d.rar - timer with decimal [59:59.9]
spr1n_timer_v1.rar  - timer without decimal [59:59]

You dont need to include all files (sprites), just depending on digits you choose:
top digits (old style) – sprites\spr1n\digits\kzold\
middle digits – sprites\spr1n\digits\kznum\
bottom (white) – sprites\spr1n\digits\kzblt\
NB! do not modify those files.


INSTALLATION

Buttons:
Copy both buttons to your map. Those use standart textures from timecounter.wad . If you want to use your
own buttons – just copy “target” and “master” key values to them!

Entities:
There is a group of 1XX entities (timer engine) in the center of timers – copy that anywhere into your map
(prefereably  near the timer digits, so you allways know what are those entities and where)

Timer digits:
Since you cant “just” rotate the digits – choose timer layout that suits you and your map. This layout
consists of BOX and digit-sprites. If you want to remove the box or you have your own layout for the timer
– ungroup the object once, get rid of the box, select sprites and move them where you need. Note that
sprite thickness is 32 units, but digits are drawn right in the middle

Files:
Make sure you include above mentioned files (sprites) to your map, according to digits you will use.

NB!
To avoid unexpected bugs - its recommended you compile your map without VIS and RAD (because its faster
and doesnt affect the timer) to verify timer work.




Ask if something is unclear, because Im asleep and may not properly explane some aspects. Also if you have
any sugestions or found a bug – I will be glad if you post that. Tho timer gone through plenty hard tests
and should not contain any critical bugs.

PS. if you need your own digits or custom look – I might help with that. Its not that easy to change or
rotate digits actually since those are sprites. Digits could be done with func_wall_toggle instead of
sprites, but that would raise precache up to ~50, unless you use phlt_copy_brush (but you cant find this
entity in zhlt).


\spr1n
