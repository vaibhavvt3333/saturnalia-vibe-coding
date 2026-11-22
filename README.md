# SKYLINE: AIRLIFT V4 — Four-Sector Rescue Campaign

**Team Pirates · Saturnalia 2026 · Vibe Coding**

A polished single-file 2D HTML5 Canvas drone-delivery game featuring four distinct sectors, a drone selection hangar, cargo physics, MTV obstacle collisions, procedural Web Audio, moving industrial hurdles, and NPC air traffic. **No installation, assets, CDN, API keys, backend, or build tools required.** Everything used by the game is contained in `index.html`.

## Play

Open [index.html](index.html) in a modern browser, or visit the [live Vercel site](https://saturnalia-vibe-coding.vercel.app) once the latest commit has deployed. Click **BEGIN OPERATION** after choosing a drone. Complete each delivery and advance to the next sector.

| Action | Desktop | Touch screen |
|---|---|---|
| Fly horizontally and vertically | WASD / Arrow keys | Onscreen directional pad |
| Pick up one crate / deliver one crate | Space / E | PICK / DROP |
| Boost | Shift | BOOST |
| Pause | P / Esc | Pause button |
| Sound | SOUND ON / OFF button | Same button |

At the **cyan rooftop depot** hover near the pad and press Space to magnetically attach cargo. Multiple pickups are permitted up to capacity. Fly to the next **golden rescue pad**, then press Space to release one crate. The minimap strip, objective prompt and HUD guide you.

## Four progressively harder sectors

| Sector | Atmosphere & map | Deliveries | Traffic NPCs | Hazards |
|---|---|---:|---:|---|
| 1 — OPEN AIRSPACE | Warm clear sunset; low-rise city, sparse ground obstacles | 2 | 3 | Gentle natural wind, basic barriers |
| 2 — CROSSWINDS & HEAVY CELLS | Blue-purple squalls with wind streaks and storm-cell clouds | 3 | 6 | Gust channels, active sliding gate, spinning rotor, storm displacement |
| 3 — URBAN CANYON | Copper-purple city skyline, taller towers, narrow building corridors | 3 | 9 | Dense buildings, turbine, gates, swinging crane, more scouts |
| 4 — NIGHT STORM & TURBULENCE | Midnight-blue sky, radial spotlight/radar halo, rain and lightning | 4 | 13 | Highest traffic, fierce gusts, 3 storm cells, flying hooks and extra obstacles |

Each new sector has different buildings / course geometry, its own color palette, weather fields, enemy traffic density, and level timer. A **1.5-second glass HUD banner** announces the new sector. Players have **1.5 seconds of damage invulnerability** upon spawning; collision separation still functions during the shield.

## NPC air traffic

Three independently animated drone types: (1) **Patrol**: red security drones scan back and forth along luminous travel lanes; (2) **Cargo**: large yellow transport drones with slower movements; (3) **Scout**: quick teal drones weaving in two axes, introduced in sector 2. All are solid circle-collision moving obstacles with explicit movement velocities and bounce separation. There are blinking navigation lights and tilt animations. Approaching traffic can trigger warning beeps, while moving quickly past an NPC without touching it earns a small near-miss reward.

## Wind and storm physics

Weather applies acceleration forces that vary by time and world position. Lateral crosswind zones feature animated wind streaks and directional signs. Large storm cells apply oscillating turbulent forces in both X and Y, and come with distinct visuals. The final level adds irregular turbulence, rain, periodic lightning, a dark ambient palette and a drone-centered radar/spotlight gradient.

## Drone hangar and physics

| Drone | Slots | Specialty |
|---|---:|---|
| Aero-Scout | 1 | Fast/light but slowed by heavy gold |
| SAT-04 Industrial | 2 | Balanced and stable; one heavy gold crate uses two slots |
| Titan Heavy-Lifter | 3 | Slowest but most armored, best battery and no heavy gold penalty |

The game retains substepped **AABB minimum-translation-vector collision separation**, independent circle-vs-AABB resolution for hanging cargo, circle/capsule collision handling for turbines/hooks and NPC drones, 0.45 bounce restitution, a 0.2-second hit-damage cooldown and ground takeoff without controls locking. Rotor hum and storm whoosh are continuous procedural Web Audio signals; collecting, deliveries, near misses, proximity warnings, impacts, sector transitions and lightning have synthesized cues. Mute affects all audio. Audio activation occurs after a user interaction, as required by modern browsers.

## How to update this competition repository

Repository: https://github.com/vaibhavvt3333/saturnalia-vibe-coding

1. In the repo, choose **Add file → Upload files**.
2. Upload the new `index.html` and `README.md`, replacing the old versions, and click **Commit changes**.
3. GitHub is already connected to Vercel. The live site will automatically redeploy: https://saturnalia-vibe-coding.vercel.app
4. To bypass an old cached version, hard refresh (**Ctrl + Shift + R**).

### Source layout

- `index.html` — all game mechanics, visuals, UI and procedural audio in one self-contained file.
- `README.md` — gameplay instructions and technical overview.

The code includes an optional `window.__skylineTest` interface solely for deterministic browser smoke tests; it doesn't affect gameplay.

## Verification

Automated Chromium checks verify all 4 sector definitions and transitions; levels with 3, 6, 9 and 13 AI drones; cargo pickups and deliveries (12 total) through victory; NPC collision push-out; the 1.5-second invulnerability and transition banner; drone selection; ground liftoff; mute/unmute; and desktop/mobile rendering. No JavaScript exceptions were observed during testing. Run the project on modern Chromium, Firefox, or Safari for regular play.
