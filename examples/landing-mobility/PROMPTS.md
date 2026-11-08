# CNIQ vehicle image prompts (Meta AI and other image generators)

These prompts produce the vehicle pictures for this landing page: a **side view** for the hero and a matching **top view** for the aerial and dashboard sections. Both should show the same car as the CNIQ reference picture: a white, two-tone, mid-size premium SUV with a black roof.

Save the results as:

| File | Used for | Shape |
|------|----------|-------|
| `assets/car-side.png` | Hero side view (driving on the road) | Landscape, about 2.6 : 1 |
| `assets/car-top.png` | Aerial curve and dashboard road | Portrait, about 1 : 2, front of car pointing **up** |

Your own CNIQ renders work too: the **top view** (white SUV, black roof, front pointing up) can be used as `assets/car-top.png` once its white background is removed. The **3/4 front view** is a good hero or poster image, but the driving road needs a pure side profile, so generate that view with prompt 1 and attach the 3/4 render as a reference.

`index.html` checks for these files on load. When a file exists, the photo replaces the drawn SVG car. When it doesn't, the SVG car is shown, so the page always works.

---

## 1. Side view (hero)

```
Ultra-realistic studio photograph of a modern premium mid-size SUV, perfect side profile view (exact 90 degree side elevation), car facing RIGHT.
Pearl white glossy paint, gloss black two-tone roof, black A/B/C pillars and dark tinted windows, thin chrome window line, black wheel-arch cladding and black lower side sills, slim LED headlight, red LED tail light, black door mirrors with white caps.
Large 20-inch multi-spoke silver alloy wheels with dark tyres.
Clean black "CNIQ" lettering decal on the front door, bold geometric sans-serif, letter-spaced.
No manufacturer badges, no logos, no number plate, no people.
Pure seamless white background (#FFFFFF), soft contact shadow directly under the tyres, even softbox lighting, crisp reflections.
Car centred and filling the frame edge to edge, tyres touching the bottom edge of the image.
Automotive catalogue quality, 8K, sharp focus, photorealistic.
```

## 2. Top view (aerial and dashboard road)

Generate this **after** the side view. Where the tool allows it, attach the side-view image as a reference so the car stays the same.

```
Ultra-realistic top-down orthographic photograph of the SAME modern premium mid-size SUV seen exactly from above (bird's-eye view, 90 degrees straight down), front of the car pointing UP.
Pearl white glossy hood and body, gloss black roof with a large dark panoramic glass sunroof, black roof rails, dark tinted windscreen and rear window, white door-mirror caps, slim LED headlights at the top, red LED tail lights at the bottom.
Symmetrical, perfectly straight, no perspective distortion.
No badges, no logos, no number plate, no people.
Isolated on a pure solid black background (#000000) with a soft natural shadow around the car.
Car centred, filling the full height of a tall portrait frame.
Automotive catalogue quality, 8K, sharp focus, photorealistic.
```

After generating, remove the background (any background-removal tool) and export a **transparent PNG**, so the car sits on the page's asphalt road.

## 3. Optional: aerial road scene (background only)

```
Cinematic aerial drone photograph looking straight down on an empty dark asphalt road curving gently from bottom-left to top-right at night, dashed white centre line, subtle light streaks, fine asphalt texture, moody low-key lighting, no cars, no people, no text.
Wide 16:9, photorealistic, 8K.
```

## Negative prompt (if the tool supports one)

```
3/4 view, perspective angle, cropped car, cut-off wheels, extra wheels, distorted wheels, warped body, text errors, misspelled lettering, brand logos, badges, licence plate, watermark, people, busy background, low resolution, blurry, cartoon, illustration
```

## Tips for matching the reference picture

- **Same car in both views:** generate the side view first, then use it as the reference or "remix" image for the top view, and repeat "the SAME SUV" in the prompt.
- **Lettering:** image generators often misspell short words. If "CNIQ" comes out wrong, generate the car without lettering. The SVG car already carries the CNIQ mark, and you can add the decal to the photo in any editor.
- **Facing direction matters:** the side view must face **right** (the direction of travel) and the top view must point **up**. The animation rotates the top view along the road, so a car that points another way will drive sideways.
- **Size:** about 2400 × 920 px for the side view and 1000 × 2000 px for the top view is plenty. Compress the PNGs (for example with TinyPNG) to keep the page fast.
