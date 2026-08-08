# Night Volt — Portfolio Site

A single-page portfolio for **Night Volt**, a Discord bot developer. Built as one static HTML file — no build step, no dependencies to install.

## What it is

A dark, circuit/oscilloscope-themed landing page:

- Animated 3D node network in the background (Three.js) that reacts to mouse and scroll
- Oscilloscope waveform canvas behind the hero
- Terminal-style boot sequence on load
- Voltage-pulse SVG dividers between sections
- Tilting "module" cards for each service
- Scroll-position side nav (desktop only)

## Files

```
nightvolt.html   the entire site (HTML + CSS + JS in one file)
```

## Running it locally

No build tools needed. Either:

- Double-click `nightvolt.html` to open it directly in a browser, or
- Serve it locally so relative behavior matches production:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/nightvolt.html
```

## Before publishing — required edit

Search the file for `YOUR_USER_ID` (two occurrences: hero CTA and contact section) and replace with your real Discord contact, e.g.:

```html
<a href="https://discord.com/users/123456789012345678" ...>
```

or swap in a `discord.gg/...` invite link instead of a user link.

## Dependencies (loaded via CDN, no install needed)

- [GSAP](https://gsap.com/) + ScrollTrigger — scroll-based reveals and the hero depth-tilt
- [Three.js r128](https://threejs.org/) — the 3D background node network
- Google Fonts: JetBrains Mono, Inter

## Customizing

| What | Where |
|---|---|
| Colors (volt yellow, purple, background) | CSS `:root` variables near the top of `<style>` |
| Copy / section text | Directly in the HTML body |
| Service cards | `.modules` section — add/remove `.module` blocks |
| Node count / behavior in the 3D background | `NODE_COUNT` and the `animate()` loop in the closing `<script>` |
| Discord contact link | Both `YOUR_USER_ID` occurrences |

## Notes

- Everything is self-contained in `nightvolt.html` — safe to rename or move as one file.
- No analytics, tracking, or external calls beyond the CDN script/font loads above.
