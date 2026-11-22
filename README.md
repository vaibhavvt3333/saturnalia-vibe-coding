# SKYLINE: AIRLIFT — Sunset Rescue Run

**Team Pirates · Saturnalia 2026 Vibe Coding Competition**

A complete 2D **side-view drone pickup-and-drop browser game**. Lift emergency cargo from a rooftop in a small sunset city, fly across a long industrial course, clear dangerous machinery, and deliver to glowing rescue landing pads before your timer or integrity runs out.

## Play

**Online:** Open the Vercel deployment linked to this GitHub repository.

**Offline:** Open `index.html` in any modern desktop or mobile browser. The game is self-contained, without dependencies, accounts, external assets, a build process, or an installation step.

Click **BEGIN OPERATION** to start.

### Controls

| Action | Keyboard | Touchscreen |
|---|---|---|
| Move / fly | `W A S D` or arrow keys | On-screen directional pad |
| Pick up / deliver cargo | `Space` or `E` | **PICK / DROP** |
| Speed boost | Hold `Shift` | Hold **BOOST** |
| Pause / resume | `P` or `Esc` | Pause button |
| Toggle sound | Sound button | Sound button |

At the start of each mission, hover over the **bright cyan city rooftop pad** and press **Space/E**. A physical crate hangs below the drone on a dynamically swinging cable. Follow the amber beacon **east** across the course. Descend toward the golden **drop-off landing pad**, then press **Space/E** to deliver. Fly back to the city to collect each remaining package.

## Game mechanics

- **Wide side-scrolling world:** A ~4,580-unit horizontal level, with smooth camera easing and velocity-aware look-ahead.
- **High-visibility sunset scene:** Layered blue, lavender, pink and orange sky, luminous sun, parallax clouds, distant mountains/city silhouette, and warm illuminated windows.
- **Small city:** Distinct rooftops, rooftop water tower, lit city buildings, streetlamps, trees, paved road, and a clearly identified pickup platform.
- **Long terrain corridor:** Concrete barriers, antenna towers, massive overhead gantry, silos, turbines, gated machinery and crane rigging. Warning stripes and beacons make hazards visible.
- **Accurate physical obstacles:** Separate collision checks for drone fuselage and rotor guards, as well as the carried swinging crate. Solid buildings, ground, walls, towers, gantries, silos and industrial equipment cannot be passed through.
- **Damage feedback:** Sparks, screen shake, red flash and audio indicate collisions. Impacts reduce Hull and/or Cargo Integrity.
- **Three increasingly challenging missions:** Stationary hurdles first; rotating turbines and a moving gate second; a swinging crane hook and stronger crosswinds last.
- **Clear win/lose goal:** Timed deliveries, scoring, bonus points, battery and hull resources, cargo-integrity requirement, mission-clear screens, final victory report, and locally saved high score.
- **Responsive mobile support:** Fully playable touchscreen D-pad, pickup/drop and boost buttons.
- **Top route-progress tracker:** Shows the drone's distance from the city toward the far end of the rescue corridor.

## Missions

| Sector | Mission | Deliveries | Additional challenge |
|---|---|---:|---|
| 1 | Sunset Supply Run | 2 | Stationary hurdles, fixed turbine, gate and crane hook |
| 2 | Crosswind Crossing | 3 | Live rotating turbine, oscillating barrier gate |
| 3 | Last Light Rescue | 3 | All previous hazards, swinging crane hook, stronger wind |

There are **8 package deliveries total** across the 3 sectors.

## Repository and deployment

The entire playable application is in **`index.html`** (HTML, CSS, Canvas rendering, vanilla JavaScript). No framework or build script is required.

1. Replace the old `index.html` in this repository with the new one (or drag it onto **Add file → Upload files**).
2. Replace `README.md` with this file.
3. **Commit changes** to the `main` branch.
4. Vercel automatically deploys the updated site from the GitHub commit. Use **Other / No framework** if Vercel asks.

**No game data is sent to a server**. The personal-best score uses the browser's local storage. Audio is generated locally with Web Audio after a player interaction.

## Verification

The implementation has been smoke-tested in Chromium on desktop and mobile (no page JavaScript errors), verified for pickup and crate collision response, and exercised programmatically through all eight deliveries, all three mission transitions and the final victory state.

Original project made for **Saturnalia 2026** by **Team Pirates**, with AI assistance.
