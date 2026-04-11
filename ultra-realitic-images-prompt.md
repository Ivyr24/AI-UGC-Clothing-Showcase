---
name: ugc-ultra-realistic-clothing-photo-prompt
description: "Generate highly detailed, ultra-realistic AI photo prompts for UGC-style full-body clothing showcase images. The default output format is always vertical 9:16 (portrait/smartphone orientation). Optimised for full-body mirror selfies showing how clothing fits and looks on an influencer model. Every prompt must look like a real person filming herself in front of a mirror, showing off a new outfit she loves."
---

# UGC Ultra-Realistic Clothing Photo Prompt Generator

Generate objective, highly specific, production-ready AI image prompts that produce ultra-realistic UGC-style full-body clothing photos. Every prompt MUST be so specific that a human photographer could recreate it — with concrete numbers, real-world lighting, exact body positioning, fabric details, and named background objects.

> **Default format: vertical 9:16 (portrait orientation)**. Every prompt specifies `vertical 9:16 frame`.

---

## Core Philosophy: Clothing First, Face Second

Unlike beauty/skincare prompts (face fills 60-90%), clothing prompts prioritise **full-body visibility**. The garment is the hero — the model's face and expression support the outfit, not the other way round.

| Beauty Prompt (BAD for clothing) | Clothing Prompt (GOOD) |
|----------------------------------|----------------------|
| "Close-up selfie, face ~85% of frame" | "Full-body mirror selfie, model fills ~85% frame height, face ~30%" |
| "She holds a product near chin" | "She's wearing the high-waisted jeans from @product, fabric hugging hips" |
| "Bathroom vanity background" | "Bright bedroom with full-length mirror, clothing rack, trainers by door" |
| "Sharp focus on face and product" | "Sharp focus on model and clothing simultaneously, fabric texture visible" |

**Rule**: The entire outfit must be visible from head to toe. Face occupies ~25-35% of frame. The clothing fit, texture, and movement potential must be clearly communicated.

---

## Master Formula — Every Prompt Must Contain These 11 Layers

Write the prompt as **one flowing paragraph** (never a numbered list). Weave all 11 layers naturally in this order:

```
1. SHOT TYPE          -> "Ultra-realistic full-body [mirror selfie/standing shot] smartphone photo"
2. CAMERA ANGLE       -> "Phone held at [chest/face] height, [mirror reflecting full body / tripod-level wide]"
3. BODY OCCUPATION    -> "Model fills ~[80-90]% of vertical 9:16 frame height, face ~[25-35]%"
4. EXPRESSION         -> [Confident happy smile + eye direction + why she feels this way]
                         MANDATORY: enthusiasm and happiness — genuine smile, bright eyes, 
                         positive energy. NEVER neutral, flat, or deadpan.
5. CLOTHING DETAIL    -> [Full @product description: garment type, fit, colour, texture, 
                         details (buttons, stitching, wash, pattern), how it sits on body 
                         (hugs hips, drapes shoulders, cinches waist, tapers at ankle)]
6. POSE               -> [Standing pose adapted to clothing type: weight on one leg, hand 
                         on hip, relaxed stance, arm at side — shows garment silhouette]
7. FOOTWEAR + STYLING -> [Shoes that complement outfit + accessories (jewellery, belt, bag)]
8. FOCUS              -> "Sharp focus on model and clothing simultaneously, fabric texture visible"
9. ENVIRONMENT        -> [Room type + full-length mirror + 2-3 NAMED background objects] 
                         softly blurred bokeh
10. LIGHTING          -> [Source + direction + colour temperature — bright natural daylight 
                         preferred for true-colour fabric rendering]
11. SKIN + FABRIC REALISM -> [Skin: visible pores, stray hairs, no filter. Fabric: visible 
                         weave/texture, natural creases, stitching detail, how light catches 
                         material, realistic drape]
```

---

## Step 1 — Gather Clothing Information

Before writing, collect (or infer from `@product`):

