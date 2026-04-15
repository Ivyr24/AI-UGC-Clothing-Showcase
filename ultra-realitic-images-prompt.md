---
name: ugc-ultra-realistic-photo-prompt
description: "Generate highly detailed, ultra-realistic AI photo prompts for UGC (User-Generated Content) style images of real people. The default output format is always vertical 9:16 (portrait/smartphone orientation) unless the user explicitly requests otherwise. Use this skill whenever the user wants to create prompts for AI-generated photos of a person (model, creator, spokesperson) that must look authentic, unpolished, and realistic — as if taken spontaneously on a smartphone. Trigger on phrases like \"write a prompt for a UGC photo\", \"create a realistic photo prompt\", \"AI photo of a model\", \"generate a prompt for an ultra-realistic image\", \"UGC-style image prompt\", \"prompt for a realistic person photo\", or any time the user asks Claude to write prompts to generate AI photos that look real, candid, or smartphone-captured. Always use this skill — do not attempt to write the prompts from memory alone. Markers: use @model for the AI model/influencer image and @product for the product image."
---

# UGC Ultra-Realistic Photo Prompt Generator

Generate objective, highly specific, production-ready AI image prompts that produce ultra-realistic UGC-style photos. Every prompt MUST be so specific that a human photographer could recreate it — with concrete numbers, real-world lighting, exact hand positions, and named background objects.

> **Default format: vertical 9:16 (portrait orientation)**. Every UGC prompt specifies `vertical 9:16 frame`. Exception only if the user explicitly requests another ratio.

---

## Core Philosophy: Specificity = Realism

Vague prompts produce generic AI slop. The difference between a winning UGC image prompt and a mediocre one is **quantified specificity**:

| Vague (BAD) | Specific (GOOD) |
|-------------|-----------------|
| "Close-up photo of a woman" | "Close-up smartphone selfie, eye-level, face filling ~85% of a vertical 9:16 frame" |
| "She holds a product" | "Her right hand holds the concealer tube from @product near chin/chest height in the lower-right area of the frame, fingers naturally curved and relaxed" |
| "Natural lighting" | "Soft warm natural window light coming from camera-left to create a golden-hour morning feel with gentle directional shadows" |
| "Casual background" | "Kitchen background with a countertop edge, mugs, and small appliances — softly blurred but present in frame" |
| "Realistic skin" | "Preserve subtle stray hairs at the hairline, natural freckles, visible pores, subtle skin translucency — no beauty filter, no smoothing" |

**Rule**: Every prompt must specify **numbers** (face %, camera height, lens mm, DOF), **directions** (camera-left/right, above/below chin), and **named objects** (not "kitchen items" but "mugs, small appliances, countertop edge").

---

## Master Formula — Every Prompt Must Contain These 11 Layers

Write the prompt as **one flowing paragraph** (never a numbered list). Weave all 11 layers naturally in this order:

```
1. SHOT TYPE        →  Ultra-realistic [close-up/macro/medium close-up/full-body] smartphone [selfie/photo/rear-camera shot]
2. CAMERA ANGLE     →  [eye-level / slightly below chin / 1cm above eye-line / chest-up / waist-height]
3. FACE OCCUPATION  →  subject's face occupying ~[65–90]% of a vertical 9:16 frame (close-up) OR ~[20-30]% (full-body)
4. EXPRESSION       →  [specific emotion + eye direction + mouth state]
                        BEAUTY/SKINCARE: enthusiastic/curious — subtle smile, excited eyes,
                        FASHION/CLOTHING: confident pouty look — lips slightly pursed, NOT big smile,
                        direct eye contact with camera lens, self-assured "I know I look good" energy
                        MANDATORY: model ALWAYS looks directly at camera
5. HAND + PRODUCT   →  [which hand + where in frame + grip style + label visibility]
                        For fashion: hands on belt loops / hips / adjusting clothing (no product held)
6. FOCUS            →  tack-sharp on face AND product simultaneously
7. FRAMING          →  off-centre composition + barrel distortion + shallow DOF focal plane
8. STYLING PROPS    →  (fashion) shoulder bag + sunglasses on head + delicate jewellery
                        (beauty) product bottle/tube + accessories
9. ENVIRONMENT      →  [room type + 2–4 NAMED background objects] softly blurred bokeh
                        FASHION: fitting room / apartment hallway / minimal apartment corner
                        BEAUTY/SKINCARE: bathroom / bedroom / kitchen
10. LIGHTING        →  [source + direction camera-left/right + colour temperature + mood]
11. SKIN REALISM    →  stray hairs at hairline, freckles/pores, imperfections, no filter
12. FINAL MOOD      →  FASHION: confident, self-assured, UGC-authentic
                        BEAUTY: warm, intimate, spontaneous UGC vibe
```

