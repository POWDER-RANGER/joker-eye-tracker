# Joker Eye Tracker

Interactive pure-visual experience: the Joker's eyes track device tilt (accelerometer/gyroscope) on mobile and mouse movement on desktop.

## Artwork setup

The current runtime draws and animates pupils over a single full-face image; it does not load a separate `joker-eyes.png` layer.

1. Prepare one complete artwork image with the face and eye regions visible.
2. Save it as `joker.png` or `joker-base.png` in the repository root (the same folder as `index.html`).
3. Adjust `LEFT_EYE`, `RIGHT_EYE`, and `PUPIL_RADIUS` in `index.html` to match the artwork dimensions.
4. Reload the page and test mouse movement on desktop and device tilt on a supported mobile browser.

**Current repository state:** the expected artwork is not included. The tracked `joker-original.jpg` is a text placeholder, not a usable image. The interactive effect will remain in its artwork-needed state until a valid image is added.

**Asset status:** `joker-original.jpg` is currently a text placeholder, not image data. The interactive effect needs valid artwork assets in the repository root before it can render. No original artwork is bundled at present.

## Live demo

Once GitHub Pages is enabled (Settings → Pages → Source: Deploy from a branch → `main` / root), the site will be available at:

**https://powder-ranger.github.io/joker-eye-tracker/**

## Controls

- **Mobile**: Tilt the phone/tablet. Tap the screen once to grant motion permission (required on iOS).
- **Desktop**: Move the mouse.

## Tweaking sensitivity

Open `index.html` and adjust the constants near the top of the `<script>` block:

- `MAX_OFFSET_X` / `MAX_OFFSET_Y` – maximum travel in pixels
- `SENSITIVITY` – overall multiplier
- `SMOOTHING` – how quickly the eyes catch up (0 = instant, higher = laggy/organic)

## Notes

- Pure visual – no text overlays after the short hint fades.
- Uses `deviceorientation` + mouse fallback.
- GPU-accelerated transforms for smooth 60 fps motion.