- **Garment type** (jeans, dress, top, jacket, skirt, set, jumpsuit, activewear)
- **Fit** (slim, relaxed, oversized, tailored, high-waisted, low-rise, cropped)
- **Colour + wash** (medium wash denim, navy ribbed knit, cream silk, black structured)
- **Texture + material** (denim, cotton, silk, knit, linen, polyester blend, leather)
- **Details** (buttons, zip, pockets, pattern, embroidery, distressing, stitching)
- **How it sits on the body** (hugs hips, drapes from shoulders, cinches at waist, flows from hip)
- **Complementary styling** (what shoes, accessories, and other clothing complete the look)

---

## Step 2 — Specify Body Occupation by Shot Role

Full-body shots need precise body-to-frame ratios:

| Shot Role | Face % | Body Height % | Use When |
|-----------|--------|---------------|----------|
| **Full-body mirror selfie** | 25-30% | 85-90% | Default — shows complete outfit head to toe |
| **Full-body standing (tripod)** | 20-25% | 90-95% | When mirror isn't appropriate, more editorial |
| **Three-quarter body** | 30-40% | 70-80% | Tops, jackets — waist-up emphasis |

> **Always state the exact percentage in the prompt** — don't write "full body," write "model fills ~85% of vertical 9:16 frame height, face ~30%."

---

## Step 3 — Specify Camera Angle for Clothing

| Term | Meaning | Best For |
|------|---------|----------|
| **"Phone at chest height, mirror reflecting full body"** | Classic TikTok mirror selfie | Default — most authentic UGC feel |
| **"Phone at face height, slight downward angle"** | Higher selfie angle, elongates body | Flattering for most body types |
| **"Propped at waist height, slight upward angle"** | Low-angle, makes legs look longer | Jeans, trousers, skirts |
| **"Tripod-level, straight-on"** | No mirror, direct shot | Editorial, OOTD posts |

> **Writing rule**: always specify phone/camera position AND the resulting angle — e.g., "phone held at chest height, mirror reflecting full body head to toe, slight downward angle."

---

## Step 4 — Specify Clothing Detail with Precision

This is the most important layer for clothing prompts. Describe the garment as specifically as a stylist would:

### Clothing Description Formula

```
Wearing [fit] [garment type] in [colour/wash] from @product — [material/texture], 
[key construction detail (stitching, buttons, zip, pockets)], 
[how it sits on body (hugs, drapes, cinches, flows)], 
[hem/ankle/neckline detail], [any pattern or distressing].
```

### Examples by Category

| Category | Good Clothing Description |
|----------|--------------------------|
| **Jeans** | "Wearing high-waisted slim-fit jeans in medium-wash blue denim from @product — visible topstitching at pockets, slight natural creasing at knees, fabric hugging hips and thighs with flattering fit, tapered ankle sitting just above her white trainers, subtle fading at thighs, copper button at waistband" |
| **Dress** | "Wearing a midi wrap dress in sage green satin from @product — V-neckline with self-tie waist, fabric draping smoothly from bust to hip then flowing to mid-calf, subtle sheen catching window light, gentle gather at the waist creating an hourglass silhouette, hem skimming her calves" |
| **Top** | "Wearing a fitted ribbed crop top in off-white cotton from @product — fine rib texture visible, crew neckline sitting flat, fabric following the curve of her torso without pulling, cropped hem ending 3cm above her waistband, short sleeves hugging upper arms" |
| **Jacket** | "Wearing an oversized leather biker jacket in black from @product — asymmetric silver zip, structured shoulders extending 2cm past natural shoulder line, supple leather with natural grain visible, sitting open over a white tee, hem hitting at hip level" |
| **Skirt** | "Wearing a pleated midi skirt in dusty rose from @product — knife pleats falling from a flat waistband, lightweight fabric with visible pleat structure, hem ending at mid-calf, gentle A-line silhouette, fabric catching light in the fold creases" |

> **NEVER write**: "wearing jeans." **ALWAYS write**: fit, colour/wash, material, construction details, how it sits on the body, hem detail.

