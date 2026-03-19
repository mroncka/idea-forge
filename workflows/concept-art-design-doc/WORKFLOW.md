# Workflow: Concept Art Design Document

Generate structured design documents in multiple concept art styles — ready for image generation pipelines.

## Purpose
From a character, environment, or prop description, produce comprehensive design documents across multiple art styles. Each doc contains structured prompts optimized for FLUX.2 Klein, Wan, and ComfyUI workflows.

## Document Types

### 1. Character Sheet
A full-turnaround character design document.
- Front / side / back view prompts
- Expression sheet (happy, angry, sad, determined, surprised)
- Outfit details: materials, colors, accessories, silhouette notes
- Proportions: height ratio, head-to-body, distinguishing features
- Prompt format: `[character name], [style], front view, full body, white background, turnaround sheet, anime/realistic/stylized`

### 2. Environment / World-Building Sheet
- Establishing shot prompt (wide, atmospheric)
- Detail study prompts (architecture, textures, foliage, props)
- Day / night / weather variants
- Color temperature and lighting notes
- Mood keywords: `liminal`, `overgrown`, `neon-noir`, `minimalist`, etc.

### 3. Color Palette Document
- Primary palette (5–7 colors with hex codes)
- Accent / highlight colors
- Shadow / mood tones
- Prompt additions: `color palette: [colors], flat design, style guide`
- Seasonal / time-of-day variants

### 4. Prop / Equipment Sheet
- Isolated object renders (front, side, 3/4 angle)
- Scale reference prompt
- Material callouts (metal, fabric, leather, glow, worn)
- Usage context prompt (held by character, in environment)

### 5. Composition Study
- Rule-of-thirds layout prompts
- Focal point + depth cues
- Framing variants (extreme wide / medium / close-up / POV)
- Dynamic pose / action framing notes
- Style tags by target aesthetic:
  - `anime`: `cell shading, clean lineart, vibrant colors, studio-quality`
  - `realistic`: `photorealistic, octane render, detailed textures, volumetric lighting`
  - `concept art`: `matte painting, concept art, artstation, dramatic lighting`
  - `flat design`: `flat illustration, vector style, minimal shading, bold colors`
  - `ukiyo-e`: `ukiyo-e woodblock, Japanese art, bold outlines, flat color fields`

## Output
```
/design-doc/
  CHARACTER_SHEET.md
  ENVIRONMENT.md
  COLOR_PALETTE.md
  PROPS.md
  COMPOSITIONS.md
  PROMPTS_COMFYUI.json   — machine-readable prompts for direct ComfyUI import
```

## Config
```json
{
  "workflow": "concept-art-design-doc",
  "subject": "character | environment | prop | scene",
  "description": "...",
  "styles": ["anime", "realistic", "concept-art", "flat-design"],
  "doc_types": ["character_sheet", "environment", "color_palette", "props", "compositions"],
  "output_comfyui_json": true,
  "model_target": "flux2-klein | wan | hunyuanvideo | sdxl"
}
```

## Integration with digital-stud
- `PROMPTS_COMFYUI.json` feeds directly into ComfyUI batch workflows
- Character sheets feed Any-Pose + ControlNet Union Pro 2.0 (Pose + Depth)
- Environment docs feed FLUX.2 Kontext for consistent world-building
- Color palettes enforce visual consistency across Cinematic Shorts episodes

---
*IdeaForge Custom Workflow — Concept Art Design Document*
