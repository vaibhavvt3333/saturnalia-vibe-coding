# SKYLINE: AIRLIFT — Emergency Drone Operations

A complete, original, no-install browser game created for **Saturnalia 2026 Vibe Coding** by **Team Pirates**.

## Play

1. Open **`index.html`** in any modern browser, or use the deployed site.
2. Click **BEGIN OPERATION**.
3. Use **WASD** or **arrow keys** to pilot the drone.
4. Fly to the **cyan supply depot**. Press **Space** or **E** to pick up cargo.
5. Follow the guidance line to the **amber rescue station**. Press **Space** or **E** to deliver.
6. Repeat until every delivery is complete. Finish all three sectors to save the city.

### Controls

| Control | Action |
| --- | --- |
| WASD / Arrow keys | Fly the drone |
| Space / E | Pick up or drop cargo |
| Shift | Boost (uses extra battery) |
| P / Escape | Pause / resume |
| On-screen buttons | Touchscreen controls |
| SOUND ON/OFF | Toggle synthesized sound |

## Game mechanics

- **3 story-driven sectors**, progressively tougher flight conditions.
- **Cargo pickup-and-drop mechanic** with proximity detection and mission markers.
- **Rescue objectives**: deliver 2, 3, and 3 cargo packages in successive sectors.
- **Win / loss conditions**: mission timer, drone battery, hull integrity, and overall victory.
- **Flight physics**: acceleration, momentum, wind, speed boost, building collisions, and turbulence hazards.
- **Recharge mechanic**: hover at the cyan depot between deliveries to refill battery.
- **Score system**: earn points from deliveries, remaining time, and drone condition; local high score.
- **Atmosphere**: animated city, moving rain, rotors, spotlights, beacons, particles, camera tracking, and procedurally synthesized sounds.
- **Mobile and desktop controls**. No libraries or external assets required.

## Technical stack

- HTML5, CSS3, vanilla JavaScript
- HTML5 Canvas 2D rendering
- Web Audio API (synthesized sound effects)
- LocalStorage (optional best score)
- No external dependencies, API keys, or installation

## Run locally

Double-click `index.html`, or serve this directory with `python -m http.server 8000` and visit `http://localhost:8000`.

## Deploy

**Vercel**: Import your public GitHub repository, choose **Framework Preset: Other** (static site), leave Build Command empty, and Deploy. `index.html` at repository root is served as the homepage.

**GitHub Pages**: Repo Settings → Pages → Deploy from branch → `main`, `/ (root)`.

## Competition requirements

| Requirement | Implementation |
| --- | --- |
| Controllable drone | Momentum-based player drone |
| Cargo + target | Supply depot pickups, rescue zone drops |
| Score, timer, win/lose | All three, plus battery, hull, multi-stage victory |
| Browser directly from repo | Single standalone `index.html` |
| Readable README | This file |

## Credits

Concept, art, and code assembled for Team Pirates during the competition. Graphics are programmatic canvas drawings; audio is procedurally generated. No copyrighted third-party assets.
