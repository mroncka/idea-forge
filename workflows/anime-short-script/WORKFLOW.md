# Workflow: Anime Short Script

Generate a complete structured script for a 3–7 minute anime short.

## Purpose
From a high-level premise or theme, produce a production-ready anime script with scene breakdown, character beats, dialogue, and visual direction notes — formatted for direct use with digital-stud Cinematic Shorts pipeline.

## Output Structure
```
/script/
  SCRIPT.md          — full formatted script
  CHARACTERS.md      — character sheets
  SCENE_BREAKDOWN.md — scene-by-scene director notes
  PROMPTS.md         — image/video generation prompts per scene
```

## Steps

### 1. Premise Expansion
Input: 1–3 sentence premise
Output:
- Genre + tone (shonen action / slice-of-life / cyberpunk / psychological)
- Logline (25 words)
- Emotional arc (setup → conflict → resolution)
- Target length (3 / 5 / 7 min) and scene count

### 2. Character Design Brief
For each character (max 4 for a short):
- Name, archetype, visual description (hair, eyes, outfit, distinguishing features)
- Voice/personality in 3 words
- Role in story (protagonist / antagonist / foil / guide)
- ComfyUI character consistency notes

### 3. Scene Breakdown
For each scene:
- INT/EXT, location, time of day
- Shot type recommendation (wide establishing / medium two-shot / close-up reaction)
- Action line (2–3 sentences)
- Emotional beat
- Estimated duration (seconds)

### 4. Dialogue
- Full dialogue per scene in screenplay format
- Subtext notes for voice acting / expression direction
- Japanese honorifics / speech pattern notes (optional)

### 5. Image Generation Prompts
Per scene, generate:
- Background/environment prompt (for FLUX.2 / Wan)
- Character pose prompt (feeds into digital-stud Any-Pose workflow)
- Key frame prompt (the single defining image of the scene)
- Style tags: `anime, cel-shaded, [studio style], cinematic lighting`

## Config
```json
{
  "workflow": "anime-short-script",
  "premise": "...",
  "genre": "action | slice-of-life | cyberpunk | psychological | fantasy",
  "target_length_min": 5,
  "art_style": "studio-ghibli | trigger | ufotable | bones | original",
  "output_comfyui_prompts": true,
  "n_characters": 2
}
```

## Integration with digital-stud
The `PROMPTS.md` output maps directly into:
- ComfyUI FLUX.2 Klein workflows (character consistency via LoRA)
- Wan/HunyuanVideo I2V for motion segments
- ElevenLabs TTS for dialogue audio
- Remotion for final assembly

---
*IdeaForge Custom Workflow — Anime Short Script*
