# Metal Implementation Notes

Focus on the real 3D feel.

- MTKView + custom render pipeline.
- Multiple draw calls: cabinet, glass, claw, prizes.
- Uniforms for lights, camera, claw transform, prize transforms.
- Outline pass or inverted-hull for chibi edges.
- Glass: blend + fresnel in fragment shader.

Physics can start on CPU; move hot parts to compute later if needed.

Start with a simple scene, then add movement and grab logic.