---

## Step 5 — Specify Pose Adapted to Clothing Type

The pose must show the garment's best features:

| Clothing Type | Recommended Pose | Why |
|---------------|-----------------|-----|
| **Jeans/Trousers** | Weight on one leg, opposite knee slightly bent, one hand on hip | Shows hip fit, thigh silhouette, creates natural body curve |
| **Dress** | Standing with slight hip shift, one arm relaxed, other touching hair or waist | Shows drape, waist definition, overall silhouette |
| **Top/Blouse** | Shoulders back, one hand at side, other holding phone (mirror selfie) | Shows neckline, sleeve fit, torso shape |
| **Jacket/Coat** | One hand in pocket or on lapel, shoulders square | Shows structure, length, how it sits open/closed |
| **Skirt** | Weight shifted to one hip, creating natural fabric movement | Shows pleat/fabric fall, waist fit, hem length |
| **Set/Co-ord** | Relaxed confident stance, both arms visible | Shows full coordination of pieces |

---

## Step 6 — Specify Lighting for True Colour Rendering

Clothing prompts need **bright, true-colour lighting** — the viewer must see the real colour and texture of the fabric.

### Light Source Library (Clothing-Optimised)

| Source | When to Use | How to Write |
|--------|-------------|--------------|
| **Bright natural window light** | Default for all clothing | "Bright natural window light from camera-left, 5500K daylight, true-colour rendering of fabric — no warm cast distorting garment colour" |
| **Soft diffused daylight** | Overcast day, even lighting | "Soft diffused daylight from large window, even illumination across full body, no harsh shadows, fabric colour appears true to life" |
| **Ring light + window** | TikTok creator vibe | "Ring light reflection in mirror, warm 4800K frontal fill, supplemented by window light from camera-right for depth" |
| **Golden hour bedroom** | Warm, cosy outfit shots | "Low golden-hour sunlight from window camera-left, warm amber tones, fabric catches warm highlights on one side" |

> **Critical**: Clothing needs bright, even lighting to show true colour. Dark or moody lighting hides fabric detail and distorts colour perception.

---

## Step 7 — Specify Environment with Full-Length Mirror

Clothing showcase environments must include a **full-length mirror** and feel like a real bedroom/hallway.

### Environment Library

| Setting | Room | Named Background Objects (pick 2-3) |
|---------|------|-------------------------------------|
| **Bedroom mirror** | Bright bedroom | "Full-length mirror on wall, unmade linen bed, wooden clothing rack with hangers, white trainers by the door" |
| **Hallway mirror** | Bright hallway | "Full-length freestanding mirror, coat hooks on wall, shoe rack, door frame visible" |
| **Closet/Dressing area** | Walk-in closet | "Full-length door mirror, shelves with folded clothes, hanging rail with coloured hangers, shoe boxes stacked" |
| **Bathroom (large)** | Bright bathroom | "Large wall mirror, marble countertop, folded towels, small plant" |

### Writing Rule

```
[Room type] with full-length [mirror type], [object 1], [object 2], [object 3] — 
softly blurred bokeh, model and clothing in sharp focus, 
[lived-in detail — "not staged, personal space feel"]
```

---

## Step 8 — Specify Skin + Fabric Realism

AI defaults to plastic skin AND plastic fabric. Fight both every time:

### Skin Realism (include 3-4 per prompt)

- "Visible pores across cheeks and nose"
- "Stray hairs at hairline"
- "Natural skin texture, no filter, no smoothing"
- "Subtle under-eye shadows"
- "Fine flyaway hairs catching the light"

### Fabric Realism (include 3-4 per prompt)

- "Visible denim weave / rib texture / knit pattern"
- "Natural creasing at joints (knees, elbows, waist)"
- "Stitching detail visible at seams and pockets"
- "Fabric catching light differently at angles (sheen, matte)"
- "Slight fading at wear points (thighs, elbows)"
- "Natural drape — fabric follows gravity, not painted on"
- "Subtle wrinkles from sitting/moving — not freshly ironed"
- "Button/zip hardware with realistic metallic sheen"

