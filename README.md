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

This page is meant to show:

- how the game idea started
- how the design changed over time
- what was improved between versions
- what technologies were used
- what was learned by building, testing, and making mistakes

## Project Status Today

The game is still in active development.

It is not presented as a finished product. It is presented because it has now reached a meaningful prototype stage:

- playable
- visually much more coherent than the first versions
- technically structured enough to continue building on
- ready for feedback, testing, contribution ideas, and iteration

## Main Repository

The actual game development repository is here but it is private for now:

**[github.com/tunasafa/arena](https://github.com/tunasafa/arena)**

This showcase repository exists to tell the development story in a clearer and more visual way.

## Development Story

### 1. The sketch stage

<table>
  <tr>
    <td width="56%">
      <img src="docs/readme-assets/03-sketch.png" alt="Sketch" width="100%">
    </td>
    <td width="44%">
      Everything started from a simple sketch.
      <br><br>
      At this point, the goal was not polish. The goal was to understand the core game idea:
      an arena-based experience with readable movement, competitive energy, and enough structure to become a real playable loop later.
      <br><br>
      Starting with sketching helped keep the scope small and testable.
    </td>
  </tr>
</table>

### 2. First concept trial

<table>
  <tr>
    <td width="56%">
      <img src="docs/readme-assets/02-first-concept-trial.png" alt="First concept trial" width="100%">
    </td>
    <td width="44%">
      This was the first serious attempt to prove the idea.
      <br><br>
      It was still rough, but that was useful. The purpose here was to check whether the game concept actually had potential in motion, not just in imagination.
      <br><br>
      One of the first lessons came here: some ideas feel exciting in theory, but only real testing shows what is worth continuing.
    </td>
  </tr>
</table>

### 3. First 3D web version

<table>
  <tr>
    <td width="56%">
      <img src="docs/readme-assets/01-first-3d-web-version.png" alt="First 3D web version" width="100%">
    </td>
    <td width="44%">
      This was the first version where the project started feeling like a real game.
      <br><br>
      The browser version made it possible to build and test gameplay quickly. That mattered a lot, because early game development benefits from fast iteration more than heavy production setup.
      <br><br>
      The main focus was simple: playable interaction, movement, collisions, and immediate feedback.
    </td>
  </tr>
</table>

**Tech used in this phase**

- `HTML`
- `CSS`
- `JavaScript`
- `Three.js` for 3D rendering
- `Matter.js` for gameplay physics

### 4. Web MVP UI improvement

<table>
  <tr>
    <td width="50%">
      <img src="docs/readme-assets/04-ui-improved-mvp-on-web.png" alt="UI improved MVP on web" width="100%">
    </td>
    <td width="50%">
      <img src="docs/readme-assets/05-example-new-ui.png" alt="Example new UI" width="100%">
    </td>
  </tr>
</table>

After the core game started working, the next challenge was clarity.

This stage was about improving the interface, making the game look more intentional, and moving it away from "early prototype energy" toward something that could be shown with more confidence.

This was an important shift because a game is not only about mechanics. If players cannot read the game clearly, the experience weakens even when the systems are working.

### 5. First mobile menu versions

<table>
  <tr>
    <td width="50%">
      <img src="docs/readme-assets/06-first-mobile-menu.png" alt="First mobile menu" width="100%">
    </td>
    <td width="50%">
      <img src="docs/readme-assets/07-first-mobile-menu-2.png" alt="First mobile menu 2" width="100%">
    </td>
  </tr>
</table>

Bringing the game to mobile was not just a screen resize. It required rethinking flow, touch interaction, spacing, and what players should see first.

This phase forced better product thinking. Desktop and web habits do not automatically translate to phones, so the mobile version became a separate design challenge.

**Tech used in this phase**

- `React Native`
- `Expo`
- `TypeScript`
- `React Navigation`
- `expo-gl`
- `expo-three`
- custom touch UI such as joystick and action buttons

### 6. Mobile graphics and visual improvement search

<table>
  <tr>
    <td width="56%">
      <img src="docs/readme-assets/10-mobile-version-graphics-improvement-search.png" alt="Mobile graphics improvement search" width="100%">
    </td>
    <td width="44%">
      This part of development was about searching for a stronger visual direction.
      <br><br>
      Instead of only adding more features, the work here focused on making the game feel more coherent: better visual decisions, improved readability, and a more consistent presentation across screens.
      <br><br>
      This is where many projects either become more focused or become messy. Here, the goal was clearly to simplify and strengthen the overall identity.
    </td>
  </tr>
</table>

### 7. Current mobile MVP / prototype

<table>
  <tr>
    <td width="33%">
      <img src="docs/readme-assets/08-last-mobile-version-real-phone.png" alt="Last mobile version on a real phone" width="100%">
    </td>
    <td width="33%">
      <img src="docs/readme-assets/09-last-version-mobile-2.png" alt="Last mobile version 2" width="100%">
    </td>
    <td width="33%">
      <img src="docs/readme-assets/11-last-version-mobile-1.png" alt="Last mobile version 1" width="100%">
    </td>
  </tr>
</table>

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

So the performance strategy is not based on overengineering. It is based on controlled scope, sensible tooling, and iterative optimization where it matters.

## What Improved Over Time

The biggest change is not just the visuals. It is the maturity of the project decisions.

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
