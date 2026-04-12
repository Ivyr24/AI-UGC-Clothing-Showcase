---
name: ugc-motion-control
description: "Generate UGC motion control videos for any niche (fashion, beauty/makeup, skincare, accessories, lifestyle, etc.). Input: @start_frame_ref (start frame extracted from a reference/model video whose motion will be transferred), @influencer (AI influencer image), @product (product image). Output: start frame analysis, 1 detailed start frame image prompt (matching the reference composition with the user's influencer + product), 1 concise motion control video prompt (the motion comes from the reference — prompt stays minimal), 3 engaging text overlay options with emojis (story-style EN UK, TikTok compliant), and product info with a compact title (format: '[item] here xx'). Trigger on: 'motion control', 'motion transfer', 'reference video UGC', 'start frame + reference', 'UGC video', 'clothing UGC', 'makeup UGC', 'beauty UGC', 'skincare UGC', 'product UGC', or any request involving a reference video whose motion should drive a generated video of an influencer with a product."
---

# UGC Motion Control Video Generator — Any Niche

Generate a complete, production-ready prompt package for a **motion control** UGC video. The pipeline takes a reference video's start frame (the motion template), an AI influencer, and a product — and produces a detailed start frame image prompt plus a concise video prompt. Because motion control uses a reference video, the motion is **transferred** from the reference — the video prompt stays short and simple.

> **CRITICAL RULE**: The first thing you must do is **analyse the provided start frame from the reference video** (`@start_frame_ref`) to understand the scene, composition, body proportions, pose, camera angle, lighting and mood. The generated start frame image must match the reference composition — only the face/body identity (`@influencer`) and the product (`@product`) change.

---

## Format Overview

```
MOTION CONTROL VIDEO
├── Reference video             (user provides — drives motion)
├── Start Frame of reference    (@start_frame_ref — you analyse this)
│
├── Output 1: Start Frame Image Prompt
│   Detailed prompt matching reference composition
│   + user's @influencer face/body + @product
│   Markers used: @influencer @product
│
└── Output 2: Video Prompt (concise)
    Short motion description — reference carries the motion
    No markers
```