> **Fabric rule**: Write at least **3 specific fabric details** per prompt. Example: "Visible denim weave at thighs, natural creasing at knees, topstitching at pockets catching the light, subtle fading where fabric stretches."

---

## Step 9 — Compose the Full Prompt

Combine all 11 layers into one flowing paragraph.

### Gold Standard Template (Jeans)

```
@influencer @product

"Ultra-realistic full-body mirror selfie, phone held at chest height angled 
slightly downward, full body visible head to toe in a large bedroom mirror, 
model fills ~85% of vertical 9:16 frame height, face ~30%; confident happy 
smile, bright eyes looking at phone screen in mirror, genuine enthusiasm — 
'look at my new jeans' energy. Wearing high-waisted slim-fit jeans in 
medium-wash blue denim from @product — visible topstitching at pockets, 
slight natural creasing at knees, fabric hugging hips and thighs with 
flattering fit, tapered ankle, subtle fading at thighs, copper button at 
waistband. Paired with a fitted white cropped tee and white trainers. 
Standing with weight on right leg, left knee slightly bent, left hand resting 
on hip, right hand holding phone. Sharp focus on model and clothing, fabric 
texture visible. Bright bedroom with full-length mirror on wall, unmade linen 
bed, wooden clothing rack with hangers, white trainers by the door — softly 
blurred bokeh, lived-in personal space. Bright natural window light from 
camera-left, 5500K daylight, true-colour rendering of denim wash, gentle 
shadow along her right side. Visible skin pores, stray hairs at hairline, 
natural skin texture — no filter. Visible denim weave, natural creasing at 
knees, stitching catching light, realistic drape — not painted on. 
Mood: confident, bright, authentic mirror selfie.
Negative: CGI, cartoon, airbrushed skin, plastic texture, plastic fabric, 
text, watermark, extra fingers, mannequin pose, catalogue shot, studio 
backdrop, overly posed, fashion editorial, DSLR bokeh."
```

### Gold Standard Template (Dress)

```
@influencer @product

"Ultra-realistic full-body mirror selfie, phone held at face height, full 
body visible head to toe in a hallway freestanding mirror, model fills ~85% 
of vertical 9:16 frame height, face ~28%; warm genuine smile with bright 
eyes, slight head tilt, looking at phone screen — excited to show off new 
dress. Wearing a midi wrap dress in sage green satin from @product — 
V-neckline with self-tie waist, fabric draping smoothly from bust to hip 
then flowing to mid-calf, subtle sheen catching window light, gentle gather 
at the waist, hem skimming her calves. Paired with nude strappy heels and 
small gold hoop earrings. Standing with slight hip shift to the left, right 
arm relaxed at side, left hand holding phone. Sharp focus on model and 
clothing, satin sheen visible. Bright hallway with freestanding full-length 
mirror, coat hooks on wall, shoe rack, door frame visible — softly blurred 
bokeh, natural home setting. Soft diffused daylight from window behind 
camera, even illumination, fabric colour appears true to life, satin 
highlights on the hip and waist. Visible skin pores, stray hairs, natural 
texture — no filter. Satin weave catching light, natural fabric flow 
following gravity, subtle fold creases at waist gather, hem weight pulling 
fabric into natural drape. Mood: elegant but effortless, real girl showing 
a beautiful dress.
Negative: CGI, cartoon, airbrushed skin, plastic texture, stiff fabric, 
text, watermark, extra fingers, mannequin pose, catalogue shot, studio 
backdrop, fashion editorial, DSLR."
```

### Gold Standard Template (Top)

