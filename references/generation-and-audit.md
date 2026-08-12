# Generation and quality audit

Publish the complete `F01–F04/08/12/16` plan first. Specify zone, distance mode, horizon, ground point, scale anchor, target person-height ratio, torso, hands, supporting/free legs, feet, gaze, interaction, crop, viewpoint, environment-light sample, three-layer shadow, identity, and complete wardrobe lock.

- Build and approve one canonical background plate and anchor manifest before F01. Use the original scene unchanged unless the user requested cleanup; when cleanup is requested, create it once on the master plate.
- Use one built-in image-generation call per photo.
- Generate sequentially and audit each result before the next call. Do not parallelize a continuity-critical series.
- Include the original person reference and canonical background plate every time. Never substitute a previous generated portrait for either primary reference.
- Repeat identity, complete wardrobe, background plate, anchor manifest, scene, and fusion locks.
- In auto-complete mode, repeat the exact generated lower garment and footwear instead of re-styling each image.
- Put only one locked pose in each call.
- Use the two-stage person-layer then local-fusion workflow when available. Do not obtain a long shot by shrinking a near-shot output.
- Repeat the distance realism lock and target person-height ratio in every call.
- Prefer masked editing/compositing: preserve all background pixels outside the person, required occlusion, reflected light, and shadow masks. Do not regenerate the whole scene.
- Request no text, label, border, collage, logo, or watermark.
- Create a contact sheet only after individual photos pass.

Audit:

- Identity: same person, apparent age, face, hairline, hairstyle, and proportions.
- Wardrobe: correct mode; visible clothing preserved; specified outfit followed; auto-completed lower garment and shoes identical; no color, material, hem, shoe, or accessory drift.
- Anatomy: plausible fingers, complete limbs unless cropped, correct supporting leg, gravity, safe joints, and locked pose.
- Fusion: believable scale/horizon, ground contact, shadows, reflected color, occlusion, edges, sharpness, grain, depth of field, and source-matched lens character.
- Distance/perspective: correct scale against a same-depth anchor; plausible head-to-body ratio; no near-lens limb perspective in a long shot; subject detail, edge acuity, contrast, saturation, grain, compression, depth, and atmospheric haze match the target distance.
- Grounding: narrow contact shadow under the supporting shoe, coherent softer cast shadow, and subtle ambient occlusion at cuffs and between legs; ground texture interrupts the shoe edge naturally.
- Environment light: destination sky light, ground bounce, and nearby structure color affect the person consistently; no residual studio/selfie lighting or colored cutout outline.
- Background continuity: compare against the canonical plate, not another generated photo. Verify exact visible text/glyph shapes; sign, poster, door, and window count/order; architecture; device position/orientation; cable path; decorations; wall marks; crop; and approved removals. Any drift is a retry.
- Photographic realism: natural skin texture and asymmetry, individual hair strands without halos, plausible fingers and feet, cloth tension and folds, consistent glasses reflections, restrained sharpening, source-matched noise/compression, coherent white balance, physically plausible shadow softness/direction, and no plastic skin, fake bokeh, over-HDR, synthetic rim light, or cutout edges.
- Scene/series: same fixed location plate, no inventions, meaningful pose diversity, and correct count.

Classify each output `pass`, `retry`, or `limited`. Retry if the head is oversized, the person is sharper than same-depth objects, facial detail exceeds target pixels, feet have halos, shadows disagree with scene anchors, environment color is missing, or the subject looks photographed with a different focal length or weather. Use the canonical plate and a tighter local mask; never fix drift by regenerating the whole frame. Stop after two repeats of the same failure and disclose the limitation. For text- or object-critical work, retain original background pixels through deterministic compositing because generative tools cannot guarantee pixel-perfect reconstruction.