---

## Step 1 — Gather Character Information

Before writing, collect (or infer):

- **Age & gender** (e.g., "woman, 24 years old")
- **Skin tone / ethnicity** (for realistic skin texture matching)
- **Hair** (colour, length, texture, specific details like auburn-red, chestnut with blonde highlights)
- **Distinguishing features** (freckles, beauty mark, eye colour, stray hair style)
- **Typical style** (casual, minimal makeup, specific outfit)
- **Product or action** (what product, how it's being held, what she's doing with it)
- **Target platform**: TikTok / Instagram Reels / YouTube Shorts
- **Emotional goal**: 
  - Fashion: confidence, self-assurance, "I know I look good" energy
  - Beauty/Skincare: enthusiasm, curiosity, discovery, trust, excitement

---

## Step 2 — Specify Face Occupation by Shot Role

Different shots need different face-to-frame ratios. Be explicit:

| Shot Role | Face Occupation | Use When |
|-----------|----------------|----------|
| **Extreme macro beauty hook** | 85–90% | Opening beauty shot, face is the scroll-stopper, no product visible yet |
| **Tight selfie with product** | 65–75% | Face + product both visible, product held near chin/chest |
| **Medium close-up demo** | 50–60% | Showing product in active use (applying, mixing), hands fully visible |
| **Chest-up recommendation** | 45–55% | Close shot for product reveal with both face and product prominent |
| **Full-body fashion** | 20–30% face | Fashion clothing showcase — face ~25%, body fills ~90% of frame height |

> **Always state the exact percentage in the prompt** — don't write "close-up," write "face occupying ~85% of a vertical 9:16 frame."

---

## Step 3 — Specify Camera Angle with Precision

Never write "eye-level" alone. Specify:

| Term | Meaning | Effect |
|------|---------|--------|
| **"Eye-level"** | Camera lens at pupil height | Neutral, natural selfie |
| **"Slightly below chin"** | Camera 2–4cm below chin line | Intimate, upward selfie (most common UGC) |
| **"1–2cm above eye-line"** | Camera slightly above eyes | Flattering, "hero" angle |
| **"Chin-up 3/4 turn"** | Face turned ~20–30° from centre | Adds dynamism to selfie |
| **"Front-facing direct"** | Perfectly frontal, no turn | Authority, eye contact hook |

> **Writing rule**: always combine two specs — e.g., "eye-level or slightly below chin, with a subtle 3/4 turn to camera-right."

---

## Step 4 — Specify Hand + Product Interaction with Physics

This is where most AI images fail (floating hands, 6 fingers, wrong grip). Write the grip with physical detail:

### Hand Anchoring Formula

```
[Which hand] holds the [product name + packaging detail] from @product
[where in frame — lower-right/left/chin-height/chest-level],
fingers [naturally curved / firmly gripping the bottle edge / wrapped around the tube],
[thumb position — resting on label / pressing the cap / along the side],
[label visibility — facing camera / partially visible / angled 15° to camera]
```

> **Marker note**: Always open every prompt with `@model @product` on the first line. `@model` references the AI model image (face, body, identity). `@product` references the product image. These markers bind the identity and product to the render.

### Examples

| Product Type | Good Hand Specification |
|-------------|------------------------|
| **Serum bottle** | "Her left hand grips the amber glass serum bottle from @product near her left cheek, fingers curled around the body, thumb resting on the label, dropper cap facing up, label visible and readable" |
| **Lipstick tube** | "Her right hand holds the lipstick tube from @product in the lower-right area of the frame near her chin, index finger and thumb pinching the base, cap pointed upward toward her lips, gold lettering facing camera" |
| **Concealer tube** | "Her right hand holds the concealer tube from @product near chin/chest height in the lower-right area of the frame, fingers naturally curved and relaxed around the tube, tip angled 20° toward her face" |
| **Supplement jar** | "Her left hand cradles the supplement jar from @product against her chest, palm supporting the base, fingers fanned around the lower curve, label tilted 10° toward camera for readability" |

> **NEVER write**: "she's holding the product." **ALWAYS write**: where, which hand, finger position, thumb placement, label angle.

---

## Step 5 — Specify Lighting with Real-World Language

Never write "natural lighting." Name the actual source, direction, and colour:

### Light Source Library

