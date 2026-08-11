# Background continuity lock

Treat the scene as a fixed photographic plate, not a prompt to redraw. The series may vary the person and crop, but must not create alternate versions of the location.

## Canonical background plate

1. Start from the original scene reference at its native geometry.
2. If the user requests removal, blur, or cleanup, create one cleaned master plate first. Inspect it before portrait generation. Never repeat that cleanup independently for each portrait.
3. Keep original scene pixels unchanged outside the person mask, contact/cast shadow, reflected-light integration, and necessary foreground occlusion.
4. Derive all portrait crops from this same plate. A crop may hide an anchor but cannot move, rewrite, resize, or delete an anchor that remains visible.

For source-critical text, signs, posters, screens, architecture, or small devices, do not ask the model to recreate them. Preserve their pixels through masking/compositing. Generative reconstruction is not reliable enough for exact Chinese characters or repeated small details.

## Anchor manifest

Before generation, inventory every continuity-critical element. Record:

```text
ANCHOR ID:
type: text / sign / door / window / device / cable / decoration / tree / lamp / other
location: left/center/right + foreground/midground/background + relation to a stable landmark
appearance: exact visible glyph shape or wording when legible, count, order, color, material, scale, orientation
state: MUST REMAIN / MUST BE ABSENT after approved cleanup
occlusion rule: whether the person may temporarily cover it
```

Include prominent wall lettering, signboard order, window and door divisions, posters, payment or power-bank terminals, their cables and bases, lamps, lanterns, trees, roof details, and other objects whose movement would expose a different background.

## Compact per-image lock

Repeat this in every image request:

```text
BACKGROUND PLATE LOCK: use the supplied canonical scene plate as unchanged photographic pixels. Do not redraw the background. Preserve all manifest anchors exactly: visible text/glyph shapes, sign count/order, architecture, device and cable positions, decorations, surfaces, perspective, lighting, grain, and defects. Apply the approved removal list consistently. Modify only the person mask, physically required occlusion, reflected light, and contact/cast shadow.
```

## Continuity failure

Mark an output `retry` when any visible anchor changes, including a missing or altered character, moved terminal, changed cable, different sign count, altered window division, invented decoration, changed wall damage, or re-created texture. Retry from the canonical plate with a tighter person mask. Do not repair continuity by regenerating the whole frame.
