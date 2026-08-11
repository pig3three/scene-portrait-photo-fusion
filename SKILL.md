---
name: scene-portrait-photo-fusion
description: Fuse an authorized person reference and a real scene photo into 4, 8, 12, or 16 photorealistic portraits while preserving identity, wardrobe, proportions, background text and object anchors, scene geometry, lighting, scale, ground contact, and photographic realism. Use when placing a referenced person into another photographed location, preserving or changing clothes and shoes, completing unseen lower-body clothing, generating a coherent multi-pose portrait series, preventing background drift between outputs, or auditing identity and compositing realism.
---

# Scene Portrait Photo Fusion

Generate finished individual photographs. Treat the person photo as the identity reference and the scene photo as the geometry, perspective, and light reference.

## Workflow

1. Identify `PERSON REFERENCE` and `SCENE REFERENCE` from content. State and correct conflicting user labels.
2. Require user-supplied or explicitly authorized person imagery. Never identify the person or infer sensitive traits.
3. Read [references/locks-and-realism.md](references/locks-and-realism.md). Publish identity, scene, and fusion locks.
4. Read [references/background-continuity.md](references/background-continuity.md). Create one canonical background plate and an anchor manifest before designing poses. If removals or cleanup are requested, perform them once on the plate and reuse that same plate throughout the series.
5. Read [references/wardrobe-planning.md](references/wardrobe-planning.md). Select one wardrobe mode, publish the complete outfit lock, and keep it unchanged across the series.
6. Read [references/pose-library.md](references/pose-library.md). Build an internal pose matrix varying scene zone, body angle, torso, hands, legs, feet, gaze, crop, motion, and interaction.
7. Read [references/generation-and-audit.md](references/generation-and-audit.md). Default to 8 photos; accept 4, 8, 12, or 16. Lock the numbered plan before generation.
8. Use built-in image editing or compositing by default, keeping the canonical background pixels unchanged outside the person integration region. Use one call per photograph and include the person reference plus canonical background plate every time. Never replace individual deliverables with a collage.
9. Generate sequentially. Audit each output against the original scene and anchor manifest before starting the next. Retry failed photos with one targeted correction, then return the plan, photos, optional contact sheet, and audit.

## Inputs and defaults

Required: one clear authorized person reference and one scene reference.

Optional: count, mood, style, aspect ratio, camera/lens look, gestures, clothing, shoes, accessories, mobility/safety limits, and contact sheet.

Defaults: 8 individual vertical 3:4 photos; natural photorealism; identity above pose novelty; no scene redesign; no text, borders, logos, or watermarks.

Wardrobe modes:

- `current`: with no clothing request and a full visible outfit, preserve current clothing and shoes.
- `specified`: when the user describes clothing, shoes, or accessories, use that description while preserving identity and proportions.
- `auto-complete`: with a half-body reference and no clothing request, preserve the visible upper garment and automatically coordinate unseen lower clothing and shoes. Label them as AI styling completion, not observed facts.

## Core invariants

- Preserve recognizable face, apparent age, skin tone, hair, and body proportions.
- Do not beautify into another person, reshape the body, lengthen limbs, change skin tone, or add makeup unless requested.
- Change clothing only in `specified` mode. In `auto-complete`, never redesign the visible upper garment; add only unseen lower clothing and shoes.
- Lock one complete outfit and repeat it verbatim in every image call.
- Match scale, horizon, ground plane, perspective, light, exposure, temperature, contrast, depth of field, grain, shadow, reflected light, occlusion, and edge integration.
- Preserve the canonical background plate, including all visible text, glyph shapes, signs, doors, windows, decorations, devices, cables, and their exact count, order, position, orientation, scale, and color. Use only safe visible interactions.
- Never independently redraw or clean the background for each output. Only the person, contact shadow, necessary foreground occlusion, and tightly localized integration pixels may change.
- Different crops may reveal less of the same plate, but must not move, omit, rewrite, or invent a background anchor inside the visible crop.
- Prefer unchanged source pixels over generative reconstruction. If exact text or object preservation cannot be guaranteed, disclose the limitation and use a mask/composite workflow rather than regenerating the full scene.

## Pose diversity

For 8 photos use at least 6 hand configurations, 6 leg/foot configurations, 4 body angles, 3 gazes, 3 crops, 2 motion states, and 3 scene zones. Include a side-facing pose and an over-shoulder transition. Use a forward lean only when comfortable, age-appropriate, non-sexualized, and plausible. Never repeat the exact hand + leg + torso + gaze combination.

## Shot lock

```text
F01｜short title
scene zone and ground point:
body angle and torso:
hands and arms:
legs, feet, and weight:
head, gaze, and expression:
environment interaction:
framing and camera view:
light and shadow integration:
identity invariants:
wardrobe mode and complete outfit lock:
```

## Safety

- Treat ambiguous youthful subjects as minors and use age-appropriate, non-sexualized poses.
- Do not infer identity or sensitive traits.
- Do not fabricate harmful real-world event evidence.
- State that outputs are synthetic when they could be mistaken for evidence of a real event.

## Final order

1. `图片角色与身份锁定`
2. `服饰模式与完整服饰锁定`
3. `场景融合判断`
4. `编号拍摄方案`
5. generated photos
6. optional contact sheet
7. `一致性与真实感检查`
