---
name: ugc-motion-control
description: "Generate UGC motion control videos for any niche (fashion, beauty/makeup, skincare, accessories, lifestyle, etc.). Input: @model (AI model image — face, body, identity), @product (product image — clothing, makeup, skincare, etc.), and optionally @startframe (start frame extracted from a reference/model video whose motion will be transferred, ONLY when explicitly provided). Output: start frame analysis (if @startframe provided), 1 detailed start frame image prompt (matching the reference composition with the user's model + product), 1 concise motion control video prompt (the motion comes from the reference — prompt stays minimal), 3 engaging text overlay options with emojis (story-style EN UK, TikTok compliant), and product info with a compact title (format: '[item] here xx'). Trigger on: 'motion control', 'motion transfer', 'reference video UGC', 'start frame + reference', 'UGC video', 'clothing UGC', 'makeup UGC', 'beauty UGC', 'skincare UGC', 'product UGC', or any request involving a reference video whose motion should drive a generated video of a model with a product."
---

Generate a complete, production-ready prompt package for a **motion control** UGC video. The pipeline takes a reference video's start frame (the motion template), an AI model, and a product — and produces a detailed start frame image prompt plus a concise video prompt. Because motion control uses a reference video, the motion is **transferred** from the reference — the video prompt stays short and simple.

> **CRITICAL RULE**: If `@startframe` is provided, **analyse it first** to understand the scene, composition, body proportions, pose, camera angle, lighting and mood. The generated start frame image must match the reference composition — only the face/body identity (`@model`) and the product (`@product`) change. If `@startframe` is NOT provided, skip Stage 1 analysis and write the image prompt based on the niche best practices and product type.

---

## Format Overview
```
MOTION CONTROL VIDEO
├── Reference video             (user provides — drives motion)
├── @startframe                 (optional — extract from reference video; you analyse this)
│
├── Output 1: Start Frame Image Prompt
│   Detailed prompt matching reference composition
│   + user's @model face/body + @product
│   Markers used: @model @product [@startframe — only if provided]
│
└── Output 2: Video Prompt (concise)
    Short motion description — reference carries the motion
    No markers
```

