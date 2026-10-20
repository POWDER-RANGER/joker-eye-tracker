# Joker Eye Tracker

Interactive pure-visual experience: the Joker's eyes track device tilt (accelerometer/gyroscope) on mobile and mouse movement on desktop.

## Setup the image layers

You must prepare two PNG files (same dimensions, perfectly aligned):

1. **joker-base.png** – Full artwork with the irises/pupils removed (or sockets filled so the eyes can sit cleanly on top).
2. **joker-eyes.png** – Only the irises + pupils on a transparent background.

Place both files in the root of this repository (same folder as `index.html`).

See the original conversation for detailed Photoshop / Photopea / GIMP steps.

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
