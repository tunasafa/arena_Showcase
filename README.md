# Arena Showcase

<div align="center">
  <h1>ARENA SHOWCASE</h1>
  <p><strong>A visual development story from first sketch to mobile MVP</strong></p>
  <p>
    This repository is the public showcase page for the ARENA game project:
    a timeline of experiments, mistakes, improvements, and the current prototype state.
  </p>
  <p>
    <a href="https://github.com/tunasafa/arena">Main Game Repository</a>
  </p>
  <p>
    <img alt="Showcase Repo" src="https://img.shields.io/badge/repo-showcase-E94560">
    <img alt="Project Status" src="https://img.shields.io/badge/project-ongoing-F59E0B">
    <img alt="Current Phase" src="https://img.shields.io/badge/current%20phase-mobile%20MVP-0A7F5A">
  </p>
</div>

> This is not the full development repository. This is the presentation page for the project journey so far.

## What This Showcase Is

ARENA started as a rough game idea, then became a 3D browser prototype, and later evolved into a mobile version that is now strong enough to present publicly as an MVP/prototype.

This page shows the visual path of the project: how it started, how it changed, what improved, and what was learned while building it.

## Project Status Today

The game is still in active development.

It is not presented as a finished product. It is presented because it has now reached a meaningful prototype stage:

- playable
- visually much more coherent than the first versions
- technically structured enough to continue building on
- ready for feedback, testing, contribution ideas, and iteration

## Current State First

<img src="docs/readme-assets/08-last-mobile-version-real-phone.png" alt="Current mobile version shown on a real phone" width="100%">

This is the current state of the project today.

The game is still ongoing, but it has now reached a mobile MVP/prototype phase that is strong enough to present publicly.

## Main Repository

The actual game development repository is here but it is private for now:

**[github.com/tunasafa/arena](https://github.com/tunasafa/arena)**

This showcase repository exists to tell the development story in a clearer and more visual way.

## Development Story

### 1. The sketch stage

<img src="docs/readme-assets/03-sketch.png" alt="Sketch" width="100%">

Everything started from a simple sketch.

The goal here was not polish. It was to test the core idea early and keep the scope small enough to build.

### 2. First concept trial

<img src="docs/readme-assets/02-first-concept-trial.png" alt="First concept trial" width="100%">

This was the first serious attempt to prove the idea.

It was rough, but useful. This stage answered the important question: does the idea still feel good once it is actually moving?

### 3. First 3D web version

<img src="docs/readme-assets/01-first-3d-web-version.png" alt="First 3D web version" width="100%">

This was the first version where the project started feeling like a real game.

The browser version made fast gameplay testing possible. The focus was simple: movement, collisions, readable interaction, and immediate feedback.

**Tech used in this phase**

- `HTML`
- `CSS`
- `JavaScript`
- `Three.js` for 3D rendering
- `Matter.js` for gameplay physics

### 4. Web MVP UI improvement

<img src="docs/readme-assets/04-ui-improved-mvp-on-web.png" alt="UI improved MVP on web" width="100%">

<img src="docs/readme-assets/05-example-new-ui.png" alt="Example new UI" width="100%">

After the core game started working, the next challenge was clarity.

This stage improved the interface, visual hierarchy, and overall readability so the prototype could feel more intentional and presentable.

### 5. First mobile menu versions

<img src="docs/readme-assets/06-first-mobile-menu.png" alt="First mobile menu" width="100%">

<img src="docs/readme-assets/07-first-mobile-menu-2.png" alt="First mobile menu 2" width="100%">

Bringing the game to mobile was not just a screen resize. It required rethinking flow, touch interaction, spacing, and what players should see first.

This phase forced better mobile thinking. Web habits did not translate directly to touch screens, so the UX had to be redesigned instead of just adapted.

**Tech used in this phase**

- `React Native`
- `Expo`
- `TypeScript`
- `React Navigation`
- `expo-gl`
- `expo-three`
- custom touch UI such as joystick and action buttons

### 6. Mobile graphics and visual improvement search

<img src="docs/readme-assets/10-mobile-version-graphics-improvement-search.png" alt="Mobile graphics improvement search" width="100%">

This part of development was about searching for a stronger visual direction.

Instead of only adding features, the focus here was coherence: better readability, cleaner visual decisions, and a stronger identity across screens.

### 7. Current mobile MVP / prototype

<img src="docs/readme-assets/09-last-version-mobile-2.png" alt="Last mobile version 2" width="100%">

<img src="docs/readme-assets/11-last-version-mobile-1.png" alt="Last mobile version 1" width="100%">

This is the point where the project can now be shown publicly with confidence.

It is still ongoing development, but it has reached a meaningful MVP/prototype phase:

- the mobile version is playable
- the visual language is much more mature than in the first builds
- the structure is good enough to continue iterating seriously
- the project is now clear enough to invite feedback and possible collaboration

---

## Technical Direction, In Short

This project has been built with practical technology choices that support iteration and real-time gameplay without making the stack unnecessarily heavy.

| Area | Main technology |
| --- | --- |
| Early browser prototype | `HTML`, `CSS`, `JavaScript`, `Three.js`, `Matter.js` |
| Mobile app layer | `React Native`, `Expo`, `TypeScript` |
| 3D rendering on mobile | `three`, `expo-three`, `expo-gl` |
| App navigation | `React Navigation` |
| Multiplayer groundwork | `Socket.IO` and peer/networking-oriented architecture |

The technical goal has been simple: use tools that are flexible enough for experimentation, but solid enough to support real gameplay progression.

## Why It Should Perform Well

The project is designed around a relatively focused arena format, which is a good fit for maintaining performance.

- the gameplay area is compact, which helps keep rendering and simulation manageable
- `Matter.js` is a strong match for controlled physics-based interaction
- `Three.js` is used in a contained way rather than for a huge asset-heavy world
- the mobile implementation already includes practical optimization patterns like cached textures, shared resources, disposal helpers, and simplified touch UI sizing
- the web implementation also shows performance-aware decisions such as particle limits, shared materials, cleanup logic, and reduced work when the page is not visible

The performance strategy is based on controlled scope, sensible tooling, and iterative optimization where it matters.

## What Improved Over Time

- the idea became clearer
- the game loop became more grounded
- the interface became easier to read
- the mobile adaptation became more intentional
- the structure of the codebase became stronger as the project expanded
- the prototype became easier to present and easier to continue developing

## Skills Learned By Building It

This project taught important lessons through iteration and mistakes.

- sketching early is useful because it reduces wasted complexity
- fast prototypes reveal weak ideas quickly
- game feel matters as much as technical correctness
- UI readability is part of gameplay quality
- mobile design needs its own thinking, not just adaptation
- not every mistake is failure; many mistakes are how the next stronger version becomes visible

## Why The Project Is Being Shown Now

The game is still ongoing, but it has reached a stage where public presentation makes sense.

That means this is a good time for:

- contributions
- testing
- design ideas
- UI/UX feedback
- gameplay balancing feedback
- technical suggestions

## Ongoing Development

ARENA is still evolving.

This showcase is a snapshot of the journey so far, not the final destination. The project has moved from sketch, to concept, to web prototype, to mobile MVP, and it will keep improving from here.
