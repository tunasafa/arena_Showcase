<div align="center">

# `ARENA`

**From a notebook sketch to a real-time 3D mobile game — the full development story**

<br>

An arena-based multiplayer fighting game where players push each other into holes, collect power-ups, and try to be the last one standing. Built from scratch — first as a browser prototype, then rebuilt as a native mobile app. **Now in Google Play Store Closed Testing with live online multiplayer!**

<br>

<img alt="Status" src="https://img.shields.io/badge/status-closed_testing-0A7F5A?style=for-the-badge">
<img alt="Phase" src="https://img.shields.io/badge/phase-google_play_closed_testing-3498db?style=for-the-badge">
<img alt="Multiplayer" src="https://img.shields.io/badge/multiplayer-online_live-7952b3?style=for-the-badge">
<img alt="Platform" src="https://img.shields.io/badge/platform-Android_%26_iOS-E94560?style=for-the-badge">

<br><br>

*This is the showcase repository — a visual timeline of how the game was made.*
*The development repo is private for now.*

<br>

<img src="docs/readme-assets/08-last-mobile-version-real-phone.png" alt="Arena mobile MVP running on a real phone" width="70%">

<br>

*The mobile MVP running on a real device. [See the latest update below.](#october-13-update)*

</div>

<br>

---

<br>

## `What Is Arena?`

**Arena** is a fast-paced physics-based game. You control a player on a circular arena full of holes. Your goal: push everyone else into those holes using dash attacks and power-ups, while avoiding falling in yourself.

The game has two modes:

- **Push Arena** — Free-for-all chaos. Push opponents into holes. Pick up perks like Speed Boost, Mega Push, Shield, Invincible, and Magnet. Last player standing wins.
- **Iso Arena** — A more strategic turn-based variant with puck mechanics and a different camera angle.

Both modes support solo play against AI bots and **live native online multiplayer**. Online matches run on a fixed-tick, server-authoritative simulation over WebSockets with 60 Hz input sampling and MessagePack v2 delta snapshots.

<br>

---

<br>

## `The Development Story`

This section tells the journey chronologically — from the first rough idea to the current mobile version. Each step shows what changed, what was learned, and what mistakes led to the next improvement.

<br>

---

### `Stage 01` — The Sketch

<img src="docs/readme-assets/03-sketch.png" alt="The first sketch of the arena game concept" width="100%">

**Every game starts somewhere.**

This was it. A rough sketch on paper — a circular arena, some holes around the edge, players in the middle.

There was no code yet, no engine, no tech decisions. Just an idea: *"what if you had to push other players into holes?"*

Looking back, the sketch was surprisingly close to what the game became. The circular shape, the hole placement around the perimeter, the center hub — all of that survived into the final version. Sketching first saved a lot of aimless coding later.

<br>

---

### `Stage 02` — First Concept Trial

<img src="docs/readme-assets/02-first-concept-trial.png" alt="First digital concept trial" width="100%">

**Does this actually work?**

The first real attempt to see if the idea had legs. Still extremely rough — no real physics, no polish, just shapes on a screen.

But this answered the most important question: **does the core loop feel fun?** Moving around an arena and trying to knock things into holes — does that have any pull?

It did. That was enough to keep going.

**Lesson learned:** Some ideas feel great in your head but fall apart the moment you actually try them. Testing the concept early, even ugly, filters out the dead ends fast.

<br>

---

### `Stage 03` — First 3D Web Version

<img src="docs/readme-assets/01-first-3d-web-version.png" alt="First 3D browser version of the arena" width="100%">

**It suddenly felt like a real game.**

This was the turning point. Moving from flat concept to a 3D browser game made everything click. You could see the arena from above, watch players move, and feel the physics.

The browser was chosen deliberately — no app store, no build tools, no compile step. Just open a file and play. That speed of iteration mattered more than anything else at this stage.

**Mistake made here:** The first version used neon-heavy visuals with glowing lines everywhere. It looked "cool" at first but quickly became hard to read during gameplay. Visual noise is not good design. This got fixed later.

**Tech that made this possible:**

| What | Why |
|------|-----|
| Three.js | 3D rendering in the browser — no Unity, no downloads, just WebGL |
| Matter.js | 2D physics engine for collisions, pushing, and hole detection |
| Vanilla JS | No framework overhead, just raw game loop control |

<br>

---

### `Stage 04` — Web UI Gets Serious

<img src="docs/readme-assets/04-ui-improved-mvp-on-web.png" alt="Improved web UI" width="100%">

<img src="docs/readme-assets/05-example-new-ui.png" alt="Example of the new UI direction" width="100%">

Once the gameplay worked, the next problem became obvious: **the game looked like a prototype**.

The UI was confusing, the menus were afterthoughts, and nothing felt intentional. This stage was about making the game look like something you'd actually want to play — not just something a developer was testing.

The lobby system, game mode selection, and visual hierarchy all got redesigned. The arena itself evolved too — from flat neon lines to a chunky **rustic industrial** style with iron plates, bolt studs, golden rim accents, and dark metal collars around every hole. Each hole now has a physical depth shaft instead of just a colored circle.

> **Key realization:** A game isn't just mechanics. If people can't instantly read what's happening on screen, the feel breaks — even when the physics are perfect underneath.

<br>

---

### `Stage 05` — Going Mobile: First Menus

<img src="docs/readme-assets/06-first-mobile-menu.png" alt="First mobile menu design" width="100%">

<img src="docs/readme-assets/07-first-mobile-menu-2.png" alt="Second iteration of mobile menu" width="100%">

This is where the real challenge started. Moving to mobile wasn't a "resize the browser window" situation. It meant rebuilding the entire rendering pipeline, input system, and navigation from the ground up.

The game engine had to be rewritten in TypeScript. The 3D rendering had to go through `expo-gl` (OpenGL ES on the phone's GPU) instead of browser WebGL. Touch controls had to replace keyboard input — a virtual joystick for movement, dedicated buttons for push and dash.

**The first mobile menus looked rough.** But they worked. And they proved the core game could run at playable frame rates on a real phone.

**Tech stack for mobile:**

| What | Why |
|------|-----|
| React Native + Expo | Cross-platform native app without writing Swift/Kotlin separately |
| expo-gl + expo-three | Bridge between Three.js and the phone's native OpenGL context |
| Matter.js | Same physics engine — reused from the web version |
| TypeScript | Type safety across a growing codebase with complex game state |
| React Navigation | Screen flow between menus, lobby, and game modes |

<br>

---

### `Stage 06` — The Graphics Search

<img src="docs/readme-assets/10-mobile-version-graphics-improvement-search.png" alt="Experimenting with mobile graphics improvements" width="100%">

**Finding the right look.**

This was the messy middle of development. The game worked, but it didn't look *right* yet on mobile.

A lot of time went into trial and error here — different arena materials, lighting setups, player model styles. The original cylinder player models got replaced with **procedural robot ball models** (sphere body, accent ring, glowing lens, side panels). Each player got unique ornament themes like Cyclops, Tri-Eye, and Armored.

The arena aesthetic shifted from neon to a grounded **rustic industrial** look — worn iron plates, bolted seams, raised metal collars around holes, golden divider lines between sectors.

**Biggest lesson here:** Graphics iteration feels slow and unproductive compared to adding features. But it's what makes people actually *want* to play your game.

<br>

---

### `Stage 07` — Mobile MVP & Closed Testing

<img src="docs/readme-assets/08-last-mobile-version-real-phone.png" alt="Mobile MVP running on a real phone" width="100%">

<img src="docs/readme-assets/09-last-version-mobile-2.png" alt="Mobile MVP gameplay" width="100%">

<img src="docs/readme-assets/11-last-version-mobile-1.png" alt="Mobile MVP arena view" width="100%">

**The first mobile closed-testing milestone.**

It runs on real phones. The arena looks intentional. The physics feel responsive. The touch controls work. The AI opponents put up a real fight. And the visual identity — the dark industrial arena with golden accents, glowing perks floating above the surface, robot ball players casting shadows on worn iron — finally feels coherent.

**What this milestone included:**

- Two game modes — Push Arena (free-for-all) and Iso Arena (turn-based strategic)
- AI opponents with configurable difficulty and behavior patterns
- Perk system — Speed Boost, Mega Push, Shield, Invincible, Magnet
- Touch controls — virtual joystick + action buttons with cooldown feedback
- Procedural 3D arena with rustic industrial aesthetic
- Player models with unique themed ornaments
- **Live online multiplayer** — Native Socket.IO + MessagePack v2 binary WebSocket transport with server-owned 60 Hz simulation, delta snapshots, 60 Hz input sampling, room codes, and 90-second reconnection grace period
- **Google Play Store Closed Testing** — Playable on Android devices with production release signing and integrated Firebase Crashlytics

<br>

---

<a id="october-12-update"></a>

### `Stage 08` — New Worlds · October 12, 2026

Today's mobile update adds **three low-poly maps to both Push Arena and Iso Arena**, keeping the original Ironworks arena available:

- **Floating Farm** — Six animal players on a thinner, textured rock island with decorative cracks, wooden fences, and deep holes.
- **Dodgem Nights** — Six detailed bumper cars, grounded traffic barriers, and a simple dark background.
- **Tidal Harbor** — Six ships inside a circular stone harbor, with swirling water holes, shoreline rocks, cargo, a lighthouse, and a light coastal background.

Animals, cars, and ships are larger and more detailed; the original ball players keep their visual size. Player discs are gone: Iso shows your ring only on your turn, while Push shows only your own player indicator. Gameplay now blocks swipe-back and includes pause controls to resume, restart solo matches, or leave. An Expo iPhone rendering crash was also fixed.

*Development renders of the latest mobile scenes, with the gameplay HUD hidden.*

**Map 02 — Floating Farm**

<img src="docs/readme-assets/12-floating-farm.png" alt="Floating Farm: six animals on a textured circular rock island with wooden fences and deep holes" width="100%">

**Map 03 — Dodgem Nights**

<img src="docs/readme-assets/13-dodgem-nights.png" alt="Dodgem Nights: six colorful bumper cars on a circular arena surrounded by traffic barriers" width="100%">

**Map 04 — Tidal Harbor**

<img src="docs/readme-assets/14-tidal-harbor.png" alt="Tidal Harbor: six ships on rippling water with whirlpool holes, stone harbor walls, a lighthouse, and a crane" width="100%">

<br>

---

<br>

<a id="october-13-update"></a>

### `Stage 09` — The Playable Overhaul · October 13, 2026

Playtesting showed matches were either over in seconds or dragged on forever. This update rebuilds the power-ups, the bots and the match pacing, then refreshes the menus and two arenas. **Android 1.0.2 (build 10)** carries it to closed testing.

<img src="docs/readme-assets/15-stage-09-overview.png" alt="Stage 09 overview: new Push and Pull mode cards, all five arena cards, and headline numbers" width="100%">

| | What changed |
|---|---|
| ⚡ **Power-ups** | **AUTO** items apply on pickup; **USE** items stack (up to 3) and fire oldest-first from one button. 18 in total, 5 brand new. |
| 🤖 **Bots** | One steady skill level all match. They hunt rivals near pits and follow the same rules as players. |
| ⏱️ **Pacing** | Sudden death: pits start pulling after 40 s (Push) or from round 5 (Pull). No more stalemates. |
| 🌐 **Online** | The same rulebook runs on the server (protocol v3), so online and solo play identically. |
| 🎨 **Look** | Restyled in-game controls, tighter camera framing, light themed skies on every map, a cleaner **Ironworks** and a robot-workshop **Rivet Foundry**. |
| 🔋 **Efficiency** | ~23 estimated draws per 6-player scene (143 in 1.0.1); a rematch texture leak fixed before release. |

<img src="docs/readme-assets/16-stage-09-power-ups.png" alt="Power-up rework: Push Arena's 8 and Pull Arena's 10 power-ups grouped into AUTO and USE" width="100%">

<br>

---

<br>

## `Under the Hood`

The game isn't built on a commercial engine. Everything from the physics loop to the arena geometry is hand-wired. Here's why the tech choices matter:

| Layer | Tech | Why This Choice |
|-------|------|-----------------|
| **3D Rendering** | Three.js / expo-three | Lightweight enough for mobile GPU. No asset pipeline needed — all geometry is procedural. |
| **Physics** | Matter.js | 2D physics projected into 3D space. Simpler than a full 3D physics engine, and the arena's top-down gameplay doesn't need the Z-axis for collisions. |
| **Mobile App** | React Native + Expo | Single codebase for iOS and Android. Expo handles native modules (GL context, screen orientation, fonts) without manual linking. |
| **Multiplayer** | Socket.IO + MessagePack (protocol v3) | Server-authoritative Node.js simulation validating player inputs, broadcasting delta snapshots, and preventing desyncs or cheating. |
| **Language** | TypeScript | Type safety across 30+ game files with shared state, physics bodies, and Three.js objects. |

### Why It Performs Well on Mobile

Mobile performance was a real battle. Early versions stuttered badly. Here's what was done to fix it:

- **Geometry merging** — Complex player models use shared geometry instances instead of creating new ones per frame
- **Object pooling** — Particles, perks, and effects reuse pre-allocated objects instead of creating garbage for the GC to clean up
- **Capped particle counts** — Hard limit of 150 particles on mobile (down from 250 on web)
- **Shared materials** — Bolt heads, arena segments, and repeated geometry all reference the same material instances
- **Disposal helpers** — Every Three.js object has explicit cleanup to prevent GPU memory leaks
- **React bridge optimization** — Game state updates are batched to avoid flooding the React Native bridge with re-renders

None of this is overengineering. The arena is a controlled, compact space — so the optimization strategy is about being disciplined with the small things rather than building a massive engine.

<br>

---

<br>

## `What Was Learned Along the Way`

Building this game taught real lessons — not from tutorials, but from hitting walls and figuring a way through.

| Lesson | How It Was Learned |
|--------|-------------------|
| **Sketch before you code** | The paper sketch saved weeks of building the wrong thing |
| **Ugly prototypes are more valuable than pretty plans** | The first concept trial looked terrible but proved the idea had potential |
| **Neon does not equal good game visuals** | The early glowing line aesthetic looked flashy but made gameplay unreadable |
| **Mobile is a different platform, not a smaller screen** | Touch controls, memory limits, and GPU constraints required a full rethink |
| **Physics tuning is game design** | Push force, dash cooldown, max speed — changing these by small amounts completely changed how the game felt |
| **Mistakes are just earlier versions** | The neon arena to rustic arena transition only happened because the first approach failed |
| **Graphics polish isn't optional** | Players judge a game in the first 2 seconds. The visual overhaul is what made the game presentable |

<br>

---

<br>

## `Project Status`

**Arena is currently in closed testing on the Google Play Store!** The native mobile app is now playable online with real-time multiplayer powered by our authoritative cloud infrastructure.

The current build is:

- **Live in Google Play Closed Testing** — Playable on real Android devices with signed `.aab` builds and active testers
- **Online multiplayer live** — Server-authoritative Node.js simulation hosted on GCP with Caddy auto-SSL, MessagePack binary protocol v3, 60 Hz input sampling, and instant reconnection
- **Visually polished & performant** — 60 FPS target via Three.js / Expo GL with static geometry batching, procedural marble textures, and adaptive resolution scaling
- **Production telemetry** — Integrated Firebase Crashlytics with native Android NDK crash monitoring
- **Open for feedback** — Active testing and tuning underway before open track and App Store releases

### What's Next

- ~~Bringing the WebRTC multiplayer to mobile (currently web-only)~~
  - **Done:** Shipped native real-time online multiplayer using a fixed-tick server-authoritative architecture (Node.js on GCP with Caddy auto-SSL, Socket.IO + MessagePack v2 binary serialization, 60 Hz input sampling, 20 Hz delta snapshots, and 90-second reconnect handling).
- ~~App store preparation and beta testing~~
  - **Done:** Reached the **Google Play Store Closed Testing** phase! Built production-signed AAB packages via EAS, set up store assets and privacy policy, and launched the closed testing track on Google Play Console.
- ~~Continued visual polish and new player model themes~~
  - **Done:** Completed mobile rendering optimizations including static geometry batching, procedural marble ball shaders, instanced particle pooling, compressed sound assets, and adaptive quality recovery for high-refresh screens. The latest mobile development build also adds animal, bumper-car, and ship models with three matching arenas.
- ~~Deeper, fairer gameplay~~
  - **Done:** Reworked power-ups into AUTO and USE items with a 3-slot stash, steady-difficulty bots, and sudden death in both modes — shared by solo and the multiplayer server (see [Stage 09](#october-13-update)).
- Scoring, progression, and match history
- More game modes and arena variations

<br>

---

<br>

## `Open for Contributions`

If any of this interests you — whether it's gameplay ideas, UI/UX feedback, physics tuning, performance suggestions, or just testing and reporting bugs — this project is open for it.

The game was built solo so far, learning by doing. Outside perspectives would be valuable at this stage.

<br>

---

<div align="center">
  <br>

  **`ARENA`**

  *From sketch — concept — browser prototype — mobile closed testing*

  *Still going.*

  <br>
</div>
