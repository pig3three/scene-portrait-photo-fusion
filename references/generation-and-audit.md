# Generation and quality audit

Publish the complete `F01–F04/08/12/16` plan first. Specify zone, ground point, torso, hands, supporting/free legs, feet, gaze, interaction, crop, view, light, shadow, identity, and the complete wardrobe lock.

- Use one built-in image-generation call per photo.
- Include both original references every time.
- Repeat identity, complete wardrobe, scene, and fusion locks.
- In auto-complete mode, repeat the exact generated lower garment and footwear instead of re-styling each image.
- Put only one locked pose in each call.
- Request no text, label, border, collage, logo, or watermark.
- Create a contact sheet only after individual photos pass.

Audit:

- Identity: same person, apparent age, face, hairline, hairstyle, and proportions.
- Wardrobe: correct mode; visible clothing preserved; specified outfit followed; auto-completed lower garment and shoes identical; no color, material, hem, shoe, or accessory drift.
- Anatomy: plausible fingers, complete limbs unless cropped, correct supporting leg, gravity, safe joints, and locked pose.
- Fusion: believable scale/horizon, ground contact, shadows, reflected color, occlusion, edges, sharpness, grain, and depth of field.
- Scene/series: recognizable geometry, no inventions, meaningful diversity, and correct count.

Classify each output `pass`, `retry`, or `limited`. Retry one targeted issue at a time and stop after two repeats of the same failure.
