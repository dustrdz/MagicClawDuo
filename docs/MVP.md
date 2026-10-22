# MagicClawDuo MVP Details

## Core Loop
1. Set Duo in laptop pose.
2. Move claw with bottom joystick.
3. Hit DROP.
4. Watch claw descend, close, and try to grab (top 3D view).
5. Success → prize lifts and drops into chute (particles + sound).
6. Miss → claw returns, try again.

## Metal Requirements
- High-quality 3D: proper depth, lighting, simple PBR or toon materials.
- Transparent glass rendering (order-independent or simple alpha).
- Smooth 60 fps on A20 Pro.
- Custom shaders for the chibi aesthetic.

## Physics Sketch
- Prizes: position, velocity, angular velocity.
- Integrate forces (gravity, drag).
- Broad-phase + narrow-phase collisions (spheres vs planes for MVP).
- Claw attachment: kinematic when grabbed.

## Controls Mapping
- Bottom half only — no fingers covering the prize view.
- Large, tactile targets.
- Haptics on drop, grab, and win.

## Art Pipeline
- Chibi prizes: big heads, tiny bodies, bold outlines generated in shader.
- Color palette: bright, high-contrast, playful.
- Reference: Teen Titans Go character designs + modern claw machine merch.
