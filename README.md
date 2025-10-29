# resting_state_screen
screen for resting state neuroimaging
Resting-State Cross (HTML + PNG)

# Resting-State Sequence (Staged Timing)

This repository provides a **controlled resting-state sequence** with automatic fullscreen, fixation display, staged instructions, a blank period, and a final end screen.

## Display Sequence

| Phase                 | Duration (Default) | Display                               | Description                                            |
| --------------------- | ------------------ | ------------------------------------- | ------------------------------------------------------ |
| 1. Fixation cross     | **150s** (2.5 min) | Centered + cross                      | Participant keeps eyes open and stays still.           |
| 2. Instruction        | **30s**            | "Now please close your eyes and rest" | Participant closes eyes and relaxes.                   |
| 3. Blank white screen | **120s** (2 min)   | White screen only                     | Participant rests with closed eyes.                    |
| 4. End screen         | Until user closes  | "END"                                 | Signals completion and automatically exits fullscreen. |

A **debug timer** logs current phase, elapsed time, and remaining time in the browser console.

---

## Files Included

* `index.html` — The **staged resting-state sequence** (fullscreen by default).
* `cross.png` (optional) — High-resolution fixation cross image if needed elsewhere.

---

## GitHub Pages Deployment

1. Upload the files to your repository root.
2. Go to **Settings → Pages**.
3. Set **Source** to `main` (root).
4. Visit:

   ```
   https://<your-username>.github.io/<repository-name>/
   ```

Example:

```
https://markoneuro.github.io/rest-cross/
```

---

## URL Customization Parameters

You can override durations or colors via URL parameters:

| Param       | Meaning                | Units      | Default   |
| ----------- | ---------------------- | ---------- | --------- |
| `d1`        | Fixation duration      | seconds    | `150`     |
| `d2`        | Instruction duration   | seconds    | `30`      |
| `d3`        | Blank white duration   | seconds    | `120`     |
| `bg`        | Background color       | hex or rgb | `#ffffff` |
| `color`     | Cross color            | hex or rgb | `#000000` |
| `text`      | Instruction text color | hex or rgb | `#000000` |
| `size`      | Cross arm length       | vmin       | `16`      |
| `thickness` | Cross stroke width     | px         | `4`       |

### Example (short test version):

```
https://<your-username>.github.io/<repo>/?d1=5&d2=3&d3=4
```

### Example (dark cross on white):

```
?color=000000&bg=ffffff
```

---

## Notes

* Fullscreen is **requested automatically**, but browser security may require the first click or key press — the script handles this.
* Cursor is hidden by default; use `?cursor=auto` to show it.
* Phase progression does not depend on user input.

---

## Debugging

Open **DevTools → Console** to watch the timer:

```
[rest] phase=1 (fixation), elapsed=12s, remaining=138s
```

This confirms timing is progressing as expected.

---

If you'd like, I can also generate:
✅ A version with audio cue transitions
✅ A version that logs timestamps to a server / Firestore
✅ A version that syncs phase timing to EEG triggers

Just tell me your recording setup.


