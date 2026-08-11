# Locks and photorealistic fusion

## Person lock

Record authorization, age category, face/apparent age, hair, proportions, top/dress, bottom, footwear, accessories, hidden attributes, allowed changes, and forbidden changes. Do not identify the person. A headshot locks face and hair, not unseen clothes, shoes, or proportions.

## Scene lock

Record viewpoint/horizon, ground plane, depth zones, usable placements, anchors, light direction/softness, color temperature, occluders, unsafe zones, and forbidden inventions. Preserve geometry, surfaces, signage layout, vegetation, architecture, and light. Reframe but do not redesign.

If labels conflict with visible roles, state it and assign roles by content. If both images contain people, ask which person is the identity reference.

## Fusion mechanics

1. Choose a ground contact point before sizing the person.
2. Match height to reliable visible anchors.
3. Respect convergence, horizon, and lens compression.
4. Keep feet on one believable ground plane.
5. Match key direction, elevation, hardness, color, exposure, contrast, sharpness, grain, motion blur, and depth of field.
6. Add reflected fill from nearby walls, ground, sky, foliage, or interiors.
7. Match shadow direction and softness; contact shadow is darkest near footwear.
8. Let real foreground objects occlude the person when geometry requires it.
9. Avoid cutout halos, floating feet, duplicate shadows, inconsistent bokeh, impossible reflections, or mismatched noise.

Use open space first; then gesture toward a real anchor; touch, lean, or sit only on a visible stable permitted surface. Never invent support.

Repeat in every generation:

```text
IDENTITY LOCK: preserve recognizable face, apparent age, skin tone, hair, proportions, exact visible wardrobe, footwear, and accessories; no beautification or reshaping.
SCENE LOCK: preserve geometry, architecture, surfaces, anchors, perspective, and light; no invented objects.
FUSION LOCK: believable ground contact, scale, perspective, occlusion, shadow, reflected light, edge integration, lens character, depth of field, grain, and color.
CONSISTENCY: same person and wardrobe; realistic anatomy; no extra people, text, logo, or watermark.
```
