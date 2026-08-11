---
name: scene-portrait-photo-fusion
description: Fuse an authorized person reference and a real scene photo into 4, 8, 12, or 16 photorealistic individual portraits with varied scene-appropriate poses while preserving the same recognizable identity, visible wardrobe, proportions, scene geometry, lighting, scale, and ground contact. Use when placing a referenced real person into another photographed location, generating a coherent portrait series, designing richer hand, arm, torso, side-facing, leaning, leg, foot, walking, turning, or environmental-interaction poses, or auditing identity and compositing realism.
---

# Scene Portrait Photo Fusion

Generate finished individual photographs, not only pose advice or pose boards. Treat the person photo as identity/wardrobe reference and the scene photo as geometry/perspective/light reference.

## Workflow

1. Identify `PERSON REFERENCE` and `SCENE REFERENCE` from content. If user labels conflict with visible content, state the mismatch and use actual roles.
2. Require user-supplied or explicitly authorized person imagery. Never identify the person or infer sensitive traits.
3. Read [references/locks-and-realism.md](references/locks-and-realism.md). Publish concise identity, wardrobe, scene, and fusion locks. Mark invisible attributes unlocked.
4. Read [references/pose-library.md](references/pose-library.md). Build an internal pose matrix varying scene zone, body angle, torso, hands, legs, feet, gaze, crop, motion, and interaction.
5. Read [references/generation-and-audit.md](references/generation-and-audit.md). Default to 8 photos; accept 4, 8, 12, or 16. Lock the numbered plan before generating.
6. Use built-in image generation by default. Use one call per finished photograph and include both original references in every call. Never replace individual deliverables with a collage.
7. Inspect every output. Retry a failed photo with one targeted correction. Return the plan, individual photos, optional contact sheet, and audit.

## Inputs and defaults

Required: one clear authorized person reference and one scene reference.

Optional: count, mood, style, aspect ratio, camera/lens look, gestures, wardrobe permission, mobility or safety limits, and contact sheet.

Defaults: 8 individual vertical 3:4 photos; photorealistic, natural, relaxed; exact visible wardrobe; identity above pose novelty; no scene redesign; no in-image text, borders, logos, or watermarks.

If full clothing or shoes are invisible, do not invent them silently. Ask for a full-body reference or explicit permission for neutral completion.

## Core invariants

- Preserve recognizable face, apparent age, skin tone, hair, body proportions, visible clothing construction/material/color, footwear, and accessories.
- Do not beautify into another person, reshape the body, lengthen limbs, change skin tone, replace clothing, or add makeup unless requested.
- Match person scale, horizon, ground plane, perspective, light direction/softness, exposure, temperature, contrast, depth of field, grain, and lens character.
- Create believable foot contact, cast and contact shadow, reflected light, occlusion, and hair/edge integration.
- Preserve scene geometry and anchors. Do not invent furniture, rails, stairs, doors, props, vegetation, or buildings.
- Use only safe visible interactions.

## Diversity

For 8 photos use at least 6 hand configurations, 6 leg/foot configurations, 4 body angles, 3 gazes, 3 crops, 2 motion states, and 3 scene zones. Include a side-facing pose and a turn/over-shoulder transition. Use a forward lean or bend only when comfortable, age-appropriate, non-sexualized, and plausible. Never repeat the exact hand + leg + torso + gaze combination.

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
identity and wardrobe invariants:
```

## Safety

- Treat ambiguous youthful subjects as minors and use age-appropriate, non-sexualized poses.
- Do not infer identity or sensitive traits.
- Do not fabricate harmful real-world event evidence involving the person.
- State that outputs are synthetic when they could reasonably be mistaken for evidence of a real event.

## Final order

1. `图片角色与锁定`
2. `场景融合判断`
3. `编号拍摄方案`
4. generated individual photos
5. optional contact sheet
6. `一致性与真实感检查`
