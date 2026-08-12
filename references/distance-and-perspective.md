# Distance and perspective realism

Calibrate placement before pose generation. Do not treat a distant subject as a resized near portrait.

## Distance modes

- `near`: person occupies 55–85% of frame height. Preserve readable facial and fabric detail while matching source lens character.
- `medium`: person occupies 30–55%. Reduce microdetail, local contrast, and edge acuity to the level of real objects at that depth.
- `long`: person occupies 12–30%. Preserve identity through silhouette, hairstyle, glasses, large facial ratios, build, and wardrobe colors; never force pore-level or eye-level detail beyond available pixels.

If the requested person would occupy under 12%, explain that reliable facial identity is limited and prioritize silhouette and clothing consistency.

## Perspective calibration

Record for every shot:

```text
distance mode:
horizon height:
foot ground point:
ground-plane direction:
same-depth scale anchor: door / railing / bollard / brick course / person-sized object
target person height as % of frame:
estimated head-to-body ratio at output size:
foreground occluders:
shadow direction, length, color, softness:
```

Size the person from a same-depth anchor and convergence lines. Keep both feet on one plane. Reject a placement when the head is enlarged to preserve likeness, limbs retain near-camera perspective, or the person scale conflicts with a door, railing, curb, bollard, or paving module.

## Two-stage fusion

1. Create or isolate a person layer with the locked identity, wardrobe, pose, body proportions, and target camera viewpoint.
2. Place that layer on the calibrated ground point without changing the background plate.
3. Match distance-dependent sharpness, microcontrast, saturation, grain, compression, depth of field, and atmospheric perspective.
4. Add only physically required reflected light, occlusion, and shadows in local masks.

When explicit layer or mask controls are unavailable, state both stages in one edit request and restrict changes to a tight person-plus-shadow region.

## Environment-light sample

Sample three contributions at the target point:

- sky/top light: hue, direction, softness, and exposure;
- ground bounce: low-angle color and intensity;
- adjacent structures: subtle reflected color from nearby walls, foliage, signs, or decorations.

Apply them to skin, white clothing, hair, and garment folds without creating a colored outline. Remove the lighting signature of the source portrait when it conflicts with the destination scene.

## Distance degradation lock

```text
DISTANCE REALISM LOCK: match the subject to real objects at the same depth in spatial resolution, edge acuity, local contrast, saturation, noise, compression, atmospheric perspective, depth of field, and motion blur. Do not preserve facial or fabric detail that the target pixel height cannot support. Never make the person cleaner or sharper than the scene.
```

## Grounding and three-layer shadow

Use all three layers:

1. `contact`: narrow and darkest immediately beneath each load-bearing shoe;
2. `near soft`: lower-opacity ground shadow expanding in the scene's light direction;
3. `ambient occlusion`: subtle darkness between trouser cuff and shoe and between the legs.

Let ground texture slightly interrupt the shoe boundary. For long shots, make contact and cast shadows smaller, softer, and lower contrast. Reject outlined feet, identical shadow blobs, floating soles, or a complete hard black silhouette inconsistent with scene shadows.

## Reference sufficiency

For long full-body shots, prefer an identity pack: clear frontal face, three-quarter face, frontal full body, side full body, and back or over-shoulder view. With only a headshot or half-body reference, label inferred height, limb proportions, back view, lower clothing, and footwear as approximate or AI styling completion.