```
@influencer @product

"Ultra-realistic three-quarter body mirror selfie, phone held at chest 
height, visible from head to upper thigh in a bedroom mirror, model fills 
~80% of vertical 9:16 frame height, face ~35%; bright enthusiastic smile, 
eyes meeting camera through mirror, confident and happy. Wearing a fitted 
ribbed crop top in off-white cotton from @product — fine rib texture visible, 
crew neckline sitting flat, fabric following the curve of her torso without 
pulling, cropped hem ending 3cm above her blue denim waistband, short 
sleeves hugging upper arms. Paired with high-waisted blue jeans and small 
gold pendant necklace. Standing with shoulders back, right hand holding 
phone, left arm relaxed at side. Sharp focus on model and clothing, rib 
texture visible. Bright bedroom with full-length wardrobe mirror, unmade 
bed with white duvet, small bedside plant, fairy lights on headboard — 
softly blurred bokeh, cosy personal space. Bright natural window light from 
camera-right, 5500K, true-colour cotton rendering, soft shadow along left 
side. Visible pores, stray hairs at hairline, natural skin — no filter. 
Fine rib texture visible across torso, natural fabric stretch at bust, 
slight wrinkle at side seam, cotton catching light evenly. 
Mood: casual, bright, 'new top' excitement.
Negative: CGI, cartoon, airbrushed skin, plastic texture, stiff fabric, 
text, watermark, extra fingers, mannequin pose, catalogue shot, studio 
backdrop, DSLR."
```

---

## Step 10 — Negative Prompt Block (Always Append)

Always end with a negative prompt tailored for clothing:

```
Negative: CGI, cartoon, airbrushed skin, plastic texture, plastic fabric, 
stiff fabric, text, watermark, captions, extra fingers, mutated hands, 
deformed limbs, mannequin pose, catalogue shot, studio backdrop, 
fashion editorial, overly posed, stock photo, DSLR bokeh, commercial 
lighting, showroom interior.
```

### Context-Specific Negatives (add as needed)

- **Denim**: "ironed denim, brand-new stiff jeans, no creasing"
- **Silk/Satin**: "matte fabric, no sheen, cardboard drape"
- **Activewear**: "gym photoshoot, professional fitness shoot"
- **Formal**: "red carpet, professional studio, too polished"

---

## Step 11 — Character Consistency Brief

When using the same influencer across multiple images, reference via `@influencer`:

- **`@influencer`** — ALWAYS present on the first line (same face, skin, hair, body type)
- **`@product`** — ALWAYS present on the first line (correct garment, exact colour, texture, details)
- **Same accessories** word-for-word across all prompts (jewellery, shoes, belt)
- **Same hair state** (up/down, styled/natural)

---

## Platform-Specific Adjustments

### TikTok / Default (Mirror Selfie UGC)

- **Always use: `vertical 9:16 frame`**
- Add: "front-facing selfie camera, mirror reflection, candid creator energy, raw and unedited"
- Phone visible in reflection for authenticity

### Instagram Reels

- Still 9:16 vertical
- Slightly more polished: "warm tones, aesthetically messy bedroom, effortlessly styled"
- Mirror selfie or propped-phone OOTD

### YouTube Shorts

- 9:16 vertical
- More editorial: "well-lit, full outfit visible, informative styling angle"

---

## Quality Checklist (run before outputting every prompt)

- [ ] Shot type = full-body (not close-up)
- [ ] Face ~25-35% of frame (not 60-90%)
- [ ] Full outfit visible head to toe
- [ ] Expression: enthusiastic, happy, confident (NEVER neutral/flat)
- [ ] Clothing described with: fit, colour/wash, material, construction details, how it sits on body
- [ ] `@influencer @product` markers on first line
- [ ] Pose adapted to clothing type
- [ ] Footwear + accessories specified
- [ ] "Sharp focus on model and clothing" stated
- [ ] Environment: full-length mirror + 2-3 NAMED background objects
- [ ] Lighting: bright, true-colour, source + direction specified
- [ ] Skin realism: 3+ imperfections + "no filter"
- [ ] Fabric realism: 3+ specific texture/detail mentions
- [ ] Negative prompt appended with clothing-specific terms
- [ ] 9:16 vertical stated
- [ ] Final mood line present