- **1 start frame analysis** (scene, composition, pose, lighting, mood)
- **1 detailed image prompt** for the new start frame (matching reference, with user's influencer + product)
- **1 concise video prompt** (motion control — short because reference drives motion)
- **3 engaging text overlay options** (story-style, EN UK, emojis, TikTok compliant)
- **Product info**: compact title (format: "[item] here xx") + description (max 40 chars) + 3 hashtags

> **The formula**: reference motion + user's influencer identity + user's product + detailed scene recreation + engaging emoji text overlay. The output looks like a real creator genuinely reacting to or showing off the product.

---

## Required Inputs

Before generating, confirm you have:

1. **`@start_frame_ref`** — The first frame extracted from the reference/model video. This is the motion template's opening composition. **REQUIRED — you must analyse this.**
2. **`@influencer`** — AI influencer image. The face, skin, hair and body type of the person who will appear in the generated video. **REQUIRED.**
3. **`@product`** — Product photo (clothing, makeup, skincare, accessories, etc.). **REQUIRED.**
4. **Product name + type + niche + key selling point** — Example: "TIA Push Up Jeans — fashion — lifts and shapes", or "Glow Serum — skincare — 7-day radiance". **REQUIRED.**
5. **Size (if applicable)** — For clothing/apparel. Example: "Size 10", "M". Used in title.

If any required input is missing, ask the user to provide it before proceeding.

---

## Workflow

```
Stage 1: Start Frame Analysis (analyse @start_frame_ref)
        → Scene, composition, body/pose, lighting, mood, niche
Stage 2: Start Frame Image Prompt (detailed, with markers)
        → Recreate reference composition with @influencer + @product
Stage 3: Video Prompt (CONCISE — motion from reference)
        → 2-4 short lines only
Stage 4: Text Overlay (3 engaging options with emojis)
        → Story-style, EN UK, TikTok compliant
Stage 5: Product Info
        → Title "[item] here xx" + description (40 chars) + 3 hashtags
```

---

## Stage 1 — Start Frame Analysis

Analyse `@start_frame_ref` carefully. Extract every detail you can see. This is the foundation for the image prompt.

### Analysis Checklist

| Analysis Point | What to Extract from `@start_frame_ref` |
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

Generate **1 ultra-realistic image prompt** that recreates the reference composition from Stage 1 — but with the user's `@influencer` face/body and `@product` as the hero product.

> **CRITICAL**: The prompt must match the reference composition closely (shot type, camera angle, pose, lighting, environment) — only the identity and product change. The reference supplies the visual blueprint.

### Mandatory First Line — Markers

```
@influencer @product
```

- `@influencer` — ALWAYS present (person's face, skin, hair, body type)
- `@product` — ALWAYS present (exact product colour, texture, details)

### 11-Layer Detailed Prompt Structure

Write as **one flowing paragraph** — all layers woven into a detailed natural-reading brief. **Be specific and detailed** — scene description, proportions, accentuated body parts, pose, lighting.

```
### Start Frame — Image Prompt

@influencer @product

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

[SUBJECT + EXPRESSION — confident happy smile / playful surprise /
excited reaction / seductive smile, bright eyes, genuine enthusiasm
reading the mood of the reference. MANDATORY: genuine emotion — never
flat or catalogue-style].

[ACCENTUATED BODY DESCRIPTION — for fashion: 'high-waisted jeans hug
hips, accentuating waist-to-hip ratio, cinched at natural waist'; for
beauty: 'full lips catching highlight, defined cheekbones, glowing
skin'; for skincare: 'bare clean skin, visible pores, dewy texture'.
Match what the reference shot is selling.]

Wearing/using [EXACT description from @product: garment type + fit +
colour + material + construction details] OR [makeup product details:
colour, finish, application style] OR [skincare product: colour,
bottle, application].

[POSE — match reference exactly: standing with weight on one leg, hand
on hip, other hand holding phone / leaning forward slightly / one hand
applying product to cheek / arm across waist highlighting silhouette].

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

- **`@influencer`** on first line — same face, skin, hair, body type across all renders
- **`@product`** on first line — same product with exact colour, texture, details
- Product must match reference placement (held / worn / applied)
- Composition must match reference (shot type, angle, proportions)
- Environment details should echo the reference scene

---

## Stage 3 — Video Prompt (CONCISE — Motion Control)

Generate **1 short video prompt**. Since this is **motion control**, the motion comes from the reference video — the prompt must stay minimal and let the reference drive the movement.

> **NO MARKERS**: The video prompt does NOT use `@influencer`, `@product`, or any markers. Write directly.

### Rules for Motion Control Video Prompts

1. **Keep it SHORT** — 2-4 short lines total
2. **Describe the scene + subject briefly** — the motion reference will supply the movement
3. **Preserve identity and product** — explicit constraint line
4. **No over-specified motion** — do NOT write long action descriptions, the reference handles that
5. **Include essential texture/mood keywords** — so the render stays realistic
6. **Negative prompt** — minimal but covers the usual artifacts

### Video Prompt Template

```
### Video Prompt — Motion Control (concise)

[Shot type matching start frame — e.g., "Full-body mirror selfie"
OR "Waist-up close-up" OR "Face close-up"], 9:16 vertical, 24fps.

Subject: [short subject description — woman in her bedroom/bathroom/
etc., wearing/using EXACT product from start frame — one short line].

[Texture + lighting line — e.g., "Ultra-realistic skin texture, true-
colour fabric/product rendering, bright natural window light, film
grain"].

Keep identity, clothing/product, hair and accessories exactly as in
start frame. No text on screen, stable geometry, no flicker.

Negative: cartoon, 3D render, plastic skin, plastic fabric, text,
captions, extra fingers, face distortion, identity drift.
```

### Example (Fashion — Jeans)

```
Full-body mirror selfie, 9:16 vertical, 24fps.

Subject: woman in her bright bedroom, high-waisted light-wash
push-up jeans paired with a cropped white tee and white trainers.

Ultra-realistic skin texture, visible denim weave, true-colour
rendering, bright natural window light, subtle film grain.

Keep identity, clothing, hair and accessories exactly as in start
frame. No text on screen, stable geometry, no flicker.

Negative: cartoon, 3D render, plastic skin, plastic fabric, text,
captions, extra fingers, face distortion, identity drift.
```

### Example (Beauty — Lip Gloss)

```
Face close-up, 9:16 vertical, 24fps.

Subject: woman in her bright bathroom, applying a glossy nude pink
lip tint with a doe-foot applicator.

Ultra-realistic skin pores, visible lip texture, glossy sheen
catching light, soft ring-light frontal fill, subtle film grain.

Keep identity, product, hair and accessories exactly as in start
frame. No text on screen, stable geometry, no flicker.

Negative: cartoon, 3D render, plastic skin, waxy lips, text,
captions, extra fingers, face distortion, identity drift.
```

---

## Stage 4 — Text Overlay (3 Engaging Options with Emojis)

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

### Title — Fixed Compact Format: `[item] here xx`

Based on the reference format "Jeans here xx" — always compact, same short length.

**Pattern**: `[garment/product type] here [suffix]`

Where `[suffix]` is one of:
- `xx` (kisses — the reference default)
- `x` (single kiss)
- A size if clothing — `10`, `12`, `S`, `M`, `L`
- `♡` (only if the user wants a light emoji)

**Rules**:
- Max 30 characters
- Ideally 10-20 characters (matching "Jeans here xx" compact feel)
- Lowercase
- EN UK
- Always ends with suffix (xx / x / size / ♡)
- No exclamation marks, no fake urgency

**Examples (matching "Jeans here xx" feel)**:
- `jeans here xx` (13 chars)
- `jeans here 10` (13 chars)
- `dress here xx` (13 chars)
- `gloss here xx` (13 chars)
- `serum here xx` (13 chars)
- `blush here x` (12 chars)
- `jacket here M` (13 chars)
- `skirt here 12` (13 chars)
- `foundation here ♡` (17 chars)

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

━━━ Title (≤30 chars, compact format) ━━━

[item] here xx — [X chars]

━━━ Description (≤40 chars) ━━━

[personal experience with optional emoji] — [X chars]

━━━ Hashtags ━━━

#[product] #[niche/quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Complete Output Package

Deliver all outputs in this order:

```
# UGC Motion Control — {Product Name}

## 1. Start Frame Analysis

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

@influencer @product

"[Detailed full prompt — 11 layers, single paragraph, matching
reference composition, proportions, accentuated body, pose,
lighting, mood, environment. iPhone/mirror selfie allowed if
reference shows it.]"

---

## 3. Video Prompt — Motion Control (concise)

[2-4 short lines only — shot type + subject + texture/lighting +
constraints + negative. NO MARKERS.]

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

━━━ Title (≤30 chars, compact format) ━━━

[item] here xx — [X chars]

━━━ Description (≤40 chars) ━━━

[personal experience with optional emoji] — [X chars]

━━━ Hashtags ━━━

#[product] #[niche/quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Technical Specs
- **Format**: Vertical 9:16
- **Pipeline**: Motion Control (reference video drives motion)
- **Image generation**: 1 detailed start frame prompt (with markers)
- **Video generation**: 1 concise motion control prompt (no markers)
- **Niche**: Any (fashion, beauty, skincare, makeup, accessories, lifestyle)
- **Text overlay**: Added in post-production by user (CapCut/TikTok)
- **Music**: Added on platform by user
- **Language**: English UK (all text content)
```

---

## Quality Standards

| # | Criteria | Pass | Fail |
|---|----------|------|------|
| 1 | Start frame analysis present | All 13 analysis points filled from `@start_frame_ref` | Missing analysis or generic values |
| 2 | Niche correctly detected | Fashion / beauty / skincare / makeup / accessories / lifestyle | Wrong niche or generic "product" |
| 3 | Shot type matches reference | Full-body/close-up/etc. matches reference exactly | Drift from reference shot type |
| 4 | Camera angle matches reference | Phone position, height, angle match reference | Drift from reference angle |
| 5 | Body proportions match reference | Face %, body %, product placement match reference | Wrong proportions |
| 6 | Accentuated body part specified | Hips/waist/lips/etc. — what the shot sells is called out | Not specified what shot highlights |
| 7 | Pose matches reference | Detailed body position matching reference | Generic pose |
| 8 | Expression matches reference mood | Happy/surprised/excited — matching reference energy | Flat or mismatched |
| 9 | Environment matches reference | Same room type + 3+ named objects matching reference | Generic or wrong room |
| 10 | Lighting matches reference | Source + direction + temperature matching reference | Generic lighting |
| 11 | `@influencer` + `@product` markers | Both on first line of image prompt ONLY | Missing from image OR present in video prompt |
| 12 | Image prompt detailed | 11 layers, single paragraph, detailed scenery + proportions + body + pose | Shallow or missing layers |
| 13 | Video prompt CONCISE | 2-4 short lines only — motion not over-specified | Long motion description (that belongs to the reference) |
| 14 | Video prompt no markers | Direct description, no @influencer or @product | Markers in video prompt |
| 15 | Identity preservation constraint | "Keep identity, clothing/product" in video prompt | Missing constraint |
| 16 | Negative prompt complete | Cartoon, plastic skin, text, face distortion, identity drift | Missing key negatives |
| 17 | Text overlay story-style | Engaging hook, reaction, story feel — like img-1 reference | Dry statement without hook |
| 18 | Text overlay emojis | 1-3 emojis naturally placed | No emojis OR emoji spam (5+) |
| 19 | Text overlay EN UK | UK spelling + casual British register | US English or mixed |
| 20 | Text overlay word count | 10-25 words per option | <8 words (too short) or >30 words (too long) |
| 21 | TikTok compliance | No banned words, no fake urgency, no absolute claims | Any banned phrase |
| 22 | Title compact format | `[item] here xx` pattern — 10-20 chars typical, ≤30 max | Wrong format or over 30 chars |
| 23 | Title lowercase EN UK | All lowercase (except brand), EN UK spelling | Caps or US English |
| 24 | Description character count | ≤40 chars including emoji, personal tone | Over 40 chars or product spec language |
| 25 | Hashtag count + format | Exactly 3 lowercase EN UK hashtags: #product #niche #reach | Wrong count, caps, or irrelevant |
| 26 | iPhone/mirror selfie allowed | Permitted in start frame if reference shows it | N/A — previous restriction removed |
| 27 | Any niche supported | Fashion / beauty / skincare / etc. all supported | Fashion-only thinking |
| 28 | Reference composition fidelity | Image prompt recreates reference scene composition faithfully | Creative drift from reference |

---

## References

- `ultra-realitic-images-prompt.md` (project root) — Ultra-realistic image prompt methodology
- Reference TikTok analysis — `img-1.png` (story-style emoji text overlay), `img-2.png` (compact title format "Jeans here xx"), `img-3.png` (engaging emoji descriptions)
- Motion control concept — reference video supplies motion; start frame + concise prompt supply identity + product
- TikTok Shop content compliance — Banned/allowed words for text overlays
