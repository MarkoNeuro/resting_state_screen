# resting_state_screen
screen for resting state neuroimaging
Resting-State Cross (HTML + PNG)

This repo provides:

rest.html – A self-contained HTML page that renders a white background with a centered fixation cross. You can tweak it via URL parameters.

cross.png – A high-resolution (2048×2048) PNG with a white background and a black plus-shaped fixation cross, suitable for preloading in game engines or experimental frameworks.

Quick Start (GitHub Pages)

Create a new GitHub repository (e.g., rest-cross).

Upload these files to the root of the repo:

rest.html

cross.png

README.md (this file)

Go to Settings → Pages:

Source: “Deploy from a branch”

Branch: main (root)

After it builds, your page will be available at:

https://<your-username>.github.io/rest-cross/rest.html

Use in your experiment

As a page (fullscreen or iframe):

<iframe
  src="https://<your-username>.github.io/rest-cross/rest.html?size=20&thickness=4&color=%23000000&bg=%23ffffff"
  style="position:fixed; inset:0; width:100%; height:100%; border:0;"
  allow="fullscreen">
</iframe>

As an image asset:
Preload cross.png and display centered on a white stage. The asset has a large resolution so it looks crisp on high-DPI displays.

rest.html – URL Parameters

size – arm length of cross in vmin, default 20

thickness – bar thickness in px, default 4

color – cross color (hex), default black; URL-encode # as %23

bg – background color (hex), default white

cursor – none (default) or auto

fs – 1 to request fullscreen on first user interaction

Examples:

Default white bg + black cross:.../rest.html?size=20&thickness=4&color=%23000000&bg=%23ffffff

Thin cross, cursor visible:.../rest.html?size=20&thickness=2&cursor=auto

Dark room:.../rest.html?size=18&thickness=3&color=%23ffffff&bg=%23222222

File tree

rest-cross/
├─ rest.html
├─ cross.png
└─ README.md

Notes

The PNG cross is a plus sign (+) (standard fixation cross), with bar thickness ≈ 4% of the image size and arm length ≈ 60% of the canvas dimension.

rest.html hides the cursor by default; set cursor=auto if you need to see it.

For strict visual consistency across monitors, prefer the PNG. For responsive layouts and quick tweaks, prefer the HTML page.

