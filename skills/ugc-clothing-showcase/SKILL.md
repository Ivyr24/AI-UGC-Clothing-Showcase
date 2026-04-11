---
name: ugc-clothing-showcase
description: "Generate 1-shot 8s silent UGC clothing showcase videos. Input: @influencer + @product + product name/type + key selling point. Output: product analysis, 1 full-body start frame image prompt, 1 video prompt (8s walk + turn + pose, Kling 3.0), 3 text overlay options (EN UK, TikTok compliant), and product info (title + description + 3 hashtags). The model wears the clothing and shows how it looks through natural confident movement. No speech — only happy expressions and body confidence. Text overlay added in post. Trigger on: 'clothing showcase', 'outfit video', 'clothing UGC', 'fashion UGC', '1 shot clothing', 'show outfit', 'OOTD video', 'mirror selfie video', 'try-on video', 'clothing ad', or any request for a short UGC clip showing how clothing looks on a model."
---

# UGC Clothing Showcase — 1-Shot 8s Silent Video Generator

Generate a complete, production-ready prompt package for a 1-shot 8-second silent UGC clothing showcase video. The influencer wears the garment and shows how it looks on her body through a natural **walk + turn + pose** sequence — no speech, no hand-held product. Text overlay (added in post-production) carries the hook. The output must feel like a real influencer filming herself showing off a new outfit she's genuinely excited about.

> **CRITICAL RULE**: The clothing from `@product` MUST be clearly visible in every frame — full outfit head to toe. This is a clothing showcase, not a face close-up. The garment is the hero.

---

## Format Overview

```
VIDEO (8 seconds — 1 shot)
├── Start Frame  (full-body standing shot — image prompt)
│   Pose: standing confidently, happy smile, both hands free
│
└── Movement Arc (8s — walk + turn + pose)
    0-3s: Walk toward camera with confident stride
    3-5s: Natural turn showing garment from different angle
    5-8s: Return to face camera, settle into confident pose
```

- **1 image prompt** for the start frame (full-body standing shot, 9:16)
- **1 video prompt** describing the 8s walk + turn + pose arc (Kling 3.0)
- **3 text overlay options** (short personal discovery, EN UK, TikTok compliant)
- **Product info**: title (30 chars, includes size) + description (40 chars) + 3 hashtags
- **Always silent** — no dialogue, no lip movement suggesting speech

> **The formula**: confident model + clothing that looks amazing on her + natural movement showing fit from every angle + short punchy text overlay. The viewer thinks "I need those" — not "she's selling me something."

---

## Required Inputs

Before generating, confirm you have:

1. **`@influencer`** — AI influencer image (uploaded). Visual anchor for the model's face, hair, body type. **REQUIRED.**
2. **`@product`** — Clothing product photo, ideally flat lay or on model/mannequin. Ensures accurate garment details. **REQUIRED.**
3. **Product name + type + key selling point** — Example: "TIA Push Up Jeans — high-waisted, flattering fit, lifts and shapes". **REQUIRED.**
4. **Garment size** — Example: "Size 10", "M", "L". Used in the product title. **REQUIRED.**

If `@influencer` or `@product` are missing, ask the user to provide them before proceeding.

---

## Workflow

```
Stage 1: Product & Audience Analysis
        → Detect clothing type, features, target audience, movement map
Stage 2: Start Frame — Image Prompt
        → Full-body standing shot, ultra-realistic, 9:16
Stage 3: Video Prompt (8s, Kling 3.0)
        → Walk + turn + pose with clothing-specific physics
Stage 4: Text Overlay (3 options)
        → Short personal discovery, EN UK, TikTok compliant
Stage 5: Product Info
        → Title (30 chars) + description (40 chars) + 3 hashtags
```

---

## Stage 1 — Product & Audience Analysis

Analyse `@product` image and user description to extract:

