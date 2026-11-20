# Scope It Out: A Microscopy Lab

An interactive replacement for the "Lab: Microscopy" slideshow, styled to match Focus Pocus. Seven stations: microscope anatomy, total magnification, a virtual microscope "license test" with troubleshooting cases, the cheek cell and onion cell wet mounts (built around Mr. Rankin's two how-to videos, with checkpoints), an animal vs. plant Venn diagram, and a downloadable lab report.

## What's in this folder

- `index.html` is the whole app (styles and scripts are inside it).
- `img/` holds the microscope photo, the micrographs, the LC logo, Marty, and stills pulled from the videos.
- `video/` holds the two how-to videos, compressed from the 4K originals to 960x540. Each is under 25 MB so it can be uploaded through the GitHub website.
- `fonts/` holds the four typefaces Focus Pocus uses (Bricolage Grotesque, Atkinson Hyperlegible, IBM Plex Mono, Overpass), so nothing loads from outside the folder.

## Preview and publish

To preview, double-click `index.html` (Chrome). There is no build step, and nothing loads from outside this folder.

To publish:

1. On github.com, create a new repository (for example `scope-it-out`). Public or private both work with Vercel.
2. On the new repo's page choose "uploading an existing file". Open this folder in Finder, select everything inside it (`index.html`, `README.md`, `fonts`, `img`, `video`) and drag those items onto the page. Drag the contents, not the `scope-it-out` folder itself, so `index.html` lands at the top level of the repo. Commit.
3. On vercel.com choose Add New, then Project, and import the repo. Leave the framework preset on "Other" and the build settings empty, then Deploy.

All 40 files go up in one drag (GitHub's website allows 100 files at a time and 25 MB per file; the two videos are 23 MB and 21 MB). After that, every commit to the repo redeploys the site automatically.

Student work saves automatically in the browser on each Chromebook. Settings (top right) has "Erase my work and start over".

## Accessibility and learning supports

The Settings button opens the same suite as the other Mustang apps:

- **See it.** Text size (Normal, Large, Extra large), Light or dark (matches the device unless a student picks one), High contrast, Animations (Full or Calm).
- **Read it.** Read aloud (speaker buttons on directions and questions, spoken feedback, select any text to hear it), Reading speed, Dyslexia-friendly text (Lexend with extra spacing), Reading ruler, Video captions.
- **Language support.** Word help (dotted underline on key vocabulary, tap for a plain definition), Spanish alongside the English, and a Word bank.
- **Colors.** Color-blind friendly mode swaps green and red for blue and orange and adds a check or an X to right and wrong answers.
- **Learning supports.** Fewer answer choices, Show me after a miss, Sentence starters, Microscope coach. These are saved with the student's work and listed at the bottom of the lab report as "Supports used".

Display settings stay on the device and never change a score. Animations are Full unless a student chooses Calm; the app ignores the Chromebook's own reduce-motion flag on purpose, because many school devices have it switched on.

To edit: the vocabulary and Spanish translations are in the `GLOSS` list, the four supports are in `SUPPORTS`, and the sentence starters are in `STARTERS`, all in `index.html`. The Spanish was written by Claude and has not been reviewed by a Spanish speaker, so it is worth a look from a colleague before students rely on it.

## Things worth checking

- **Captions.** The video captions were machine-transcribed and tidied by hand. They live in a block called `CAPS` in `index.html`. Each line is `[start seconds, end seconds, "text | split | into | lines"]`.
- **Checkpoint timing.** The pause points are in the `CHECKS` block right below the captions. `t` is the time in seconds where the video pauses. They were placed in natural pauses in the narration; nudge a number if one lands mid-sentence.
- **Microscope labels.** The 12 part names, descriptions and dot positions are in the `PARTS` block. Positions are tied to `img/scope.png`, so swapping in a photo of a different microscope means updating the x and y numbers.
- **Virtual microscope.** Station 3 is hands-on: students flip the switch, carry the slide to the stage, spin the nosepiece, turn the knobs and slide the diaphragm lever directly on the drawing. The nine mission steps are in the `MISSION` list.
- **Home page wording.** The memo, the station cards and the photo captions are in the `VIEW.home` block and the `ST` and `GALLERY` lists.

## Images

Replace any of these in `img/` with a file of the same name and the app uses the new one: `lc-logo.png`, `marty.png`, `cheek-40x.jpg`, `cheek-100x.jpg`, `onion-40x.jpg`, `onion-100x.jpg`, `air-bubbles.jpg`, `onion-wrinkled.jpg`.

Please don't replace `cheek-400x.jpg` or `onion-400x.jpg` without also updating their click maps (`MAPS` in `index.html`); the "Tag the cells" activity knows where each nucleus, membrane and wall is in those two exact photos.
