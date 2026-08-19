---
name: craft-image-prompts
description: Convert vague visual ideas into precise, controllable image-generation prompts using a director-style structure covering subject, scene, action, composition, camera and lighting, style, and constraints. Use when users ask to write, expand, optimize, diagnose, translate, or create variants of prompts for text-to-image models, or when generated images are random, poorly composed, stylistically inconsistent, or missing requested details.
---

# Craft Image Prompts

Turn wishes into directions. Describe observable visual facts and spatial relationships instead of relying on subjective labels such as “cool,” “cinematic,” or “premium.”

## Workflow

1. Determine whether the user wants only a prompt or also wants the image generated. If generation is requested, prepare the prompt first and then use the available image-generation tool.
2. Preserve every explicit requirement. Infer ordinary details when harmless; ask only about missing choices that would substantially change the result.
3. Translate abstract intent into visible evidence. Replace “mysterious” with concrete cues such as obscured facial features, low-key side lighting, drifting fog, and deep negative space.
4. Build the prompt from the seven control layers below. Omit irrelevant layers; do not pad the prompt with decorative synonyms.
5. Order information by importance and resolve contradictions. State the focal subject and defining composition early.
6. Add constraints that prevent likely failures without creating an indiscriminate negative-prompt list.
7. Return a clean, model-ready prompt in the user's language. Add an English version only when requested or when the named model clearly benefits from it.

## Seven Control Layers

Use this flexible sequence:

`subject + scene + action/state + composition + camera/lighting + style/material + constraints`

- **Subject:** Identify each focal element; specify appearance, material, scale, clothing, color, and distinguishing features only where they matter.
- **Scene:** Establish foreground, middle ground, background, ground plane, weather, time, atmosphere, and spatial relationships.
- **Action/state:** Describe pose, gaze, gesture, interaction, motion, and environmental response. Prefer an active moment over a static inventory.
- **Composition:** Set shot size, subject placement, visual hierarchy, scale contrast, symmetry/asymmetry, leading lines, depth, and negative space.
- **Camera/lighting:** Specify viewpoint, angle, lens feel or focal length when useful, depth of field, light direction, hardness, contrast, color temperature, and shadow detail.
- **Style/material:** Anchor the medium, rendering method, palette, texture, era, genre, and mood. Prefer explainable visual traits over vague quality words.
- **Constraints:** State aspect ratio, exclusions, identity/count requirements, text rules, and any must-not-change details.

Read [references/prompt-patterns.md](references/prompt-patterns.md) when diagnosing a failed prompt, producing multiple controlled variants, or needing reusable templates and examples.

## Composition Before Adjectives

Express relationships through composition rather than labels:

- Replace “the tree is huge and the person is tiny” with “extreme wide shot; the tree canopy fills most of the frame while the lone figure occupies less than five percent near the roots.”
- Replace “make it cinematic” with a specific viewpoint, lens feel, lighting setup, contrast, palette, and frame ratio.
- Replace “beautiful” with concrete form, color, texture, light, and atmosphere choices.

Use measurable or relational language when exact numbers would be artificial: foreground/background, centered/off-center, dominant/subordinate, dense/sparse, sharp/soft, warm/cool.

## Output Contract

For a new prompt, return:

1. **Final prompt:** One coherent block ready to paste into an image model.
2. **Negative constraints:** Include only when the target model supports them or the exclusions are important.
3. **Optional assumptions:** Mention only consequential details inferred from an underspecified request.

For prompt optimization, additionally provide a short diagnosis of the largest control gaps. Preserve the user's concept instead of silently redesigning it.

For variants, change one major axis at a time—such as composition, lighting, or medium—and label that axis. Keep all other requirements stable so results are comparable.

## Quality Check

Before returning, verify:

- Every requested subject is present with an unambiguous count and relationship.
- The frame has a clear focal point and spatial hierarchy.
- The action, composition, camera, and lighting do not conflict.
- Abstract mood words are supported by visible cues.
- Style descriptors are mutually compatible and useful.
- Constraints cover likely unwanted text, watermark, extra subjects, anatomy, or cropping only when relevant.
- The prompt is specific but not overloaded; remove repeated quality boosters and low-value adjective chains.

## Source Attribution

This skill distills and extends the prompting framework from [“如何写好一个生成图像的提示词”](https://linux.sb/topic/13965?p=1&floor=13). See [references/prompt-patterns.md](references/prompt-patterns.md) for the detailed source note.
