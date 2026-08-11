# Generation and quality audit

## Generate

- Publish the complete `F01–F04/08/12/16` plan first.
- Specify zone, ground point, torso, hands, supporting/free legs, knees, ankles, feet, gaze, interaction, crop, view, light, shadow, and invariants.
- Use one built-in image-generation call per final photo.
- Include both original references every time. Generated results may be secondary continuity references but never replace originals.
- Repeat identity, wardrobe, scene, and fusion locks.
- Put only one locked pose in each call.
- Request no text, label, border, collage, logo, or watermark.
- Create a contact sheet only after individual photos pass.

## Audit

Identity: same recognizable person, apparent age, face, hairline, hairstyle, proportions, wardrobe, footwear, and accessories.

Anatomy: plausible fingers, complete limbs unless intentionally cropped, correct supporting leg, believable gravity, safe joints, and the locked pose.

Fusion: believable scale/horizon, one ground plane, matching contact/cast shadow, reflected color, occlusion, edge quality, sharpness, grain, and depth of field.

Scene/series: recognizable geometry, no inventions, same person/wardrobe/treatment, meaningful pose diversity, and correct count.

Classify each output `pass`, `retry`, or `limited`.

Targeted retry: strengthen identity locks; restate supporting/free leg and hand silhouette; restate ground point/contact shadow; restate light; remove scene inventions; or simplify anatomy while preserving intent. Stop after two repeats of the same failure and report the limitation.
