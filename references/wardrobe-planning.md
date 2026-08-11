# Wardrobe planning

Select one mode before pose design and publish the result.

## Current

Use when no clothing description is supplied and the full outfit is visible. Preserve every visible garment, layer, material, color, silhouette, hem, sleeve, closure, shoe, accessory, and styling detail. Do not restyle for the scene.

## Specified

Use when the user names clothing, shoes, accessories, or a dress code.

- Treat the description as authoritative while preserving identity, age, proportions, and hair.
- Resolve unspecified details conservatively so the outfit is coherent, wearable, age-appropriate, scene-appropriate, weather-plausible, and safe.
- Do not add brands, logos, jewelry, bags, hats, or props unless requested.
- If the request conflicts with safety, mobility, climate, or location, explain the conflict and use the closest safe interpretation.

## Auto-complete

Use when the reference is half-body, the visible upper garment is usable, and no clothing description is supplied.

1. Preserve the visible upper garment exactly.
2. Infer only unseen lower clothing and shoes.
3. Match formality, colors, fabric weight, silhouette, season, scene, apparent age category, and pose needs.
4. Prefer simple logo-free timeless pieces that do not compete with the face or scene.
5. Prefer stable footwear suitable for the ground and movement.
6. Do not infer hidden brand, price, occupation, religion, culture, or personal preference.
7. Call additions `AI styling completion`, not observed wardrobe.

Typical coordination: a casual light blouse or knit may pair with straight trousers, an A-line/midi skirt, clean flats, loafers, or simple sneakers; a structured shirt/jacket with tailored trousers or straight skirt and stable shoes; a sporty top with coordinated practical bottoms and sneakers.

Choose one outfit, not alternatives, unless variants are requested.

```text
wardrobe mode: current / specified / auto-complete
observed and preserved:
user-specified replacements:
AI styling completion:
top:
bottom:
outerwear:
footwear:
accessories:
materials and colors:
fit and hem constraints:
pose restrictions:
```

Repeat this lock in every generation call.
