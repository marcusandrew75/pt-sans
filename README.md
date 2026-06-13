# P.T. SANS

**A playable, browser-based horror demo built with Three.js — a loving homage to Hideo Kojima's *P.T.***

An L-shaped haunted hallway and a bedroom, rendered in real time in the browser. Dread by candle-dim lamplight, a house full of unwell sounds, framed photographs of people who are no longer smiling, and a figure named Lisa who would very much like you to stay. Walk slowly. Wear headphones.

> *"P.T." — "sans" Kojima.* The name is the wink: this is P.T. **without** the original — an independent tribute, recreated from scratch.

---

## ⚠️ Homage & Disclaimer (please read)

This project is an **unofficial, non-commercial fan tribute** inspired by ***P.T.* (Playable Teaser, 2014)** — the legendary teaser for the cancelled *Silent Hills*, conceived and directed by **Hideo Kojima** in collaboration with **Guillermo del Toro**, developed by **Kojima Productions / 7780s Studio**, and published by **Konami**.

- It is **not affiliated with, endorsed by, sponsored by, or associated with** Konami, Kojima Productions, Hideo Kojima, Guillermo del Toro, or *Silent Hill(s)*.
- ***P.T.*, *Silent Hills*, *Silent Hill*, and "Lisa"** are the intellectual property of **Konami** and their respective owners. All trademarks belong to their respective holders.
- **No original *P.T.* assets are used or redistributed.** No ripped models, textures, audio, code, or maps. Every wall, light, sound, and the level layout in this project was **independently recreated** — geometry, textures, and the entire audio score are generated procedurally in code (Web Audio API + HTML canvas), or assembled from the independently-licensed third-party assets credited below.
- This is a personal learning / art project made out of admiration for the original. It is offered free of charge, and nothing here is sold.

If you represent a rights holder and have any concern, please open an issue and it will be addressed promptly.

---

## ▶️ How to run it

The demo is a single `index.html`, but it loads JavaScript modules and image/model assets, so it **must be served over HTTP** — opening the file directly (`file://`) will not work.

**Option A — Python (already on most Macs/Linux):**
```bash
cd pt-sans
python3 -m http.server 8123
```
Then open **http://localhost:8123** in a modern browser (Chrome, Edge, Firefox, or Safari).

**Option B — Node:**
```bash
cd pt-sans
npx serve -l 8123      # or: npx http-server -p 8123
```

Then:
1. Click **"click to wake up"** — this grabs the mouse (pointer-lock) and starts the audio.
2. The cursor disappears; that's normal. Press **Esc** any time to release it.
3. Walk to the end of the hall. Keep going. Don't run — you can't anyway.

> 💡 Headphones strongly recommended. Half the horror is in the sound, and the jump scare has a sub-bass hit that laptop speakers will waste. Dim the lights.

---

## 🎮 Controls

| Input | Action |
| --- | --- |
| **W A S D** / arrow keys | Move (a deliberate, unhurried walk — no sprint) |
| **Mouse** | Look |
| **Click** (on title) | Start / lock pointer / enable audio |
| **Esc** | Release the mouse |

---

## 🩸 What happens

A first-person walk through an L-shaped corridor into a single room. Along the way: flickering lamps and a stuttering fluorescent over a black basement door, crooked period photographs (some with a face scratched out), a radio that murmurs if you lean in, and a house that knocks, scratches, breathes, and hums a lullaby when no one is there. A figure appears once down the hall — and then she doesn't. Reaching the room triggers a one-time jump scare and its quiet, worse aftermath.

It is a self-contained vertical slice: one hallway, one room, taken one step at a time.

---

## 🛠️ Tech

- **[Three.js](https://threejs.org/)** (r184) for WebGL rendering, vendored locally in `three-js/` (only the `build/` core and `examples/jsm/` addons that are actually imported).
- **Post-processing:** ground-truth ambient occlusion (GTAO), bloom, and a custom "grime" shader (chromatic aberration, animated film grain, scanlines, vignette).
- **Procedural everything:** all wall/floor/door textures are painted on `<canvas>`; the **entire soundtrack and every sound effect is synthesized live** with the Web Audio API (no audio files) — drone, footsteps, creaks, knocking, scratching, crying, a hummed lullaby, the jump-scare sting, and a convolution reverb to seat it all in the corridor.
- **Character:** a rigged figure from Adobe Mixamo, loaded via `FBXLoader`, re-textured in code into a pale spectre and dressed in a procedural nightgown, animated through the tease / scare / aftermath beats.
- No build step, no framework, no bundler. It's one HTML file and some assets.

---

## 🙏 Credits & third-party assets

The original code, level design, procedural textures, and procedural audio in this project are © 2026 Marc Andrew and released under the **MIT License** (see [`LICENSE`](LICENSE)). The third-party assets bundled in this repo are **not** covered by that MIT license and remain under their own terms:

- **Three.js** — © Mr.doob & contributors, [MIT License](https://github.com/mrdoob/three.js/blob/dev/LICENSE).
- **Character model & animations** — Adobe **[Mixamo](https://www.mixamo.com/)** ("Zombiegirl W Kurniawan" + motion clips), used under the Mixamo license. *(Provided here for the demo to run; not offered as a redistributable asset pack.)*
- **Photographs** (in `photos/`), sourced from **[Unsplash](https://unsplash.com/)** under the Unsplash License, courtesy of:
  - The Art Institute of Chicago
  - Museum of New Zealand Te Papa Tongarewa
  - Port Morien Digital Archive
  - Smithsonian Institution
  - The Cleveland Museum of Art
- **Inspiration** — *P.T.* by Hideo Kojima, Guillermo del Toro, Kojima Productions, and Konami. With gratitude and respect.

---

## 📄 License

Original work: **MIT** © 2026 Marc Andrew. Third-party assets retain their respective licenses as noted above. *P.T.*, *Silent Hill(s)*, and related marks are the property of Konami and are referenced here only for the purpose of homage and identification.