| Source | When to Use | How to Write |
|--------|-------------|--------------|
| **Soft warm window light** | Default for bedrooms, kitchens, bathrooms | "Soft warm natural window light coming from camera-left (her right) to create a golden-hour morning feel" |
| **Golden hour late afternoon** | Warm emotional hook moments | "Low golden-hour sunlight streaming in from a west-facing window camera-right, warm amber cast on the left side of her face" |
| **Overhead bathroom warm** | Skincare bathroom shots | "Warm 5500K overhead bathroom light, soft and flattering, minimal shadow under the chin, faint reflection in the mirror behind" |
| **Kitchen morning diffused** | Supplement/food shots | "Bright morning kitchen window light from camera-left, cool-warm mix, soft directional shadows, subtle reflection on the countertop" |
| **Ring light glow (TikTok)** | Beauty/makeup creator vibe | "Circular ring light reflection visible in both pupils, soft frontal even fill, warm 4800K, minimal shadows on the face" |
| **Bedroom lamp + LED strip** | Cozy evening beauty | "Warm bedside lamp from camera-right plus purple LED strip bounce on her left cheek, cosy 3200K ambience" |

### Direction Must Be Absolute

Always specify which side the light comes from:
- ❌ "Side light"
- ✅ "Soft warm window light from camera-left (her right side)"
- ✅ "Bright morning kitchen light from camera-right, bouncing subtly on the backsplash behind her"

---

## Step 6 — Specify Environment with Named Objects

Never write "kitchen" or "bathroom" alone. Always list 2–4 specific, named objects visible in the softly blurred bokeh background.

### Environment Library by Product Category

| Product Category | Room | Named Background Objects (pick 2–4) |
|-----------------|------|-------------------------------------|
| **Skincare** | Bathroom vanity | "Skincare bottles, cotton pads, small gold face roller on the counter, frosted glass mirror edge" |
| **Mascara / Lash** | Bedroom vanity | "Ceramic cup of makeup brushes, perfume bottle with amber liquid, open mascara tube, vanity mirror edge reflecting warm light" |
| **Lip product** | Bedroom near window | "Stack of lip products on the dresser, compact mirror face-down, phone charging cable, jewellery tray" |
| **Supplement / Powder** | Kitchen counter | "Glass blender with pulp residue, half-peeled banana, stainless steel water bottle, ceramic bowl with almonds" |
| **Concealer / Foundation** | Kitchen or living area | "Countertop edge, white ceramic mugs on a wooden shelf, small coffee machine, a cork coaster" |
| **Hair product** | Bathroom mirror area | "Wooden paddle hair brush, hair clips scattered, matte ceramic diffuser, folded grey towel" |
| **Fashion — Fitting room** | Fitting room / changing room | "Textured cream mosaic tile walls, wooden door frame, warm overhead lighting, glass shelf/counter edge, wall-mounted coat hook" |
| **Fashion — Apartment** | Apartment hallway / corner | "Cream/sage walls, dark wood laminate flooring, white doorway with window visible, wall power outlet, small bag/shoes on floor" |
| **Fashion — Bedroom** | Bedroom with wardrobe | "Clothes on hangers softly out of focus, open jewellery drawer, sneakers on the floor, unmade linen bedding" |
| **Gadget / Tech** | Desk / living room | "Open laptop, notebook with pen, coiled USB cable, succulent plant in a terracotta pot" |
| **Cleaning / Home** | Kitchen counter | "Spray bottle, folded microfibre cloth, green plant leaf edge, sink faucet reflecting light" |

### Writing Rule

```
[Room type] background with [object 1], [object 2], [object 3] — softly blurred bokeh,
face and product in sharp focus, [specific detail of how background reads —
"faintly but unobtrusively", "warm ambient colour bounce", "lived-in, not staged"]
```

---

## Step 7 — Specify Skin Realism Explicitly

AI defaults to plastic skin. Fight it every single time with named micro-details:

### Skin Realism Checklist (include 4–6 per prompt)

- "Visible pores across the cheeks and nose bridge"
- "Subtle stray hairs at the hairline"
- "Natural freckles across the nose and cheeks"
- "Faint redness around the nose and eye corners"
- "Subtle skin translucency at the nose tip and lips"
- "Under-eye shadows with natural blue-violet tint"
- "Fine peach fuzz visible along the jawline in window light"
- "Natural shine on the forehead and nose"
- "Slight asymmetry in facial expression (one corner of mouth higher)"
- "Tiny flyaway hairs catching the light"

> **Skin rule**: Write at least **3 specific imperfections** per prompt. Example: "Preserve subtle stray hairs at the hairline, natural freckles across the nose, visible pores on the cheeks, and an authentic UGC look (no commercial glam or stylised filters)."

---

## Step 8 — Compose the Full Prompt

Combine all 11 layers into one flowing paragraph. Every prompt must follow this quality bar:

