# resting_state_screen
screen for resting state neuroimaging
Resting-State Cross (HTML + PNG)

# Resting-State Task (Configurable Landing + Automatic Runner)

This repository provides a simple, browser-based resting-state display used for behavioral, EEG, MEG, or fMRI experiments. It allows the experimenter to configure timing and visual parameters before starting.

---

## Overview

### The sequence presented to the participant:

| Phase | Display | Default Duration | Description |
|------|---------|-----------------|-------------|
| **1. Fixation** | Centered cross | 150 seconds | Participant looks at the cross and relaxes. |
| **2. Interval (Instruction Text)** | “Now please close your eyes and rest” | 5 seconds | Participant prepares to close eyes. |
| **3. Rest (Eyes closed)** | Blank screen (white or black) | 150 seconds | Participant rests without visual input. |
| **4. End Screen** | “END” | Until escape | Signals the end of the resting period, fullscreen exits. |

The entire flow runs **automatically** once started.

---

## Files

landing.html → Landing page (configuration UI),
index.html → Runner page (displays the timed sequence),
cross.png → Optional cross image asset (not required by the default renderer),
README.md → Documentation (this file)



---

## Landing Page (landing.html)

The landing page lets you configure:

| Setting | Description | Default |
|--------|-------------|---------|
| Fixation duration (d1) | Duration of cross display | 150 s |
| Interval duration (inter) | Time instruction text remains visible | 5 s |
| Rest duration (d2) | Duration of blank screen | 120 s |
| Variant | `white` = white bg + black cross, `black` = black bg + white cross | white |
| Cross size | Display size of cross (`vmin`) | 16 vmin |
| Cross thickness | Cross stroke width (`px`) | 4 px |
| Cursor | Whether the mouse pointer is hidden | hidden |

All inputs are **validated** and **saved automatically** in the browser (localStorage), so the experimenter does not need to re-enter values across subjects.

### Start the Task
Press the **Start** button — the sequence opens in the same window.

---

## Runner Page (index.html)

`index.html` receives configuration values from `landing.html` automatically and runs the sequence in fullscreen mode.

### Console Debug Timer

A timestamped log prints once per second for monitoring / protocol verification:

[rest] phase=1 (fixation), elapsed=32s, remaining=118s



Good for experimenter tracking; safe for participant use (no visual timer appears).

---

## URL Parameters (automatically generated — no need to edit manually)

| Parameter | Meaning |
|----------|---------|
| `d1` | Fixation duration (seconds) |
| `inter` | Interval text duration (seconds) |
| `d2` | Blank screen duration (seconds) |
| `variant` | `white` or `black` |
| `size` | Cross size in vmin |
| `thickness` | Cross stroke width (px) |
| `cursor` | `none` or `auto` |

---

## Fullscreen Notes

- Fullscreen activates automatically.
- Some browsers require the first click or keypress — this is already handled by the code.

---

## Recommended Usage Workflow

1. Open the **landing page** (`landnig.html`) in the experiment browser.
2. Set durations and visual variant.
3. Click **Start**.
4. Let the participant perform the resting-state task.
5. Monitor progress via the console timer (optional).

---

## License
You are free to use, modify, and integrate this into any study.