| Analysis Point | What to Extract |
|----------------|----------------|
| **Clothing type** | Jeans, dress, top, jacket, skirt, set, jumpsuit, activewear, etc. |
| **Fit** | Slim, relaxed, oversized, tailored, high-waisted, cropped, etc. |
| **Key visual feature** | Texture (denim, silk, knit), detail (buttons, zip, pattern), wash/colour |
| **Selling point** | Comfort, flattering fit, versatile, affordable, trending, shapes body |
| **Target audience** | Age range + style tribe (casual, smart-casual, going-out, athleisure) |
| **Season/occasion** | Summer, winter, date night, work, everyday, festival |
| **Colour palette** | Main colour + accent colours from `@product` |

### Clothing-to-Movement Map

Based on the detected clothing type, select the optimal movement pattern:

| Clothing Type | Primary Movement (0-3s) | Turn Style (3-5s) | Pose (5-8s) |
|---------------|------------------------|-------------------|-------------|
| **Jeans/Trousers** | Walk toward camera — show front fit, hip movement | 180° turn showing rear fit and pockets | Hand on hip, weight shifted, confident stance |
| **Dress** | Walk with natural fabric sway, arms relaxed | Gentle turn letting fabric flow and catch light | Slight hip shift, hand at side, full silhouette visible |
| **Top/Blouse** | Confident stride showing torso fit, arms swing | Shoulder-led turn showing neckline and back | Shoulders back, arms visible, relaxed confident pose |
| **Jacket/Coat** | Walk with jacket open, structure visible | Turn showing back/shoulder structure | One hand on lapel or in pocket, squared shoulders |
| **Skirt** | Walk with natural fabric sway at hem | Slight spin letting pleats/fabric move | Weight on one hip, fabric settled, full length visible |
| **Set/Co-ord** | Full confident walk showing coordination | Turn showing pieces together from behind | Relaxed stance, both pieces visible head to toe |
| **Jumpsuit** | Stride with arm swing, waist cinch visible | Turn showing back detail and overall silhouette | Hand on hip, emphasising waist definition |
| **Activewear** | Dynamic walk with slight bounce, fabric stretch | Side step showing stretch and fit | Athletic stance, fabric moulding to body |

### Output Format

```
### Product & Audience Analysis

- **Clothing type**: [detected]
- **Fit**: [slim/relaxed/oversized/etc.]
- **Key feature**: [texture/detail/colour]
- **Selling point**: [comfort/style/versatility/flattering]
- **Target audience**: [age + style tribe]
- **Season/occasion**: [when to wear]
- **Colour palette**: [main + accent]
- **Movement pattern**: [primary walk + turn style + final pose]
```

---

## Stage 2 — Start Frame Image Prompt

Generate **1 ultra-realistic full-body image prompt** — compact single-paragraph format. **NO phone, NO mirror selfie** — the model is NOT holding any device.

> **CRITICAL**: Follow the full-body clothing format from `ultra-realitic-images-prompt.md` (project root). Face ~25-35% of frame, full outfit visible head to toe. Both hands free — natural pose, no phone.

### Mandatory First Line

Every prompt starts with reference markers:

```
@influencer @product
```

