# MagicClawDuo

**Dusty's Magic iPhone Duo Laptop-Mode Claw Machine**

Real 3D claw machine with cute whimsy chibi / Teen Titans Go art style. The Duo becomes a mini arcade cabinet.

## Vision
Laptop pose: **top half = 3D glass case with prizes + claw**, **bottom half = joystick + drop button**.

Full Metal for the real 3D feel — lighting, reflections on the glass, soft shadows, and satisfying physics when the claw grabs (or misses).

## Art Style
- Cute chibi prizes (tiny monsters, plushies, magic orbs, food characters)
- Bold outlines, exaggerated features, bright saturated colors
- Teen Titans Go energy: simple shapes, big expressions, playful bounce
- Liquid-glass claw and case accents matching Dusty's Magic

## MVP Scope
1. Single claw machine cabinet
2. Laptop-mode split (top = 3D view, bottom = controls)
3. Metal-rendered 3D scene with glass, claw, and 3–5 prizes
4. Claw movement (X/Y) + drop + close/open
5. Basic physics (gravity, prize collisions, simple grab detection)
6. Win/lose feedback with chibi particles
7. Score / tickets

## How It Works (Laptop Mode)
- `onHingeChange` detects laptop pose.
- Layout:
  - Top: continuous Metal view of the machine interior.
  - Bottom: virtual joystick (or D-pad) + big DROP button + claw strength indicator.
- Reserved regions keep controls clear of the crease.

## Metal Architecture
- Custom Metal renderer for maximum control and 3D feel.
- Scene: cabinet interior, glass planes (transparent + refraction or simple alpha), claw mesh, prize meshes.
- Lighting: directional + point lights, soft shadows or blob shadows for MVP.
- Shaders:
  - Toon / cel shading + outline for chibi look.
  - Glass shader (fresnel, simple refraction or reflection).
  - Prize-specific materials (soft plush, shiny orb).
- Camera: fixed inside-the-cabinet view looking down/slightly angled.
- Update loop: input → claw physics/IK → prize physics → render.

## Physics
- Claw: constrained movement in X/Y plane, vertical drop on button, open/close animation.
- Prizes: rigid bodies (simple spheres or boxes for MVP) with gravity, friction, and collisions against walls/floor/other prizes.
- Grab: when claw closes, check overlap; if success, attach prize to claw and lift; else miss.
- Drop prize into chute on successful lift.
- Optional compute shader for many prizes later; CPU physics fine for MVP.

## Controls (Bottom Half)
- Joystick: move claw left/right/forward/back.
- DROP button: descend, close, attempt grab, rise.
- Optional: claw strength slider (affects grab chance or timing).
- Reset / new game.

## Project Structure (Suggested)
```
MagicClawDuo/
├── Sources/
│   ├── Metal/
│   │   ├── ClawRenderer.swift
│   │   ├── Shaders.metal
│   │   └── Scene.swift
│   ├── Physics/
│   └── UI/
├── Assets/
└── Docs/
```

## Next Steps
- Xcode 27.1 + iOS 27.1 target
- Basic Metal scene with claw + one prize
- Input on bottom half
- Physics integration
- Chibi prize models (placeholders first)
- Glass and lighting polish

Built for Dusty's Magic — pure arcade joy on the fold.
