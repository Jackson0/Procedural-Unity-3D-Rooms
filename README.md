# Procedural-Unity-3D-Rooms



Disclaimner: This readme was written by a human and formatted using AI

---


Building Unity 3D Procedural Dungeon / Rooms — A showdown between **Claude 4.6 Opus**, **Gemini 3.1 PRO**, **GPT5.4 (High)** and **GPT5.4 (XHigh)**

Decided to make this available, for science, and because it is interesting.

---

## The Setup

It started from a base script that was built using Claude 4.6 Opus, that was capable of building a single-floor (no stairs) rooms and corridors "complex."

I then decided, using this as a base + a prompt, to compare the output of the current top major LLM coding agents available.

---

## Environment

- Unity 6.3 with the Universal 3D template
- VS Code + Copilot

---

## Execution

All agents were fed the script, and the prompt. 1-shot generation, NO tweaks afterwards unless to fix a compilation error.

---

## Files

Included in this repo are the packaged GameObject asset — You should be able to simply download it and pull it into Unity 6.3.

>  Other versions of Unity (especially earlier) may result in issues and may need to be adapted.

| # | File |
|---|------|
| 1 | `Procedural_Claude_Opus_4.6.unitypackage` |
| 2 | `Procedural_Gemini_3.1_PRO.unitypackage` |
| 3 | `Procedural_GPT5.4_High.unitypackage` |
| 4 | `Procedural_GPT5.4_XHigh.unitypackage` |

---

## Result Summary

###  Claude Opus 4.6

**Score: 6/10** | ⏱ ~15 mins | 📄 1,041 lines

####  The Good
- Around the perimeter Opus added some rectangles scattered about, with varying dimensions. I assume this is to add to the scene as distant buildings. These objects are named "Towers"
- From outside, the main structure looks really cool — fascinating even. Lots of corridors, rooms or spaces along corridors.
- It added some more detail within, apart from the lights. There are pillars, corner fills, trimmings etc. The windows even have frames.
- Random different colored lights scattered about for added ambience.
- Rooms have "bulbs"! Spheres with an emission material. Neat.

####  The Bad
- Windows are not see-through. The glass itself is, but no apertures were created where windows are placed.
- The stairs.. the stairs. Probably one of the tougher parts of the assignment — here they all seem to lead dead straight into the floor of the upper level. No gap in the floor, so you can't actually use them, meaning all upper levels are unreachable.
- Some stairs are very thin. They ignore the "Stairs Width" field.

> Overall a great attempt with much to build upon further.

---

###  Gemini 3.1 PRO

**Score: 4/10** | ⏱ ~5 mins | 📄 445 lines *(less than the prompt script!)*

####  The Good
- The overall structure looks good — interesting architecture.
- Gemini completed the task quicker than any other agent — but it shows.
- Windows are see-through — has glass and an actual hole in the wall. Good.

####  The Bad
- The geometry is a bit of a mess. There are rooms and corridors, but also many open gaps in the walls (where corridors meet), walls sticking out into rooms/corridors etc.
- Stairs. They look cool, but they all lead dead into the upper floor. Same as Opus.
- Stairs are placed in non-sensical spots. Some clip through windows.

> I'm sure the issues can be fixed — but they are there.

---

###  GPT 5.4 High

**Score: 6/10** | ⏱ ~10 mins | 📄 1,544 lines

####  The Good
- Somewhat interesting structure — it took a different approach. Rooms aren't spaces at the ends of corridors here. They seem to just be spaces built out from corridors. Still good for exploring.
- It added lots of lights. Looks nice, but definitely too much.
- Lights are emissive bulbs again.
- There are interesting objects to be found! I found what it called "Curiosity Spires" scattered about. They aren't very complicated, but I approve!
- Windows are good. See through, with windowsills.
- Stairs have openings at the top. So close to being usable.

####  The Bad
- Stairs. They are unusable. Steps too high, and too narrow. Adjusting the width does not help. They also go through room walls. They DO however have openings in the floor at the top, so if the staircase dimensions are fixed they should actually work fine.

> Got some good things going, just messed up with the stairs.

---

###  GPT 5.4 XHigh

**Score: 9/10** | ⏱ Over 1h 30m | 📄 1,687 lines

####  The Good
- This one looks pretty cool. Very labyrinth-like. Lots of corridors leading to lots of rooms.
- **The stairs are usable!** Honestly most of its score is just because of this.
- Windows work.
- This one is fun to explore.

####  The Bad
- No "curiosities," not much effort into the ambiance.
- In some cases the stair placement blocks a door.

> Pumped out a behemoth of a script that actually works well.

---

## Leaderboard

| Rank | Model | Score | Time | Lines |
|------|-------|-------|------|-------|
|  1 | GPT 5.4 XHigh | 9/10 | ~1h 30m | 1,687 |
|  2 | Claude Opus 4.6 | 6/10 | ~15 min | 1,041 |
|  2 | GPT 5.4 High | 6/10 | ~10 min | 1,544 |
|  4 | Gemini 3.1 PRO | 4/10 | ~5 min | 445 |