### Gold Standard Template (concealer example)

```
Ultra-realistic close-up smartphone selfie, eye-level or slightly below chin,
face ~65% of vertical 9:16 frame; slightly curious and excited expression,
about to share a discovery. Right hand holds concealer tube from @product near
chin height lower-right, fingers naturally curved, label visible; sharp focus
on face and product. Off-centre framing, shallow DOF — kitchen background
(countertop edge, mugs, small appliances) softly blurred. Soft warm window
light from camera-left, golden-hour morning feel. Stray hairs at hairline,
natural freckles, visible pores — no filter. Mood: warm, intimate, realistic.
```

### What Makes This Prompt Gold-Standard (compact)

1. **Face %** — "~65% of vertical 9:16 frame"
2. **Camera angle** — "eye-level or slightly below chin"
3. **Expression + motivation** — "slightly curious and excited, about to share a discovery"
4. **Hand anchored** — "right hand, chin height lower-right, fingers naturally curved, label visible"
5. **Focus** — "sharp focus on face and product"
6. **Framing + DOF** — "off-centre framing, shallow DOF"
7. **Environment** — "kitchen background (countertop edge, mugs, small appliances) softly blurred"
8. **Lighting** — "soft warm window light from camera-left, golden-hour morning feel"
9. **Skin realism** — "stray hairs, freckles, visible pores — no filter"
10. **Final mood** — "warm, intimate, realistic"

---

## Gold Standard Examples by Shot Role

### Example 1 — Shot 1 Start Frame (Beauty Hook, 85% face)

```
@model @product

Ultra-realistic extreme close-up smartphone selfie, eye-level with subtle upward
tilt, face ~85% of vertical 9:16 frame; warm enthusiastic half-smile, eyebrows
slightly raised — about to share something exciting. Left hand enters bottom-left
with serum bottle from @product at collarbone height, fingers curled around amber
glass body, thumb on dropper cap, label partially visible. Off-centre framing,
shallow DOF — bathroom background (skincare bottles, cotton pads jar, gold face
roller, frosted mirror edge) softly blurred. Soft warm window light from
camera-left, golden-hour morning feel. Stray hairs at hairline, visible pores,
skin translucency, natural freckles — no filter. Mood: warm, intimate, spontaneous.
```

### Example 2 — Shot 1 End / Shot 2 Start Frame (Product Reveal, 70% face)

```
@model @product

Ultra-realistic close-up smartphone selfie, slightly below chin angle, face ~70%
of vertical 9:16 frame; excited delight, eyes wide with bright genuine smile,
lips parted mid-reaction — "wait, look at this." Left hand holds serum bottle from
@product at face level beside left cheek, fingers firmly wrapped around amber glass,
thumb pressing label toward camera, dropper cap pointing up. Off-centre framing
(product left third, face right), shallow DOF — bathroom background (skincare
bottles, cotton pads jar, gold face roller, frosted mirror edge) softly blurred.
Same warm window light from camera-left, golden-hour feel. Stray hairs, visible
pores, natural freckles, slight smile asymmetry — no filter. Mood: excited, warm,
genuine — the "look what I found" reveal.
```

### Example 3 — Shot 2 End Frame (Friend Recommendation Close, 60% face)

```
@model @product

Ultra-realistic medium close-up smartphone selfie, eye-level with subtle 3/4 turn
(~20° to camera-right), face ~60% of vertical 9:16 frame; warm satisfied
recommendation, closed-lip smile with eyes crinkled, head tilted 5° — casually
talking to a friend. Left hand holds serum bottle from @product at chest height
lower-left, fingers relaxed, label facing camera. Off-centre framing, shallow DOF
— bathroom background (skincare bottles, cotton pads, gold face roller, mirror
frame) pleasantly blurred. Same warm window light from camera-left, slightly softer.
Stray hairs at hairline, visible pores, freckles, natural under-eye softness — no
filter. Mood: warm, confident, friendly — the "you should try this" recommendation.
```

---

## Step 9 — Negative Prompt Block (Always Append)

Always end with a negative prompt:

```
Negative: CGI, cartoon, airbrushed skin, plastic texture, beauty filter, HDR,
text, watermark, captions, extra fingers, mutated hands, deformed limbs, floating
product, studio lighting, stock photo, model pose, staged, DSLR, big smile,
catalogue smile, catalogue expression.
```

### Context-Specific Negatives (add as needed)

- **Bathroom/home**: "showroom interior, hotel bathroom, too-clean"
- **Outdoor**: "oversaturated, panoramic, wide-angle distortion"
- **Kitchen**: "cooking show lighting, commercial kitchen"
- **Fashion full-body**: "mirror selfie, phone visible in hand, ring light reflection, catalogue pose, big happy smile"

