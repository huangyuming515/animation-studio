
# DOWNLOAD & open with index.html
 
Animation & Four-Direction Character Studio

A browser-based animation editor and four-direction character preview tool, distributed as a single HTML file.

Import existing artwork or extract video frames, edit animations, organize character actions, and export assets without installing Node.js or running a backend.

## Features

### Animation Editing

- Import multiple images and arrange frame order.
- Duplicate, delete, and reorder frames.
- Set individual or shared frame durations.
- Preview forward, reverse, and ping-pong playback.
- Slice regular sprite sheets using rows, columns, margins, and spacing.
- Extract frames from browser-supported videos.

### Image Editing

- Remove similar-colored backgrounds.
- Optionally remove only background areas connected to image edges.
- Erase pixels or rectangular selections to transparency.
- Crop individual frames or apply supported edits in batches.
- Undo the most recent image edit for each frame.

### Layers and Effects

- Add image overlays, speech bubbles, subtitles, and narration text.
- Adjust position, size, opacity, typography, and colors.
- Display layers across all frames, one bound frame, or a frame range.
- Apply pulsing glow, orbiting sparks, rotating magic circles, and speed lines.

### Four-Direction Characters

- Organize front, back, left, and right artwork.
- Add idle, walk, and run frame sets.
- Adjust frame dimensions, scale, alignment, and offsets.
- Preview movement with keyboard or on-screen controls.
- Export direction sheets and individual animation sheets.
- Copy a character action into the animation editor for GIF export.

### Project Files

- Save supported assets, frames, timing, layers, and settings as JSON.
- Load compatible project files to continue editing.
- No automatic saving: download your project before closing the page.

## Interface Languages

The eight-language edition includes:

- Traditional Chinese
- Simplified Chinese
- English
- Japanese
- Korean
- Spanish
- French
- German

Use the language selector at the top of the page. The selection is remembered when browser storage is available.

Translations cover supported interface labels, common messages, and built-in tutorials. Some unlisted messages may remain in their original language.

User-entered dialogue, narration, filenames, and image content are not translated. Switching languages does not change the project format.

## Quick Start

1. Download `index.html`.
2. Open it in a recent desktop version of Chrome or Edge.
3. Import a few sequential images.
4. Check the frame order.
5. Set each frame to approximately 100 milliseconds.
6. Preview the animation.
7. Generate a GIF, then click its download link.
8. Create and download a project JSON file to save your editing work.

Generating an output does not automatically save it to your computer.

## Common Workflows

### Create an Animation from Images

1. Import sequential images such as `001.png`, `002.png`, and `003.png`.
2. Reorder frames if necessary.
3. Adjust frame durations.
4. Add optional layers and effects.
5. Preview and export.

Timing examples:

- 50 ms per frame: approximately 20 FPS.
- 100 ms per frame: approximately 10 FPS.
- 200 ms per frame: approximately 5 FPS.

Animated GIF and WebP imports are not automatically separated into individual frames.

### Extract Video Frames

1. Select a video.
2. Set the start and end times.
3. Choose the extraction rate and maximum image size.
4. Extract and append frames to the animation.
5. Edit and export the result.

Start with a short 2–3 second clip, 10 FPS, and a 720 px long edge.

Video support depends on browser decoding capabilities. If playback fails, try converting the source to MP4 with H.264 video.

Extraction does not preserve audio or transfer motion to another character.

### Slice a Sprite Sheet

1. Select the imported sheet.
2. Enter its column and row counts.
3. Set margins and spacing.
4. Preview the grid.
5. Choose the reading order and slice.

For a sheet containing four cells across and two down, use four columns and two rows.

Slicing replaces the selected frame and cannot be undone with the image-edit undo button. Keep the original sheet.

### Preview a Character

1. Import artwork for each direction.
2. Add walk frames and optional run frames.
3. Use consistent frame dimensions and alignment.
4. Enable keyboard control and click the control canvas.
5. Move using the controls below.

Keyboard controls:

- Arrow keys or WASD: walk.
- Shift + movement keys: run.
- Release movement keys: return to idle.

Direction mapping:

- Front: down.
- Back: up.
- Left: left.
- Right: right.

Missing actions may fall back to available artwork. A single image moves as a static pose; the tool does not generate walking frames.

If source frames already share a consistently aligned canvas, preserve their transparent padding to reduce animation jitter.

## Export Formats

### Animated GIF

- Looping animation.
- Up to 256 colors.
- No partial transparency.
- Requires the GIF encoding library to be available.
- Solid backgrounds are recommended for soft glow effects.

### PNG

- A single rendered frame.
- Supports transparency and partial transparency.

### PNG Sprite Sheet

- A static image containing multiple frames.
- Requires animation or game code to play.
- Does not include keyboard controls, movement paths, or collision logic.

Four-direction sheets use the order front, back, left, right.

For a 2 × 2 layout:

- Top left: front.
- Top right: back.
- Bottom left: left.
- Bottom right: right.

The four-direction export uses the first idle frame from each direction.

### WebM

- Silent video recorded in real time.
- Transparent areas use the selected background color.
- Requires compatible browser recording APIs.
- Keep the tab in the foreground during recording.
- Performance limitations may cause dropped frames.

Direct MP4 export is not included.

## Saving and Loading Projects

To save:

1. Create the project file.
2. Click the project JSON download link.
3. Keep the downloaded file in a safe location.

To resume:

1. Open `index.html`.
2. Load a compatible project JSON file.

Project files preserve supported frame data, layers, character assets, and settings.

They do not preserve:

- The original video file.
- Playback position.
- Image-edit undo history.

Loading replaces the current workspace. Save existing work first.

Project compatibility depends on the base editor version. The language upgrade does not convert older project formats.

## Publish with GitHub Pages

1. Create a public GitHub repository.
2. Upload `index.html` to the repository root.
3. Add this file as `README.md`.
4. Open **Settings → Pages**.
5. Select **Deploy from a branch**.
6. Select your publishing branch, usually `main`.
7. Select **/ (root)** and save.
8. Open the website URL shown by GitHub Pages after deployment.

The default project website address follows this pattern:

https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/

To update the website, replace the root `index.html` and commit the change.

Upload the upgraded animation editor, not the separate language-upgrade utility. Rename files such as `index (1).html` to `index.html` before uploading.

If an old interface remains visible after deployment, try a hard refresh with Ctrl + Shift + R.

## Privacy and Network Access

- Selected images, videos, and project data are processed in the browser.
- Selecting local files does not automatically upload them to GitHub.
- No application backend or API key is required.
- GIF export loads `gifenc@1.0.3` from jsDelivr when it is not already available in the current session.
- Loading the GIF library creates a network request to the CDN; it does not require uploading