- **1 start frame analysis** (scene, composition, pose, lighting, mood) — only if `@startframe` was provided
- **1 detailed image prompt** for the new start frame (matching reference, with user's model + product)
- **1 concise video prompt** (motion control — short because reference drives motion)
- **3 engaging text overlay options** (story-style, EN UK, emojis, TikTok compliant)
- **Product info**: compact title (format: "[item] here xx") + description (max 40 chars) + 3 hashtags

> **The formula**: reference motion + user's model identity + user's product + detailed scene recreation + engaging emoji text overlay. The output looks like a real creator genuinely reacting to or showing off the product.

---

## Required Inputs
Before generating, confirm you have:

1. **`@model`** — AI model image. The face, skin, hair and body type of the person who will appear in the generated video. **REQUIRED.**
2. **`@product`** — Product photo (clothing, makeup, skincare, accessories, etc.). **REQUIRED.**
3. **`@startframe`** — (OPTIONAL) First frame extracted from the reference/model video. When provided, it is the motion template's opening composition that you **must analyse**. When NOT provided, skip Stage 1 and proceed directly to Stage 2 using niche best practices.
4. **Product name + type + niche + key selling point** — Example: "TIA Push Up Jeans — fashion — lifts and shapes", or "Glow Serum — skincare — 7-day radiance". **REQUIRED.**
5. **Size (clothing only)** — ONLY required for clothing/apparel. Example: "Size 10", "M". Used in title. For non-clothing products (makeup, skincare, etc.) size is NOT needed — title uses friend-recommend format instead.

If any required input is missing, ask the user to provide it before proceeding.

---

## Workflow
```
Stage 1: Start Frame Analysis (ONLY if @startframe was provided)
        → Scene, composition, body/pose, lighting, mood, niche
        → SKIP this stage if @startframe was NOT provided

Stage 2: Start Frame Image Prompt (detailed, with markers)
        → Recreate reference composition (or niche best-practice if no @startframe)
        → Markers: @model @product [@startframe — include on first line ONLY if provided]

Stage 3: Video Prompt (CONCISE — motion from reference)
        → 2-4 short lines only — fashion-specific motion language
        → No markers

Stage 4: Text Overlay (3 engaging options with emojis)
        → Story-style, EN UK, TikTok compliant

Stage 5: Product Info
        → Title "[item] here xx" + description (40 chars) + 3 hashtags
```

---

## Stage 1 — Start Frame Analysis (only when @startframe is provided)
Analyse `@startframe` carefully. Extract every detail you can see. This is the foundation for the image prompt.

### Analysis Checklist
| Analysis Point | What to Extract from `@startframe` |
|----------------|----------------------------------------|
| **Niche** | Fashion / beauty / skincare / makeup / accessories / lifestyle |
| **Shot type** | Full-body / three-quarter / waist-up / face close-up / hand close-up |
| **Camera angle** | Straight-on / slight up / slight down / mirror selfie (phone visible) |
| **Camera height** | Waist / chest / face / above / below |
| **Body proportions in frame** | Face % / body fill % / product placement |
| **Pose / body language** | Standing / sitting / leaning / holding product / applying product |
| **Hands** | Free / holding phone / holding product / applying product to face |
| **Accentuated body parts** | Hips / waist / lips / eyes / jawline / cheeks — what the shot highlights |
| **Facial expression** | Happy / surprised / neutral reaction / seductive smile / excited |
| **Environment** | Bedroom / bathroom / hallway / kitchen / studio — NAMED OBJECTS visible |
| **Lighting** | Natural window / ring light / warm bedroom / cold bathroom — direction + temperature |
| **Colour palette** | Dominant colours + accent colours in the scene |
| **Mood** | Intimate / playful / confident / chaotic / calm |
| **Aspect ratio** | 9:16 vertical (TikTok) — assumed default |

### Output Format
```
### Start Frame Analysis

- **Niche**: [detected]
- **Shot type**: [full-body / waist-up / close-up / etc.]
- **Camera angle**: [straight-on / mirror selfie with phone / etc.]
- **Camera height**: [waist / chest / face height]
- **Body proportions**: [face ~X%, body ~Y%, product ~Z%]
- **Pose**: [detailed description of body position]
- **Hands**: [holding phone / holding product / applying / free]
- **Accentuated body**: [hips / lips / jaw / cheeks — what is highlighted]
- **Expression**: [happy / surprised / seductive / excited]
- **Environment**: [room type + 3-4 NAMED background objects]
- **Lighting**: [source + direction + colour temperature]
- **Colour palette**: [main + accent]
- **Mood**: [intimate / playful / confident / etc.]
```

---

## Stage 2 — Start Frame Image Prompt

Generate **1 ultra-realistic image prompt** that recreates the reference composition from Stage 1 — but with the user's `@model` face/body and `@product` as the hero product. If `@startframe` was NOT provided, write the image prompt using fashion/niche best practices for the given product type.

> **CRITICAL**: The prompt must match the reference composition closely (shot type, camera angle, pose, lighting, environment) — only the identity and product change. The reference supplies the visual blueprint.

### Mandatory First Line — Markers
```
@model @product
```
OR if `@startframe` was explicitly provided:
```
@model @product @startframe
```

- `@model` — ALWAYS present (person's face, skin, hair, body type)
- `@product` — ALWAYS present (exact product colour, texture, details)
- `@startframe` — Include on first line ONLY when the user provided it in the input. If they did NOT provide a start frame, do NOT include `@startframe`.

### Fashion-Specific UGC Image Prompt — Full-Body Clothing Showcase

For fashion/clothing products (jeans, leggings, dresses, skirts, tops, jackets), the image prompt must follow the **ultra-realistic full-body UGC fashion formula** below. This is distinct from beauty/skincare (face-focused) shots.

#### Fashion Image Prompt Key Layers

```
1. SHOT TYPE        → Ultra-realistic full-body vertical smartphone rear-camera shot (someone ELSE filming — NOT selfie, NOT mirror)
2. CAMERA ANGLE     → [straight-on / slight upward angle / waist-height] — rear camera, no phone visible in frame
3. BODY PROPORTION  → model fills ~85-95% of 9:16 vertical frame height; face ~20-30%; CLOTHING IS THE HERO
4. EXPRESSION       → [confident pouty / lips slightly pursed / subtle knowing look] — direct eye contact with camera lens, NOT big smile
                       MANDATORY: model looks DIRECTLY at camera. Expression is confident and self-assured, NOT catalogue-happy.
                       Think "I know I look good" energy, slight head tilt, eyebrows may be gently raised.
5. CLOTHING HERO    → [exact garment fit description: how it hugs hips, cinches waist, drapes, sits on leg; fabric texture; specific colour + finish]
6. BODY MOVEMENT    → [weight shift / hip pop / stride / one leg forward / natural S-curve pose]
7. ACCENTUATED BODY → [hips / waist-to-hip ratio / glutes / legs / silhouette — what the garment highlights]
8. STYLING PROPS    → [shoulder bag (chain strap / leather — ALWAYS present), sunglasses on head, delicate jewellery, bracelet]
                       A shoulder bag is a key UGC styling anchor — include it in every clothing prompt.
9. ENVIRONMENT      → [fitting room with tiled/textured walls + mirror / apartment hallway with neutral walls + wood floor
                       / minimal bedroom — 2-3 NAMED objects] softly blurred bokeh
10. LIGHTING        → [bright overhead (fitting room) / natural daylight from doorway (apartment) — warm neutral 5000-5500K]
11. SKIN + FABRIC   → visible skin texture, fabric weave/grain/sheen, natural creases at joints — no filter
12. FINAL MOOD      → confident / self-assured / UGC-authentic — NOT catalogue, NOT studio, NOT overly happy
```

#### Fashion UGC Image Prompt Gold Standard

```
@model @product

"Ultra-realistic full-body vertical smartphone photo shot by someone else (rear camera), 9:16 vertical frame.

Camera positioned at waist-to-chest height, straight-on or with a subtle upward tilt — the model fills ~90% of the frame height, face occupying ~25% at the top of frame, full legs and feet visible at the bottom. No phone visible in frame — someone else is filming her.

[SUBJECT — from @model: e.g., 'confident young woman, mid-20s, hair pulled up in a messy bun with loose strands framing face, warm skin tone, natural complexion'] with a [expression: MUST be 'confident pouty look — lips slightly pursed, direct unwavering eye contact with camera lens, subtle head tilt, eyebrows gently raised — self-assured "I know I look good" energy, NOT smiling big'].

MODEL MUST LOOK DIRECTLY AT CAMERA — this is non-negotiable for UGC authenticity.

Wearing [EXACT from @product: e.g., 'high-waisted grey-wash flare jeans with visible topstitching at pockets, double-button waistband detail, fabric hugging hips and thighs then flaring from knee, slight natural creasing at knees']. Paired with [complementary top: e.g., 'fitted white crop top / ribbed white tank top showing 3 cm of midriff']. Styling anchor: [shoulder bag — e.g., 'quilted silver chain-strap shoulder bag on right shoulder' OR 'small black leather bag with tan strap']. Additional: [sunglasses pushed up on head, delicate gold necklace, small hoop earrings, bracelet].

[POSE: e.g., 'standing with weight shifted to one hip, one hand resting on belt loop, other arm relaxed at side — natural confident stance, slight S-curve in body line, one knee slightly bent'].

[ENVIRONMENT — pick one:
  • Fitting room: 'Bright fitting room — textured cream mosaic tile walls, wooden door frame, warm overhead lighting, glass shelf/counter edge visible'
  • Apartment hallway: 'Bright minimalist apartment hallway — cream/sage walls, dark wood laminate flooring, white doorway with window visible in background, wall power outlet'
  • Apartment corner: 'Clean apartment corner — plain white walls, wooden floor, minimal objects — blue bag on floor, wall-mounted power outlet'
— softly blurred bokeh, lived-in and personal, NOT a studio].

[LIGHTING: 'Bright warm overhead light (fitting room) OR bright natural daylight from window/doorway in background, 5000-5500K, even body illumination with gentle directional shadows defining body curves — true-colour fabric rendering'].

Fabric texture clearly visible — denim weave/knit texture, natural creasing at joints, waistband hardware (buttons/zip) with metallic sheen. Realistic skin: visible pores, stray hairs at hairline, subtle natural skin shine — no filter, no retouching.

Mood: confident, self-assured, UGC-authentic — feels like a real girl showing off a new outfit on TikTok, natural ease.

Negative: CGI, cartoon, airbrushed skin, plastic texture, plastic fabric, stiff fabric, big smile, catalogue smile, text, watermark, extra fingers, mannequin pose, catalogue shot, studio backdrop, fashion editorial, overly posed, DSLR, face distortion, identity drift, phone visible in hand, mirror selfie, ring light reflection."
```

### 11-Layer Detailed Prompt Structure (Universal — all niches)
Write as **one flowing paragraph** — all layers woven into a detailed natural-reading brief. **Be specific and detailed** — scene description, proportions, accentuated body parts, pose, lighting.

```
### Start Frame — Image Prompt

@model @product [@startframe — include ONLY if provided by user]

"Ultra-realistic [shot type from analysis — full-body mirror selfie /
waist-up / three-quarter / close-up] smartphone photo, 9:16 vertical.

[CAMERA — exactly as seen in reference: e.g., 'phone held at chest
height angled slightly downward, mirror reflecting full body head to
toe, iPhone visible in hand' OR 'selfie arm extended, phone at face
height, slight downward tilt' OR 'tripod-level straight-on, waist
height, no phone visible'].

[PROPORTIONS — match reference exactly: 'model fills ~85% of frame
height, face ~25%, [accentuated body part e.g. hips / waist / lips]
occupies the visual centre'].

[SUBJECT + EXPRESSION — confident pouty look / lips slightly pursed /
subtle knowing half-smile / direct unwavering eye contact with camera,
eyebrows gently raised, head tilted slightly — self-assured energy.
MANDATORY: model looks DIRECTLY at camera. NOT a big happy smile —
think confident "I know I look good" TikTok energy. Never flat or
catalogue-style, never exaggerated happiness]

[ACCENTUATED BODY DESCRIPTION — for fashion: 'high-waisted leggings hug
hips, accentuating waist-to-hip ratio, cinched at natural waist, glutes
rounded and defined'; for beauty: 'full lips catching highlight, defined
cheekbones, glowing skin'; for skincare: 'bare clean skin, dewy texture'.
Match what the reference shot is selling.]

Wearing/using [EXACT description from @product: garment type + fit +
colour + material + construction details] OR [makeup product details:
colour, finish, application style] OR [skincare product: colour,
bottle, application].

[POSE — match reference exactly: standing with weight on one leg, hand
on hip, other hand holding phone / leaning forward slightly / one hand
applying product to cheek / arm across waist highlighting silhouette]

[ENVIRONMENT — match reference: named room type + 3-4 specific named
objects visible — e.g., 'bright bedroom with full-length wardrobe
mirror, unmade linen bed, wooden clothing rack with hangers, white
trainers by door' OR 'bright bathroom with marble counter, round vanity
mirror, ceramic toothbrush holder, folded white towel, small plant' —
softly blurred bokeh, lived-in personal space].

Sharp focus on model and product simultaneously, [texture keywords:
fabric weave / skin pores / lip gloss sheen / powder texture / serum
drops] clearly visible. Visible skin pores, stray hairs at hairline,
natural texture — no filter.

[LIGHTING — match reference: 'bright natural window light from camera-
right, 5500K daylight, true-colour rendering, gentle shadows' OR
'warm bedroom bedside lamp plus cool window fill, 3800K + 5500K mix'
OR 'ring light frontal fill, soft shadows, 4800K']. 

Mood: [intimate / playful / confident / excited — match reference
mood].

Negative: CGI, cartoon, airbrushed skin, plastic texture, plastic
fabric, stiff fabric, text, watermark, extra fingers, mannequin pose,
catalogue shot, studio backdrop, fashion editorial, overly posed,
DSLR, face distortion, identity drift."
```

### Character + Product Consistency Rules
- **`@model`** on first line — same face, skin, hair, body type across all renders
- **`@product`** on first line — same product with exact colour, texture, details
- **`@startframe`** on first line — ONLY include if user explicitly provided a start frame image
- Product must match reference placement (held / worn / applied)
- Composition must match reference (shot type, angle, proportions)
- Environment details should echo the reference scene

---

## Stage 3 — Video Prompt (8-Second UGC Choreography)

Generate **1 video prompt** optimised for the user's chosen AI video platform (**Veo 3.1** or **Kling 3.0**). The video must be **8 seconds** long and follow the **body-first hook choreography** pattern extracted from real UGC TikTok reference videos.

> **NO MARKERS**: The video prompt does NOT use `@model`, `@product`, `@startframe`, or any markers. Write directly.

> **CRITICAL — MODEL MUST LOOK AT CAMERA**: Throughout the video, whenever the model's face is visible, she MUST look directly at the camera. This is the single most important rule for UGC authenticity.

### The Body-First Hook Choreography (8 Seconds)

Every fashion UGC video follows this proven 5-phase choreography pattern. This is the motion blueprint — adapt timing to the user's chosen platform format:

```
Phase 1 — HOOK (0-2s):     Body-only close-up at waist level. Face is NOT visible.
                            Camera shows clothing fit: waistband, fabric texture, belt/buttons.
                            Subtle micro-movement only (breathing, slight weight shift).
                            → This forces the viewer to stop scrolling: "whose body is this?"

Phase 2 — REVEAL (2-4s):   Camera tilts up OR model walks toward camera → FACE REVEAL.
                            Model's face appears — direct eye contact with camera,
                            confident pouty expression (lips slightly pursed, not big smile).
                            She may touch/adjust her clothing or waistband.
                            → Identity is established. Viewer is now hooked.

Phase 3 — SHOWCASE (4-6s):  Weight shift to one hip, hand on hip or belt loop.
                            Body rotates slowly showing garment from different angle.
                            Slow deliberate movement — body owns the space.
                            Clothing moves naturally with the body.
                            → Garment silhouette and fit are fully revealed.

Phase 4 — TURN (6-7s):     Slow 3/4 or full turn to show back/side of clothing.
                            Over-shoulder look back at camera during the turn.
                            Hair may sway, fabric moves with the rotation.
                            → Rear/side view of the outfit.

Phase 5 — FINALE (7-8s):   Returns to front-facing position OR holds the turned pose.
                            Final direct eye contact with camera.
                            Confident settled stance — hand on hip.
                            → Clean ending, model owns the frame.
```

### Rules for Video Prompts (All Platforms)
1. **Duration: 8 seconds** — always specify this explicitly
2. **Body-first hook is MANDATORY** — always start with body/clothing close-up, no face
3. **Model looks at camera** — whenever face is visible, direct eye contact with lens
4. **Confident pouty expression** — NOT a big smile, NOT neutral. Lips slightly pursed, self-assured
5. **Someone else is filming** — rear camera, no phone visible, no mirror, no selfie arm
6. **Shoulder bag always present** — chain strap or leather bag as styling anchor
7. **Slow deliberate movement** — no rushed or jerky motion, body owns the space
8. **Negative prompt** — covers artifacts AND unwanted expressions
9. **Ask the user**: "Optimise for Veo 3.1 or Kling 3.0?" — then use the correct format below

---

### Platform A — Veo 3.1 (Google) — Timestamp Prompting Format

Veo 3.1 uses the **5-part formula**: `[Cinematography] + [Subject] + [Action] + [Context] + [Style & Ambiance]`
and supports **timestamp prompting** for precise shot control within a single generation.

**Key Veo 3.1 Rules:**
- Max clip length: 8 seconds
- Resolution: 720p or 1080p
- Aspect ratio: 9:16
- Timestamp format: `[00:00-00:02]`, `[00:02-00:04]`, etc.
- Use cinematic camera language: dolly, tracking, crane, slow pan
- Use "ingredients to video" with reference images for character consistency
- Describe negative as excluded elements ("a scene with no text, no watermarks")
- Can specify SFX and ambient audio

#### Veo 3.1 — Fashion UGC Video Prompt Template

```
### Video Prompt — Veo 3.1 (8s, timestamp prompting)

9:16 vertical, 1080p, 8 seconds, ultra-realistic smartphone-quality footage.

[00:00-00:02] Tight close-up at waist level — only the model's torso visible
from chest to mid-thigh. Camera at waist height, straight-on. Full detail of
[EXACT clothing from start frame: e.g., 'grey-wash flare jeans — double-button
waistband, topstitching at pockets, fabric hugging hips']. White crop top hem
visible. Quilted chain-strap shoulder bag resting on hip. Subtle breathing
movement only. Face NOT visible — cropped above chest. No phone in frame.

[00:02-00:04] Camera slowly tilts upward revealing the model's face — direct
eye contact with camera lens, confident pouty expression, lips slightly pursed,
subtle head tilt. She adjusts her waistband with one hand, other arm relaxed.
Bright [environment: fitting room / apartment hallway] background softly
blurred. Natural warm overhead lighting.

[00:04-00:06] Full-body shot — model shifts weight to one hip, places hand on
hip, body creates natural S-curve. Slow deliberate weight shift showing
garment silhouette and fit. Clothing moves naturally with the body. Direct
eye contact maintained. Fabric texture visible — natural creasing, denim weave.

[00:06-00:08] Model begins slow 3/4 turn — over-shoulder look back at camera
during rotation, hair sways gently. Settles into final pose showing rear/side
view of outfit. Confident direct gaze over shoulder. Shoulder bag chain
catches the light.

Style: Ultra-realistic, raw smartphone UGC footage, natural skin texture
with visible pores, fabric moves realistically with body. Bright warm
lighting, true-colour fabric rendering, subtle film grain. Ambient: quiet
room tone, soft fabric rustle.

A scene with no text overlays, no watermarks, no catalogue lighting, no
studio backdrop. Natural skin — no airbrushing, no plastic texture. Stable
facial features, consistent identity throughout. No big smile — expression
is confident and pouty. No mirror, no phone visible.
```

#### Veo 3.1 — Gold Standard Example (Grey Flare Jeans)

```
9:16 vertical, 1080p, 8 seconds, ultra-realistic smartphone-quality footage.

[00:00-00:02] Tight close-up at waist level — only the model's torso visible
from bust to upper thigh. Camera at waist height, straight-on. Grey-wash flare
jeans with double-button waistband and visible topstitching, paired with a
fitted white ribbed tank top showing 3 cm of midriff. LV-print shoulder bag
strap crossing the torso. Subtle breathing, slight weight shift. Face NOT
visible. No phone visible.

[00:02-00:04] Slow camera tilt upward revealing model's face — early-20s woman
with hair in messy bun, loose strands framing face. Direct confident eye
contact with camera lens, lips slightly pursed in a pouty self-assured look,
subtle head tilt. She hooks one thumb into a belt loop. Bright apartment
hallway — cream walls, dark wood floor, doorway with window light in
background — softly blurred bokeh.

[00:04-00:06] Full-body vertical frame — model shifts weight to left hip
creating an S-curve, right hand on hip. Slow deliberate pose showing
jeans flare from knee, full leg length and fit visible. Hoop earrings catch
light. Direct eye contact. Denim fabric shows natural creasing at knees,
waistband hardware gleaming.

[00:06-00:08] Model turns slowly to 3/4 rear view — looks over right
shoulder at camera with confident gaze. Hair sways gently with the turn.
Jeans rear fit and flare silhouette visible. Settles into final pose.
Shoulder bag chain glints.

Style: Ultra-realistic raw UGC, visible skin pores, natural denim weave
texture, true-colour fabric rendering, bright natural daylight 5500K from
background window, subtle film grain. Ambient: quiet room, soft denim rustle.

A scene with no text, no watermarks, no studio lighting, no phone visible,
no mirror, no big smile. Natural skin, stable face, consistent identity.
```

---

### Platform B — Kling 3.0 — Multi-Shot Sequence Format

Kling 3.0 uses the **5-layer structure**: `Scene → Characters → Action → Camera → Audio & Style`
and supports **multi-shot sequences** with time codes for precise pacing.

**Key Kling 3.0 Rules:**
- Max clip length: 15 seconds (use 8s for UGC)
- Use character labels: `[Character A: descriptive name]`
- Time-coded shots: `Shot 1 (0-2 seconds):`, `Shot 2 (2-4 seconds):`, etc.
- Specific camera verbs: dolly push, tracking, crash zoom, handheld shoulder-cam
- Include micro-motions for realism: breathing, blinking, hair sway, fabric movement
- Use negative prompting: "No shake. Stable face. Outfit artifact free."
- Describe textures explicitly for credibility
- Anchor characters early with detailed descriptions

#### Kling 3.0 — Fashion UGC Video Prompt Template

```
### Video Prompt — Kling 3.0 (8s, multi-shot)

[Character A: confident young woman — EXACT description from start frame:
hair, skin, expression, clothing, accessories, shoulder bag] in a
[environment from start frame]. 9:16 vertical, 8 seconds.

Shot 1 (0-2 seconds): Tight close-up at waist level — only Character A's
torso visible from bust to mid-thigh. Camera at waist height, static.
[Exact clothing detail: garment type, buttons, stitching, fabric texture].
Shoulder bag strap visible. Subtle breathing micro-motion. Her face is
not in frame. No phone visible.

Shot 2 (2-4 seconds): Slow camera tilt upward revealing Character A's face.
Direct eye contact with camera lens, confident pouty expression — lips
slightly pursed, head tilted slightly. She touches her waistband or belt
loop casually. Bright [environment] background — softly blurred.

Shot 3 (4-6 seconds): Full-body vertical framing. Character A shifts weight
to one hip, hand on hip, creating natural S-curve. Slow deliberate movement
showing garment silhouette. Direct eye contact. Fabric moves naturally,
natural creasing visible.

Shot 4 (6-8 seconds): Character A turns slowly to 3/4 rear view — looks
over shoulder at camera with confident gaze. Hair sways with the turn.
Rear garment fit visible. Settles into final pose.

Ultra-realistic skin texture with visible pores, natural denim/fabric weave,
true-colour garment rendering, bright warm lighting. Subtle film grain.
Micro-motions: breathing, blinking, slight hair sway, fabric movement.

No shake. Stable face. Outfit artifact free. No morphing textures. No text
on screen. Consistent identity throughout.

Negative: blur, flicker, distorted face, warped limbs, morphing, deformed
hands, extra fingers, big smile, catalogue expression, plastic skin, plastic
fabric, stiff fabric, text, captions, phone visible, mirror, identity drift.
```

#### Kling 3.0 — Gold Standard Example (Taupe Mini Dress)

```
[Character A: confident young woman, mid-20s, half-up half-down wavy blonde
hair, warm tan skin, wearing a structured taupe/brown sleeveless mini dress
with padded shoulders and high crew neckline, quilted chain-strap shoulder
bag, gold bracelet, small hoop earrings, black ankle boots] in a minimalist
apartment corner. 9:16 vertical, 8 seconds.

Shot 1 (0-2 seconds): Tight close-up at chest-to-thigh level — only
Character A's torso visible. Camera at waist height, static. Structured
taupe dress fabric visible — clean seam lines, padded shoulder edge, hem
hitting mid-thigh. Phone held casually in right hand at hip level. Face
not visible. Subtle breathing. White wall and wooden floor in soft bokeh.

Shot 2 (2-4 seconds): Slow camera tilt upward revealing Character A's
face. Direct eye contact with camera — confident pouty look, lips pursed
slightly, one eyebrow barely raised. She shifts the bag on her shoulder.
Clean white wall behind, minimal apartment corner.

Shot 3 (4-6 seconds): Full-body vertical — Character A steps slightly
forward, weight on left hip, right hand with phone at side. Shows full
dress silhouette — padded shoulders, A-line hem, legs, ankle boots. She
looks directly at camera with self-assured expression. Subtle head tilt.

Shot 4 (6-8 seconds): Quick confident spin — dress hem lifts slightly with
the turn, hair catches the light. Settles into final pose — hand on hip,
direct eye contact, slight knowing half-smile. Shoulder bag chain glints.

Ultra-realistic skin texture, visible dress fabric structure and subtle
sheen, true-colour taupe rendering, bright warm natural light, film grain.
Micro-motions: breathing, blinking, hair settling after turn, dress fabric
settling.

No shake. Stable face. Outfit artifact free. No morphing textures.

Negative: blur, flicker, distorted face, warped limbs, morphing, extra
fingers, catalogue smile, plastic skin, stiff fabric, text, mirror,
identity drift.
```

---

### Motion Control Mode (When Reference Video Drives Motion)

When a reference video is provided for motion transfer, the video prompt stays **concise** (2-4 lines) because the reference handles the motion. But still include the expression and camera-look rules:

```
### Video Prompt — Motion Control (concise, 8s)

[Shot type matching start frame], 9:16 vertical, 8 seconds, 24fps.

Subject: [short confident description — woman in [environment], wearing
EXACT product from start frame + styling props]. Direct eye contact with
camera whenever face is visible. Confident pouty expression — NOT smiling.
Natural slow deliberate movement — weight shifts, hip sway, clothing moves
with the body.

Ultra-realistic skin texture, visible fabric weave and texture detail,
true-colour rendering, bright natural lighting, subtle film grain.

Keep identity, clothing, hair, shoulder bag and accessories exactly as in
start frame. No text on screen, stable geometry, no flicker.

Negative: cartoon, 3D render, plastic skin, plastic fabric, stiff fabric,
mannequin motion, big smile, catalogue expression, text, captions, extra
fingers, face distortion, identity drift, mirror, phone visible.
```

### Example — Beauty (Lip Gloss)
```
Face close-up, 9:16 vertical, 8 seconds, 24fps.

Subject: woman in her bright bathroom, applying a glossy nude pink
lip tint with a doe-foot applicator. Eyes looking directly at camera.

Ultra-realistic skin pores, visible lip texture, glossy sheen
catching light, soft ring-light frontal fill, subtle film grain.

Keep identity, product, hair and accessories exactly as in start
frame. No text on screen, stable geometry, no flicker.

Negative: cartoon, 3D render, plastic skin, waxy lips, text,
captions, extra fingers, face distortion, identity drift.
```

---

## Stage 4 — Text Overlay Options

Text is added by the user in post-production. Generate **3 engaging variations** — story-style with emojis, inspired by the reference style ("I saw a girl saying these jeans will literally lift your bum and push it into shape... she was NOT lying. 😭💗🥹").

### Style Rules
- **Story-style and engaging** — short story hook, personal reaction, or bold discovery
- **Emojis ARE used** — 1-3 emojis at end of sentence or natural places (😭 💗 🥹 😮 ✨ 💕 🤌 🔥 👀 🥹)
- **EN UK language mandatory** — "colour" not "color", "bum" not "butt", "favourite" not "favorite"
- **Can be longer than 10 words** if story-style — but ideally 10-25 words
- **Conversational** — like talking to a best friend on TikTok
- **First-person or friend-reporting tone** — "I saw..." / "I genuinely..." / "Nobody told me..."
- **No ALL CAPS** except for emphasis words (e.g., "NOT lying", "LITERALLY")

### TikTok Shop Content Compliance — MANDATORY
**BANNED words/phrases (NEVER use):**
- "Cheapest" / "lowest price" / superlative pricing
- "Cure" / "treat" / "heal" / any medical claim
- "Lose weight" / "slim" / body-shaming language
- "Instant results" / "guaranteed" / absolute claims
- "RUN" / "HURRY" / fake urgency
- "Before and after" transformation comparisons
- "#1" / "best ever" / unverifiable superlatives
- Competitor names or disparagement

**ALLOWED engaging triggers:**
- **Story hook**: "I saw a girl saying..." / "Someone told me..."
- **Personal reaction**: "She was NOT lying" / "I genuinely can't..."
- **Discovery**: "Didn't know [item] could [benefit]"
- **Surprise**: "Nobody told me..." / "The way these..."
- **Social proof**: "Everyone's asking" / "Going viral"
- **Emotion**: "I'm obsessed" / "Genuinely unreal"
- **Soft scarcity**: "Whilst the sale's still on"

### Text Overlay Patterns (pick 3 and adapt)
| Pattern | Template | Example |
|---------|----------|---------| 
| **Story hook + reaction** | "I saw a girl saying [benefit]... she was NOT lying. 😭💗" | "I saw a girl saying these jeans will lift your bum... she was NOT lying 😭💗🥹" |
| **Personal obsession** | "Genuinely can't believe how [benefit] these [item] are ✨" | "Genuinely can't believe how comfy these jeans are ✨🥹" |
| **Surprise discovery** | "Nobody told me [item] could do THIS 👀" | "Nobody told me a lip tint could last this long 👀💗" |
| **Bold claim + emoji** | "These [item] are about to change your life 🤌" | "This serum is about to change your skin 🤌✨" |
| **Soft scarcity** | "Catching these whilst the sale's still on 💕" | "Catching these jeans whilst the sale's still on 💕" |
| **Side-by-side feel** | "The way these [item] [benefit] 😮" | "The way these jeans fit everywhere 😮💗" |
| **Friend recommend** | "Running, not walking, to get these [item] 🥹" | "Running not walking to get this gloss 🥹💕" |

### Output Format — COPY-READY
```
### Text Overlay Options — COPY-READY (EN UK + Emojis)

━━━ Option 1 — [Pattern name] ━━━

[story-style text with emojis — 10-25 words]

━━━ Option 2 — [Pattern name] ━━━

[story-style text with emojis — 10-25 words]

━━━ Option 3 — [Pattern name] ━━━

[story-style text with emojis — 10-25 words]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

> TikTok Shop compliant — no superlatives, no body-shaming,
> no fake urgency, no absolute claims, no medical claims.
```

---

## Stage 5 — Product Info

### Title — Format Depends on Niche
The title format **depends on whether the product is clothing or not**. Pick the right path:

---

#### Path A — Clothing / Apparel: `[item] here [size or xx]`

Based on the reference format "Jeans here xx" — compact, always includes size or kiss suffix.

**Pattern**: `[garment type] here [size/xx]`

Where the suffix is:
- A size — `10`, `12`, `S`, `M`, `L`, `XL`
- `xx` (kisses — reference default, if size not used)

**Rules**:
- Max 30 characters (ideally 10-20 characters)
- Lowercase, EN UK
- **Always include size** when the garment has sizing
- No exclamation marks

**Examples (clothing)**:
- `jeans here 10` (13 chars)
- `dress here S` (12 chars)
- `jacket here M` (13 chars)
- `skirt here 12` (13 chars)
- `jeans here xx` (13 chars — if size skipped)

---

#### Path B — Non-Clothing (Makeup, Skincare, Accessories, Lifestyle, etc.): `my best [item] …`

Friend-to-friend recommendation tone — as if a girl is telling her mate about something great she found. **No size needed** — size isn't relevant for these products.

**Patterns**:
- `my best [item] …` (classic friend-recommend)
- `the [item] everyone needs`
- `my fave [item] rn`
- `[item] that actually works`
- `finally found the one ✨`

**Rules**:
- Max 30 characters (count precisely)
- Lowercase, EN UK
- Friend-to-friend casual tone — genuine, not salesy
- `…` (ellipsis) or soft emoji allowed at end
- No size, no exclamation marks

**Examples (non-clothing)**:
- `my best lip gloss ever …` (24 chars)
- `my fave blush rn ✨` (18 chars)
- `the serum everyone needs` (24 chars)
- `my best skincare find` (21 chars)
- `my best perfume ever …` (22 chars)
- `the mascara that works` (22 chars)
- `finally found my shade 🥹` (24 chars)
- `my fave highlight rn` (20 chars)

### Description (max 40 characters)
One short sentence describing the key benefit or personal experience. Light emoji at end allowed.

**Rules**:
- Max 40 characters (count precisely, INCLUDING any emoji)
- EN UK language
- Personal / conversational
- 0-1 emoji (optional)

**Examples**:
- `so comfy I forgot I was wearing them` (37 chars)
- `the fit is genuinely insane ✨` (29 chars)
- `7 days and my skin's a mirror 💗` (31 chars)
- `lasts through dinner, drinks + more` (36 chars)
- `finally found my shade 🥹` (24 chars)

### 3 Hashtags for TikTok Ranking
**Formula**: #[product type] + #[niche/quality keyword] + #[broad reach]

**Rules**:
- Exactly 3 hashtags
- EN UK
- Lowercase only
- First = specific product type (#jeans, #lipgloss, #serum, #blush)
- Second = niche or quality (#fashion, #makeup, #skincare, #flattering, #glowup)
- Third = broad reach (#fyp, #trending, #tiktokshop)

**Examples by niche**:
- Jeans: `#jeans #flattering #fyp`
- Dress: `#dress #datenight #fyp`
- Lip gloss: `#lipgloss #makeup #fyp`
- Serum: `#serum #skincare #glowup`
- Blush: `#blush #makeuptips #trending`
- Perfume: `#perfume #fragrance #fyp`

### Output Format — COPY-READY
```
### Product Info — COPY-READY

━━━ Title (≤30 chars) ━━━

[clothing: "[item] here [size/xx]"  |  non-clothing: "my best [item] …"] — [X chars]

━━━ Description (≤40 chars) ━━━

[personal experience with optional emoji] — [X chars]

━━━ Hashtags ━━━

#[product] #[niche/quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Full Output Template

Deliver all outputs in this order:

```
# UGC Motion Control — {Product Name}

## 1. Start Frame Analysis
*(Only output this section if @startframe was provided by the user)*

- Niche: [detected]
- Shot type: [full-body / close-up / etc.]
- Camera angle: [mirror selfie with phone / straight-on / etc.]
- Camera height: [waist / chest / face]
- Body proportions: [face ~X%, body ~Y%, product ~Z%]
- Pose: [detailed description]
- Hands: [holding phone / product / free]
- Accentuated body: [hips / lips / jaw — what shot highlights]
- Expression: [detected emotion]
- Environment: [room type + named objects]
- Lighting: [source + direction + temperature]
- Colour palette: [main + accent]
- Mood: [detected mood]

---

## 2. Start Frame — Image Prompt

@model @product [@startframe — include ONLY if provided by user]

"[Detailed full prompt — 11 layers, single paragraph, matching
reference composition, proportions, accentuated body, pose,
lighting, mood, environment. For fashion: full-body, clothing hero,
body silhouette emphasis. iPhone/mirror selfie allowed if
reference shows it.]"

---

## 3. Video Prompt — Motion Control (concise)

[2-4 short lines only — shot type + subject + texture/lighting +
constraints + negative. NO MARKERS. Fashion: include body-confident
movement language + fabric realism keywords.]

---

## 4. Text Overlay Options — COPY-READY (EN UK + Emojis)

━━━ Option 1 — [Pattern] ━━━

[story-style text with emojis — 10-25 words]

━━━ Option 2 — [Pattern] ━━━

[story-style text with emojis — 10-25 words]

━━━ Option 3 — [Pattern] ━━━

[story-style text with emojis — 10-25 words]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## 5. Product Info — COPY-READY

━━━ Title (≤30 chars) ━━━

[clothing: "[item] here [size/xx]"  |  non-clothing: "my best [item] …"] — [X chars]

━━━ Description (≤40 chars) ━━━

[personal experience with optional emoji] — [X chars]

━━━ Hashtags ━━━

#[product] #[niche/quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Technical Specs
- **Format**: Vertical 9:16
- **Video duration**: 8 seconds (NOT 12s — optimised for AI generation)
- **Pipeline**: Motion Control (reference video drives motion) OR Direct Generation (Veo 3.1 / Kling 3.0)
- **Image generation**: 1 detailed start frame prompt (with markers)
- **Video generation**: 1 platform-optimised video prompt (no markers)
  - **Veo 3.1**: Timestamp prompting format (`[00:00-00:02]` etc.)
  - **Kling 3.0**: Multi-shot sequence format (`Shot 1 (0-2 seconds):` etc.)
- **Hook pattern**: Body-first / face-second reveal (MANDATORY for fashion)
- **Expression**: Confident pouty — direct eye contact — NOT big smile
- **Camera**: Rear camera (someone else filming) — no selfie, no mirror
- **Styling**: Shoulder bag ALWAYS present as styling anchor
- **Niche**: Any (fashion, beauty, skincare, makeup, accessories, lifestyle)
- **Text overlay**: Added in post-production by user (CapCut/TikTok)
- **Music**: Added on platform by user
- **Language**: English UK (all text content)
```

---

## Quality Standards
| # | Criteria | Pass | Fail |
|---|----------|------|------|
| 1 | Start frame analysis present (when @startframe provided) | All 13 analysis points filled from `@startframe` | Missing analysis when @startframe was given |
| 2 | Start frame analysis skipped when NOT provided | Section omitted cleanly | Generated analysis from thin air |
| 3 | Niche correctly detected | Fashion / beauty / skincare / makeup / accessories / lifestyle | Wrong niche or generic "product" |
| 4 | Shot type matches reference (or niche best-practice) | Full-body/close-up/etc. matches reference or niche | Drift from reference shot type |
| 5 | Camera angle matches reference | Phone position, height, angle match reference | Drift from reference angle |
| 6 | Body proportions match reference | Face %, body %, product placement match reference | Wrong proportions |
| 7 | Accentuated body part specified | Hips/waist/lips/etc. — what the shot sells is called out | Not specified what shot highlights |
| 8 | Pose matches reference | Detailed body position matching reference | Generic pose |
| 9 | Expression matches reference mood | Happy/surprised/excited — matching reference energy | Flat or mismatched |
| 10 | Environment matches reference | Same room type + 3+ named objects matching reference | Generic or wrong room |
| 11 | Lighting matches reference | Source + direction + temperature matching reference | Generic lighting |
| 12 | `@model` + `@product` markers | Both on first line of image prompt ONLY | Missing from image OR present in video prompt |
| 13 | `@startframe` marker | On first line ONLY when user provided a start frame — omitted otherwise | Present when not provided OR missing when provided |
| 14 | Image prompt detailed | 11 layers, single paragraph, detailed scenery + proportions + body + pose | Shallow or missing layers |
| 15 | Fashion image prompt: clothing is hero | Garment fit, fabric texture, body silhouette explicitly described | Generic clothing description |
| 16 | Video prompt CONCISE | 2-4 short lines only — motion not over-specified | Long motion description (that belongs to the reference) |
| 17 | Video prompt no markers | Direct description, no @model, @product, or @startframe | Markers in video prompt |
| 18 | Video prompt: fashion keywords | Fabric movement, body-confident motion, texture realism keywords present | Generic video prompt |
| 19 | Identity preservation constraint | "Keep identity, clothing/product" in video prompt | Missing constraint |
| 20 | Negative prompt complete | Cartoon, plastic skin, plastic fabric, text, face distortion, identity drift | Missing key negatives |
| 21 | Text overlay story-style | Engaging hook, reaction, story feel | Dry statement without hook |
| 22 | Text overlay emojis | 1-3 emojis naturally placed | No emojis OR emoji spam (5+) |
| 23 | Text overlay EN UK | UK spelling + casual British register | US English or mixed |
| 24 | Text overlay word count | 10-25 words per option | <8 words (too short) or >30 words (too long) |
| 25 | TikTok compliance | No banned words, no fake urgency, no absolute claims | Any banned phrase |
| 26 | Title format correct for niche | Clothing: `[item] here [size/xx]` (includes size). Non-clothing: `my best [item] …` friend-recommend tone. ≤30 chars | Wrong path for niche, missing size on clothing, or salesy/over 30 chars |
| 27 | Title lowercase EN UK | All lowercase (except brand), EN UK spelling | Caps or US English |
| 28 | Description character count | ≤40 chars including emoji, personal tone | Over 40 chars or product spec language |
| 29 | Hashtag count + format | Exactly 3 lowercase EN UK hashtags: #product #niche #reach | Wrong count, caps, or irrelevant |
| 30 | iPhone/mirror selfie allowed | Permitted in start frame if reference shows it | N/A |
| 31 | Any niche supported | Fashion / beauty / skincare / etc. all supported | Fashion-only thinking |
| 32 | Reference composition fidelity | Image prompt recreates reference scene composition faithfully | Creative drift from reference |

---

## References
- `ultra-realitic-images-prompt.md` (project root) — Ultra-realistic image prompt methodology
- Reference TikTok analysis — `img-1.png` (story-style emoji text overlay), `img-2.png` (compact title format "Jeans here xx"), `img-3.png` (engaging emoji descriptions)
- Reference video prompt style — `Captura de tela 2026-04-12 155009.png` — UGC fashion leggings motion control reference (rear reveal, hip shift, leg extension, sensual pacing, TikTok 4K aesthetic)
- **UGC Video Analysis** (3 TikTok reference videos analysed April 2026):
  - `snaptik_7626349235675385110_v3.mp4` — Grey jeans + white crop top, fitting room, body-first hook → face reveal → rear turn → spin
  - `snaptik_7624554840798121238_v3.mp4` — Grey flare jeans + white tank, apartment hallway, walk-toward-camera → turn → over-shoulder look
  - `snaptik_7626836669957737750_v3.mp4` — Taupe mini dress, apartment corner, body close-up → reveal → spin with hair motion → hand-on-hip pose
  - **Key findings**: Body-first/face-second hook; confident pouty expression (NOT big smile); slow deliberate movement; direct camera eye contact; shoulder bag styling anchor; minimalist environments (fitting room / apartment — NOT bedroom mirror)
- **Veo 3.1 Prompting Guide** — https://cloud.google.com/blog/products/ai-machine-learning/ultimate-prompting-guide-for-veo-3-1
  - 5-part formula: Cinematography + Subject + Action + Context + Style & Ambiance
  - Timestamp prompting: `[00:00-00:02]` precise shot control
  - Max 8 seconds, 9:16, 1080p, SFX/ambient audio support
- **Kling 3.0 Prompting Guide** — https://www.atlabs.ai/blog/kling-3-0-prompting-guide-master-ai-video-generation
  - 5-layer structure: Scene → Characters → Action → Camera → Audio & Style
  - Multi-shot time-coded sequences: `Shot 1 (0-2 seconds):`
  - Character labels: `[Character A: description]`
  - Micro-motions for realism: breathing, blinking, hair sway, fabric movement
  - Negative prompting: "No shake. Stable face. Outfit artifact free."
- Motion control concept — reference video supplies motion; start frame + concise prompt supply identity + product
- TikTok Shop content compliance — Banned/allowed words for text overlays
- **Markers**: `@model` (person identity), `@product` (product image), `@startframe` (optional reference frame — include ONLY when user provides it)
