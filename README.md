# NEON RUN

A neon-styled 2D platformer where you navigate a futuristic grid, stomp enemies, collect orbs, and fight an Overlord boss — all in a single HTML file.

---

## How to Play

Open `platformer.html` in any modern browser. No install needed.

**Goal:** Collect every orb on a level to advance. Survive all 10 levels, then defeat the Overlord boss on Level 10.

**Controls**

| Action | Keys |
|---|---|
| Move | Arrow Keys or WASD |
| Jump | ↑ / W / Space |
| Double Jump | Jump again mid-air |
| Stomp enemy | Land on top of them |
| Pause / Exit | ■ EXIT button (top-right) |

On mobile/touch: use the on-screen D-pad (◀ ▶ ▲). Rotate to landscape for the best experience.

---

## Features

- **10 levels** across unique themed worlds (The Grid, Descent, Towers, Zigzag, The Void, Labyrinth, Stairway, Gauntlet, Chaos, The Summit)
- **Boss fight** on Level 10 — the Overlord floats, fires projectiles, and enters Rage Mode at half HP
- **Secret Level 11 — Hacker Mode** — unlocked by defeating the boss in under 10 seconds; harder enemies, green matrix aesthetic, and a remixed track
- **6 power-ups** that spawn on platforms each level:
  - ⚡ Speed Boost, 🛡 Shield, △ Triple Jump, ★ Score ×2, ↘ Shrink Enemies, ◉ Coin Magnet
- **Combo system** — collect orbs and stomp enemies in quick succession for score multipliers (up to ×4)
- **Procedural audio** — fully synthesized music (normal, boss, hacker tracks) and SFX using the Web Audio API; no audio files required
- **Pixel-art astronaut sprite** — animated idle, walk, jump, and fall states with jet boot flames
- **3 save slots** (World α, β, γ) with auto-save every 10 seconds
- **2-player co-op** over WebRTC via PeerJS — one player hosts, the other joins with a 4-letter room code; both must clear orbs before advancing
- **17 achievements** tracked in localStorage (stomps, combos, power-up collection, speed kills, and more)
- **Difficulty settings** — Easy, Normal, Hard (affects enemy speed)
- **Fullscreen support** — Ctrl+F or F11

---

## Cheat / Admin Controls

These are built in for testing:

| Shortcut | Effect |
|---|---|
| Ctrl+3 | Level warp menu |
| Ctrl+6 | Instantly kill the active boss |
| Ctrl+7 | Restore lives to 10 |

---

## Settings

Accessible from the start screen:

- Music and SFX volume sliders (independent)
- Music / SFX on/off toggles
- Difficulty: Easy / Normal / Hard
- Particle effects on/off

---

## Technical Notes

- Single `.html` file — no build step, no server required
- Multiplayer uses [PeerJS](https://peerjs.com/) (loaded via CDN) with Google STUN servers and a public TURN relay for NAT traversal
- Save data and achievements stored in `localStorage`
- Scales to fit any screen size; mobile portrait shows a rotate-device prompt

---

## Scoring

| Action | Points |
|---|---|
| Collect orb | 10 (×combo multiplier, ×2 with Score power-up) |
| Stomp enemy | 25 (×combo multiplier) |
| Stomp boss | 50 per hit |
| Defeat boss | 500 bonus |
| Complete level | 100 × level number |

Combo multipliers: ×2 at 3 combo, ×3 at 5, ×4 at 8+
