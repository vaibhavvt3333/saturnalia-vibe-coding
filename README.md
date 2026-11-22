# SKYLINE: AIRLIFT V3 — Drone Fleet & Physics Update

**Team Pirates · Saturnalia 2026 · Vibe Coding**

A zero-install, self-contained HTML5 Canvas game. Pilot one of three drones across a colorful 2D sunset city and a long industrial obstacle course, collect rescue cargo on a rooftop, and deliver it to distant stations. All HTML, CSS, JavaScript, graphics and locally synthesized effects are inside **`index.html`**. No npm, external CDNs, keys or framework required.

## Start / Play

Open [`index.html`](index.html) in any modern browser (desktop or phone), or launch the deployed Vercel site. On the start screen, **select a drone** from the hangar, then press **BEGIN OPERATION**. The drone can be switched after completing each sector, before starting the next.

| Control | Keyboard | Mobile |
|---|---|---|
| Fly / land / lift off | **WASD** or **Arrow Keys** | D-pad |
| Pick up another crate at cyan rooftop / drop one at golden pad | **Space** or **E** | PICK / DROP |
| Boost | **Shift** | BOOST |
| Pause / resume | **P** / **Esc** | Pause button |
| Audio | Sound button | Sound button |

**Pickup:** Hover near the cyan rooftop marker and press **Space**. For a drone with spare capacity, press **Space** again to collect more crates (until all remaining shipments are loaded or the cargo bay is full). Follow the route marker to the next golden pad, press **Space** there to deliver **one crate**, and continue to the next station with any remaining crates.

## Drone selection and practical capacity

| Airframe | Capacity | Flight behavior | Heavy gold shipment |
|---|---|---|---|
| **Aero-Scout** | 1 crate | Agile acceleration and maximum top speed; lower armor/battery | Can carry 1, but speed and thrust are reduced |
| **SAT-04 Industrial** | 2 crates | Balanced flight; stable hover; medium armor/battery | One heavy crate occupies both cargo slots |
| **Titan Heavy-Lifter** | 3 crates | Slower but more armored and larger battery | Heavy shipments do not cause additional slowdown |

All airframes are visually different; their maximum speed, acceleration, hull durability, flight stability, battery capacity, cargo slot capacity and heavy-cargo penalty are wired into simulation state. The top HUD displays **current cargo load / drone capacity**. Heavy gold crates consume two slots on SAT-04, so `1/2 · FULL` means one heavy crate has filled both slots.

## Physics update

- **AABB minimum translation vector (MTV)** resolution for drone collisions with buildings, walls, gantries, silos, gate frame and gates. Collisions separate along the least-penetration face.
- **Circle-vs-rectangle MTV** for individually tethered cargo crates, plus circle/capsule separation for rotating blades, hooks and security drones.
- Inward speed produces a **0.45-restitution bounce** along the contact normal; no hidden 'controls disabled on hit' state.
- Separate **0.2-second hit-damage cooldown**, collision sparks, screen shake, damage meters and sound.
- Ground is resolved with a specific floor clamp (`groundY - droneHalfHeight - clearance`), zeroing **only downward** velocity. Up thrust and sideways scooting remain available at all times.
- **Several physics substeps per frame** guard against fast bodies passing through thin obstacles. Multiple carried cargo objects have individually simulated spring tethers.

## Levels & moving hurdles

1. **Sunset Supply Run:** 2 standard supply deliveries, stationary infrastructure, rooftop pickup.
2. **Crosswind Crossing:** 3 fragile deliveries; moving vertical gate and spinning wind-turbine blades.
3. **Last Light Rescue:** 3 heavy gold deliveries; faster turbine, moving gate, swinging crane hook and horizontally patrolling security drone, with stronger crosswinds.

The industrial route features warning stripes, blinking lights, towers, overhead gantries, and a minimap/progress bar. Full 3-sector success earns a win screen and saved local best score. Timer, battery, hull and cargo integrity create fail conditions.

## Source and deployment

Repository: https://github.com/vaibhavvt3333/saturnalia-vibe-coding

Live site (after committing updated files): https://saturnalia-vibe-coding.vercel.app

To update the existing project:

1. On the GitHub repository click **Add file → Upload files**.
2. Upload **`index.html`** and **`README.md`** from this folder; replace the older files.
3. Click **Commit changes** on the `main` branch. Vercel is already linked and automatically rebuilds from the new commit. No need to create another Vercel project.

If the old game remains visible, hard refresh (**Ctrl + Shift + R**).

## Verification

Chromium smoke tests covered 3 hangar choices, 2-crate and 3-crate loading, heavy gold slot restrictions, pickup and individual drop interactions, all 3 missions to the victory screen, physical floor liftoff, AABB wall separation with a 0.45 bounce, and crate collision separation. Desktop and mobile layouts were checked, with no page JavaScript exceptions in those tests.

Original competition project for **Team Pirates**, created using AI-assisted coding.