- `@influencer` — ALWAYS present (person's face, skin, hair, body type)
- `@product` — ALWAYS present (correct garment, exact colour, texture, details)

### 11-Layer Compact Prompt Structure

Write as **one flowing paragraph** — all essential layers woven into a single natural-reading brief:

```
### Start Frame — Image Prompt

@influencer @product

"Ultra-realistic full-body standing shot, straight-on camera at waist 
height, full body visible head to toe in a [bright bedroom/hallway], 
model fills ~85% of vertical 9:16 frame height, face ~[25-30]%; 
[expression — confident happy smile, bright eyes, genuine enthusiasm, 
looking directly at camera. MANDATORY: happiness and confidence — never 
neutral or flat]. Both hands free — no phone, no device.

Wearing [full clothing description from @product: garment type, fit, 
colour/wash, material, key construction details (stitching, buttons, 
pockets, zip), how it sits on body (hugs hips, drapes shoulders, cinches 
waist), hem detail, any pattern or distressing].

Paired with [complementary footwear] and [accessories if any].

Standing with [pose adapted to clothing type: weight distribution, hand 
position, body angle — shows garment silhouette at its best].

Sharp focus on model and clothing simultaneously, fabric texture visible. 
[Room type] with [object 1], [object 2], [object 3] — softly blurred 
bokeh, lived-in personal space.

[Lighting — bright natural window light, source + direction + 5500K 
daylight for true-colour fabric rendering].

Visible skin pores, stray hairs at hairline, natural texture — no filter. 
[Fabric realism — visible weave/texture, natural creasing, stitching 
detail, how light catches material, realistic drape].

Mood: [confident, bright, authentic UGC energy / excited new outfit 
energy].

Negative: CGI, cartoon, airbrushed skin, plastic texture, plastic fabric, 
stiff fabric, text, watermark, extra fingers, mannequin pose, catalogue 
shot, studio backdrop, fashion editorial, overly posed, DSLR, holding 
phone, mirror selfie, phone in hand, mirror reflection."
```

### Character Consistency Rules

- **`@influencer`** on first line — same face, skin, hair, body type
- **`@product`** on first line — same garment with exact colour, texture, details
- **Same accessories** described (jewellery, shoes, belt)
- **Same hair state** (up/down, styled/natural)
- Outfit description word-for-word identical in image and video prompts

---

## Stage 3 — Video Prompt (8s, Kling 3.0)

Generate **1 video prompt** for the 8-second walk + turn + pose sequence.

> **NO MARKERS**: The video prompt does NOT use `@influencer`, `@product`, or any reference markers. Write the subject description and clothing description directly — no placeholders. Only the image prompt (Stage 2) uses markers.

### Kling 3.0 Master Formula (5 Layers)

Every Kling 3.0 video prompt follows this structure:

```
1. [CAMERA MOVEMENT]          — ONE specific move with speed
2. [SUBJECT & ACTION PHYSICS] — Walk + turn + pose with clothing physics
3. [ENVIRONMENT / LIGHTING]   — Named room + objects + true-colour light
4. [TEXTURE & DETAILS]        — Skin pores, fabric weave, film grain
5. [CONSTRAINTS / NEGATIVE]   — Keep identity, no text, negative prompt
```

### Key Kling 3.0 Rules

1. **2-6 short lines** — concise director's shot list, not verbose essays
2. **ONE camera move** — combining multiple causes wobble and identity drift
3. **Physics-based motion** — describe HOW things move, not just what:
   - Bad: "She walks" → Good: "Steady pace, heel-first landing, rolling forward with visible weight transfer"
   - Bad: "She turns" → Good: "Body rotates 180° to the right, hips leading, shoulders following, hair swinging with momentum"
4. **Anchor feet to floor** — sliding feet are Kling 3.0's #1 full-body artifact
5. **Name real light sources** — never "dramatic lighting"
6. **Texture keywords mandatory** — Kling defaults to plastic without explicit texture calls
7. **Constraints line mandatory** — "Keep identity exactly, keep clothing"
8. **Negative prompt mandatory** — prevents common artifacts

### Movement Arc: Walk + Turn + Pose (Timed to 8 Seconds)

| Seconds | Beat | Movement Description | Clothing Physics |
|---------|------|---------------------|-----------------|
| **0-3s** | **Walk** | Model walks toward camera with confident natural stride. Heel-first landing, visible weight transfer, arms swing naturally at sides. | Fabric moves with body: denim stretches at thighs, dress hem sways, jacket swings from button point |
| **3-5s** | **Turn** | Natural body rotation (180° or 360°) showing garment from behind/side. Hips lead, shoulders follow, hair swings with momentum. | Rear details visible: back pockets, rear fit, back drape, hem movement during rotation |
| **5-8s** | **Pose** | Returns to face camera, settles into confident pose. Weight shifts to one leg, body settles. Direct eye contact with camera. | Clothing settles after movement: fabric drapes naturally, creases form at joints, silhouette is clearly defined |

### Clothing-Specific Physics Keywords

| Fabric Type | Physics for Walk | Physics for Turn | Physics for Pose |
|-------------|-----------------|------------------|-----------------|
| **Denim** | "Denim stretches slightly at thighs with each step, natural creasing at knees, hem brushes trainers" | "Rear pockets shift with hip rotation, waistband sits flat through turn, fabric weight maintains structure" | "Fabric settles at thighs, natural crease pattern visible, structured drape from waist to ankle" |
| **Silk/Satin** | "Fabric flows and catches light with each step, hem sways with momentum, subtle sheen shifts" | "Fabric billows outward during turn, catches light at new angles, drapes reset with momentum" | "Fabric settles into gravity-led drape, sheen visible on hip and thigh, hem weight pulls straight" |
| **Knit/Jersey** | "Soft fabric moulds to body during movement, gentle stretch and recovery visible, hem bounces" | "Fabric clings during rotation, natural stretch at waist, recovery visible as body settles" | "Fabric moulds to settled pose, natural cling at waist and hip, soft drape from relaxed arm" |
| **Cotton** | "Lightweight cotton shifts with arm swing, slight wrinkle at waist, hem lifts with stride" | "Cotton moves freely with rotation, natural flutter at hem, wrinkles shift with body" | "Cotton settles naturally, soft wrinkles at action points, light catching flat surfaces" |
| **Structured (blazer)** | "Structured shoulders maintain shape, lapels hold position, fabric swings from button point, back vent opens" | "Structure maintains through turn, shoulder pads hold line, open front swings with momentum" | "Jacket settles on shoulders, lapels fall into place, structured silhouette clearly defined" |
| **Pleated/Flowy** | "Pleats separate and rejoin with each step, fabric billows, hem creates wave-like motion" | "Pleats fan outward during spin, fabric catches maximum light in folds, beautiful full rotation" | "Pleats settle vertically, fabric weight pulls folds closed, elegant static drape" |

### Camera Moves for Full-Body Clothing (Pick ONE)

| Move | How to Write | Best For |
|------|-------------|----------|
| **Locked + micro-jitter** (DEFAULT) | "Locked camera with subtle handheld micro-jitter, no directional drift" | Authentic handheld UGC feel |
| **Slow dolly-in 3%** | "Slow dolly-in, camera pushes forward 3% over 8s toward the model" | Builds intimacy as she approaches |
| **Slow tilt up** | "Slow tilt up from feet to face over 8s" | Dramatic outfit reveal (shoes to face) |
| **Organic drift** | "Organic handheld drift, camera moves 2% right over 8s with micro-shake" | Dynamic energy for walk sequences |

### Video Prompt Template

```
### Shot 1 — Video Prompt (0s-8s) — Silent — Kling 3.0

[CAMERA MOVE — e.g., "Locked camera with subtle handheld micro-jitter"],
[LENS — 35mm equivalent, full-body framing, 9:16 vertical].

Subject: [description matching the influencer] woman in her [bright room type],
wearing [EXACT outfit description from Stage 2 — word-for-word identical
to image prompt clothing description, including footwear and accessories].

0-3s WALK: She walks toward the camera with a confident natural stride — 
heel-first landing, rolling forward with visible weight transfer, arms 
swinging naturally at her sides. [Clothing-specific physics from table 
above]. Her expression is bright and happy — genuine wide smile, bright 
eyes, looking at camera with natural confidence and excitement.

3-5s TURN: She begins a natural [180°/360°] turn to [her right/left] — 
hips leading the rotation, shoulders following naturally, [hair description 
— swings/bounces with the momentum]. [Rear/side clothing view description: 
what becomes visible — back pockets, rear silhouette, back drape, etc.]. 
Her head follows the turn, briefly looking over her shoulder [with a 
playful/confident glance].

5-8s POSE: She completes the turn to face the camera again, settling 
into a confident pose — [specific pose from clothing-to-movement map: 
weight shift, hand position, body angle]. Direct eye contact with camera, 
warm satisfied smile. [Clothing settles after movement: fabric drape, 
crease pattern, silhouette clearly visible].

Environment: [bright room type] with [object 1], [object 2], [object 3] 
— softly blurred bokeh. [Lighting — bright natural window light from 
camera-left/right, 5500K daylight, true-colour fabric rendering, gentle 
shadows].

Texture: visible skin pores, stray hairs at hairline, [fabric texture — 
denim weave/silk sheen/rib pattern/knit texture], natural fabric creasing, 
stitching detail, film grain. No beauty filter.

No speech, mouth stays with natural happy smile — no lip movement 
suggesting speech. Background audio: natural room ambience only.

Duration: 8s, 9:16 vertical, 24fps.

Keep identity exactly, keep clothing, hair, accessories, and footwear. 
Keep background layout. No new objects, no text on screen, stable 
geometry, no flicker.

Negative: cartoonish, 3D render, smooth plastic skin, plastic fabric, 
stiff fabric, floating limbs, sliding feet, moonwalking, text morphing, 
text on screen, captions, extra fingers, mutated hands, face distortion, 
identity drift, mannequin pose, catalogue look, fashion editorial, 
OPEN MOUTH SPEAKING, mid-speech lip position, talking.
```

---

## Stage 4 — Text Overlay (3 Options)

Text is added by the user in post-production (CapCut, TikTok editor). Generate **3 variations** — short personal discovery style.

### Style Rules

- **Max 10 words** on screen — one short sentence
- **Personal discovery tone** — "Didn't know jeans could be this comfy" (like img-2 reference)
- **EN UK language mandatory** — "colour" not "color", "bum" not "butt", "favourite" not "favorite"
- **Conversational** — as if texting a best friend
- **No ALL CAPS** except brand names
- **No emojis** or max 1 if genuinely natural
- **First-person** — "I", "my", "me" language
- **No hard sell** — discovery, not persuasion

### TikTok Shop Content Compliance — MANDATORY

**BANNED words/phrases (NEVER use):**
- "Cheapest" / "lowest price" / "best price" / any superlative pricing
- "Cure" / "treat" / "heal" / any medical claim
- "Lose weight" / "slim" / "slimming" / any body-shaming language
- "Instant results" / "guaranteed" / absolute claims
- "RUN" / "HURRY" / "LAST CHANCE" / fake urgency/scarcity
- "Before and after" / transformation comparisons
- "#1" / "best ever" / unverifiable superlatives
- Body-shaming language of any kind
- Competitor names or disparagement

**ALLOWED copywriting triggers:**
- **Personal discovery**: "Didn't know [item] could [quality]"
- **Curiosity**: "Have you seen...?" / "Nobody told me..."
- **Social proof**: "viral" / "trending" / "everyone's asking"
- **Personal experience**: "I've been wearing these for [X] weeks"
- **Identity**: "for my [body type/style] girls"
- **Value**: "worth every penny" / "such a find"
- **Casual reaction**: "genuinely unreal" / "obsessed"
- **Soft scarcity**: "whilst the sale's still on" (only if true)

### Text Overlay Patterns (pick 3 and adapt to the specific product)

| Pattern | Template | Example |
|---------|----------|---------|
| **Personal discovery** | "Didn't know [item] could [quality]" | "Didn't know jeans could be this comfy" |
| **Friend discovery** | "Nobody told me about these [item]" | "Nobody told me about these jeans and I'm fuming" |
| **Casual reaction** | "These [item] are genuinely [reaction]" | "These jeans are genuinely unreal" |
| **Simple statement** | "[Item] that actually [benefit]" | "Jeans that actually fit properly" |
| **Soft question** | "Have you tried [brand]'s [item] yet?" | "Have you tried TIA's push-up jeans yet?" |
| **Personal result** | "The way these [item] [benefit]" | "The way these jeans lift everything" |
| **Trend hook** | "The viral [item] everyone's wearing" | "The viral jeans everyone's been wearing" |

### Output Format — COPY-READY

```
### Text Overlay Options — COPY-READY (EN UK)

━━━ Option 1 — Personal Discovery ━━━

[adapted text — max 10 words]

━━━ Option 2 — [Pattern name] ━━━

[adapted text — max 10 words]

━━━ Option 3 — [Pattern name] ━━━

[adapted text — max 10 words]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

> TikTok Shop compliant — no superlatives, no body-shaming,
> no fake urgency, no absolute claims.
```

---

## Stage 5 — Product Info

### Title (max 30 characters)

Friend-to-friend recommendation format. As if sharing with a mate. **Must include garment size.**

**Pattern**: "[Garment] here [size]" / "my best [item] [size]" / "[item] [size] — worth it"

Based on the reference format "Jeans here xx" — simple, casual, includes size.

**Rules**:
- Max 30 characters (count precisely)
- **MUST include the garment size** (S, M, L, XL, 6, 8, 10, 12, 14, etc.)
- EN UK language
- Lowercase (no caps except brand names if included)
- Friend recommendation tone — casual, genuine
- No exclamation marks, no emojis
- Must feel like a girl telling her friend about something great she found

**Examples**:
- "jeans here 10" (14 chars)
- "dress here S" (12 chars)
- "my best jeans find size 12" (27 chars)
- "these jeans M — trust me" (25 chars)
- "the dress everyone needs L" (27 chars)
- "jacket here XL" (15 chars)

### Description (max 40 characters)

One short sentence describing the key benefit or personal experience.

**Rules**:
- Max 40 characters (count precisely)
- EN UK language
- Conversational tone — personal experience, not product spec
- First-person where possible

**Examples**:
- "so comfy I forgot I was wearing them" (37 chars)
- "flattering on literally every body type" (40 chars)
- "the fit is actually insane" (27 chars)
- "they go with literally everything" (34 chars)
- "genuinely the comfiest jeans I own" (35 chars)

### 3 Hashtags for TikTok Ranking

**Formula**: #[garment type] + #[style/quality keyword] + #[broad reach]

**Rules**:
- Exactly 3 hashtags
- EN UK
- Lowercase only
- First = specific garment type (#jeans, #dress, #jacket)
- Second = key quality or style attribute (#flattering, #comfortable, #fashion)
- Third = broad reach hashtag (#fyp, #trending, #ootd)
- No spaces within hashtags

**Examples by category**:
- Jeans: `#jeans #flattering #fyp`
- Dress: `#dress #datenight #fyp`
- Top: `#croptop #fashion #trending`
- Jacket: `#jacket #winterstyle #fyp`
- Skirt: `#midiskirt #ootd #trending`

### Output Format — COPY-READY

```
### Product Info — COPY-READY

━━━ Title (≤30 chars) ━━━

[friend recommendation title with size] — [X chars]

━━━ Description (≤40 chars) ━━━

[personal experience] — [X chars]

━━━ Hashtags ━━━

#[garment] #[quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Complete Output Package

Deliver all outputs in this order:

```
# UGC Clothing Showcase — {Product Name}

## 1. Product & Audience Analysis
- Clothing type: [detected]
- Fit: [slim/relaxed/oversized/etc.]
- Key feature: [texture/detail/colour]
- Selling point: [comfort/style/versatility/flattering]
- Target audience: [age + style tribe]
- Season/occasion: [when to wear]
- Colour palette: [main + accent]
- Movement pattern: [walk style + turn style + final pose]

---

## 2. Start Frame — Image Prompt

@influencer @product

"[Full-body standing shot prompt — 11 layers, single paragraph, 
face ~25-30%, full outfit visible head to toe, no phone]"

---

## 3. Video Prompt (0s-8s) — Silent — Kling 3.0

[Full video prompt with walk + turn + pose movement arc,
clothing-specific physics, Kling 3.0 format, 2-6 lines]

---

## 4. Text Overlay Options — COPY-READY (EN UK)

━━━ Option 1 — [Pattern] ━━━

[text — max 10 words]

━━━ Option 2 — [Pattern] ━━━

[text — max 10 words]

━━━ Option 3 — [Pattern] ━━━

[text — max 10 words]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## 5. Product Info — COPY-READY

━━━ Title (≤30 chars) ━━━

[title with size] — [X chars]

━━━ Description (≤40 chars) ━━━

[description] — [X chars]

━━━ Hashtags ━━━

#[garment] #[quality] #[reach]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

---

## Technical Specs
- **Duration**: 8 seconds (1 shot)
- **Format**: Vertical 9:16
- **Frame generation**: 1 start frame image prompt
- **Video generation**: 1 x 8s Kling 3.0 prompt
- **Mode**: Silent (no dialogue, happy/confident expressions only)
- **Text overlay**: Added in post-production by user (CapCut/TikTok)
- **Music**: Added on platform by user
- **Language**: English UK (all text content)
```

---

## Quality Standards

| # | Criteria | Pass | Fail |
|---|----------|------|------|
| 1 | Clothing type detection | Correctly identifies garment from @product | Wrong type or generic "clothing" |
| 2 | Movement map selection | Correct primary walk + turn + pose for the garment type | Generic walk for all types |
| 3 | Full-body framing | Face ~25-35%, full outfit visible head to toe | Face fills >50% or outfit cut off at legs |
| 4 | Full-body standing shot | Straight-on camera at waist height, both hands free, no phone | Mirror selfie, phone in hand, or catalogue shot angle |
| 5 | Expression mandatory | Enthusiastic, happy, confident — genuine smile, bright eyes | Neutral, flat, deadpan, or overly posed model face |
| 6 | Clothing detail depth | Full description: type, fit, colour, texture, how it sits on body, construction details | Vague "wearing jeans" or missing material/fit |
| 7 | Clothing physics in video | Fabric-specific movement (stretch, sway, drape, crease, settle) | Generic "clothing moves" or no fabric physics |
| 8 | Walk physics | "Heel-first landing, weight transfer" or equivalent | "She walks" without physics |
| 9 | Turn description | Specific rotation (180°/360°), hips leading, hair swing, rear view | "She turns around" without detail |
| 10 | Pose specificity | Named pose: weight shift, hand position, body angle | "She poses" without specifics |
| 11 | 3-beat timing | Walk (0-3s) + turn (3-5s) + pose (5-8s) timed to 8 seconds | Missing beats or wrong timing |
| 12 | @influencer/@product markers | Both on first line of image prompt ONLY (never in video prompt) | Markers missing from image prompt OR markers present in video prompt |
| 13 | Same outfit across prompts | Exact clothing description word-for-word in image AND video prompts | Drift between image and video prompts |
| 14 | Camera move (Kling 3.0) | ONE move specified with direction + speed (35mm lens) | Multiple moves or vague "camera follows" |
| 15 | Kling 3.0 format | 2-6 lines, master formula layers, constraints + negative | Verbose essay or missing layers |
| 16 | NO DIALOGUE | Explicit "no speech" + "no lip movement" in video prompt | Missing speech constraint |
| 17 | NO TEXT ON SCREEN | Explicit in video prompt + negative prompt | Missing text constraint |
| 18 | Text overlay word count | Max ~10 words, one sentence | Longer than 10 words or multiple sentences |
| 19 | Text overlay style | Personal discovery, friend tone, clean and minimal | Story-style, emoji-heavy, or salesy |
| 20 | Text overlay EN UK | UK spelling and casual British register throughout | US English or mixed language |
| 21 | TikTok compliance | No banned words, no body-shaming, no fake urgency | Any banned phrase present |
| 22 | Title character count | Max 30 chars, includes garment size, friend recommendation tone, EN UK | Over 30 chars, missing size, or salesy tone |
| 23 | Description character count | Max 40 chars, personal experience, EN UK | Over 40 chars or product spec language |
| 24 | Hashtag format | Exactly 3: #garment #quality #reach — lowercase, EN UK | Wrong count, irrelevant, or wrong format |
| 25 | Fabric realism in image | Visible texture, natural creases, stitching detail mentioned | Smooth/plastic fabric look |
| 26 | Environment correct | Bedroom/hallway with 2-3 named objects, lived-in personal space | Studio backdrop or generic room |
| 27 | Lighting true-colour | Bright natural daylight, 5500K, true-colour fabric rendering | Moody/dark or wrong colour cast on fabric |
| 28 | Negative prompt complete | Includes mannequin pose, catalogue look, sliding feet, moonwalking, plastic fabric | Missing clothing-specific negatives |
| 29 | Footwear specified | Complementary shoes described in both image and video prompts | Missing footwear or mismatched shoes |
| 30 | Compact paragraph format | Image prompt as single flowing paragraph with all 11 layers | Numbered list format or missing layers |

---

## References

- `ultra-realitic-images-prompt.md` (project root) — Full-body clothing image prompt methodology
- Kling 3.0 video prompt best practices — Master formula, camera grammar, physics keywords
- TikTok reference analysis (8 videos, 3 images) — Movement patterns, text overlay language, description style
- TikTok Shop content compliance — Banned/allowed words for text overlays