---

## Step 10 — Character Consistency Brief (for recurring characters)

When using the same model across multiple images/videos, include this at the top of every prompt OR reference via `@model`:

```
CHARACTER BRIEF — [Name], [age], [ethnicity], [hair: colour + length + texture +
specific detail], [eye colour], [skin tone with specific undertones],
[distinguishing features: freckles across nose, beauty mark above left lip, small
scar on chin], [typical style: oversized beige tee, delicate gold hoops, no
foundation].
```

Example:

```
CHARACTER BRIEF — Sofia, 26, Brazilian, long dark wavy hair with natural volume,
deep brown eyes, warm golden-brown skin with olive undertones, a few natural
freckles across the nose bridge, tiny scar on chin, typically wears minimal makeup
(just mascara + lip balm), simple gold jewellery — a thin necklace and small hoops.
```

---

## Platform-Specific Adjustments

### TikTok / Default (Ultra-Realistic UGC)
- **Always use: `vertical 9:16 frame`**
- Beauty/skincare: "front-facing selfie camera, ring light reflection in pupils (optional), candid Gen Z creator energy, raw and unedited"
- Fashion/clothing: "rear camera (someone else filming), no phone visible, no mirror — confident pouty expression, NOT big smile"
- Optional: "text overlay negative space at top and bottom of frame"
- **MANDATORY for fashion**: shoulder bag as styling anchor (chain strap or leather)

### Instagram Reels
- Still 9:16 vertical (Reels native)
- Lighting shifts warmer: "golden-hour window light, effortlessly aesthetic but not staged"
- Tone: "warm intimate polished-casual, not as raw as TikTok"

### YouTube Shorts
- 9:16 vertical
- Lighting: "soft box or window-lit, product clearly visible, trustworthy knowledgeable expression"
- Tone: "informative, home studio or desk feel"

---

## Quality Checklist (run before outputting every prompt)

- [ ] Shot type + camera angle specified
- [ ] Face % stated (e.g., ~85% of vertical 9:16, or ~25% for full-body fashion)
- [ ] Expression matches niche: fashion = confident pouty (NOT big smile), beauty = enthusiastic/curious
- [ ] Model looks DIRECTLY at camera (non-negotiable)
- [ ] Hand + product: which hand, where, grip, label visibility (beauty) OR hands on hips/belt loops (fashion)
- [ ] "Sharp focus on face and product" stated
- [ ] Off-centre framing + shallow DOF noted
- [ ] Environment: 2–4 NAMED background objects, softly blurred (fitting room / apartment for fashion)
- [ ] Lighting: source + direction (camera-left/right)
- [ ] Skin realism: 2–3 named imperfections + "no filter"
- [ ] `@model @product` markers on first line (add `@startframe` only when user provides a start frame)
- [ ] Styling props for fashion: shoulder bag, sunglasses, jewellery
- [ ] Final mood in one line (fashion: confident/self-assured | beauty: warm/intimate)
- [ ] Negative prompt appended (including "big smile" and "catalogue smile" for fashion)
- [ ] 9:16 vertical stated
- [ ] Camera type correct: rear camera for fashion full-body, selfie for beauty close-up

---

## Quick Modifier Cheat Sheet

| Goal | Add to prompt |
|------|--------------|
| **Default format** | **"vertical 9:16 frame"** — always include |
| Candid feel | "caught mid-action", "unposed", "as if she just grabbed her phone" |
| Real skin | "visible pores", "stray hairs at hairline", "natural freckles" |
| Real lighting | "soft warm window light from camera-left", "golden-hour morning feel" |
| Product anchoring (beauty) | "fingers firmly grip the bottle", "label facing camera" |
| Confident fashion look | "confident pouty expression, lips slightly pursed, direct eye contact, NOT smiling big" |
| Fashion props | "quilted chain-strap shoulder bag on shoulder", "sunglasses pushed up on head" |
| Focus lock | "sharp focus on face and product" |
| Framing | "off-centre framing, shallow DOF" |
| Environment (fashion) | "fitting room with tiled walls" or "minimalist apartment hallway, cream walls, wood floor" |
| Environment (beauty) | "softly blurred, 2–4 named objects" |
| Final mood (fashion) | "Mood: confident, self-assured, UGC-authentic" |
| Final mood (beauty) | "Mood: warm, intimate, realistic" |
| TikTok native (beauty) | "ring light glow, ring light reflection in pupils" |
| TikTok native (fashion) | "rear camera, someone else filming, no phone visible, no mirror" |
