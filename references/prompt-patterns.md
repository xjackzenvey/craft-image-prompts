# Prompt Patterns

## Contents

- Diagnostic map
- Reusable templates
- Controlled variants
- Worked examples
- Source basis

## Diagnostic Map

| Symptom | Likely missing control | Repair |
|---|---|---|
| Subject looks generic | Subject | Add silhouette, material, color, clothing, age/condition, or one distinctive feature. |
| Elements float or overlap | Scene | Define ground plane, foreground/middle/background, distances, and occlusion. |
| Pose feels lifeless | Action/state | Describe an in-progress gesture plus gaze, wind, cloth, hair, particles, or object interaction. |
| Scale contrast is weak | Composition | Use shot size, frame occupancy, placement, and a physical reference for scale. |
| “Cinematic” result is random | Camera/lighting | Specify viewpoint, lens feel, key-light direction, softness, contrast, palette, and aspect ratio. |
| Style is inconsistent | Style/material | Choose one primary medium and two or three compatible traits; remove competing labels. |
| Extra people, text, or props appear | Constraints | State exact counts and concise exclusions. |
| Prompt is ignored | Priority/overload | Put must-have facts first, remove repetitions, and reduce competing details. |

## Reusable Templates

### Compact

```text
[aspect ratio]. [shot/composition]. [primary subject with defining traits] [action/state] in [scene and spatial layers]. [camera/viewpoint], [lighting]. [medium/style traits], [palette/texture/mood]. Constraints: [must keep]; exclude [likely failures].
```

### Spatially complex scene

```text
Create [image purpose and ratio]. Focal subject: [identity, appearance, count, scale]. Foreground: [...]. Middle ground: [...]. Background: [...]. Action and interaction: [...]. Composition: [shot size, placement, hierarchy, depth, negative space]. Camera and light: [angle, lens feel, focus, light direction/quality, contrast]. Visual language: [medium, palette, texture, era, mood]. Keep [...]. Do not include [...].
```

### Prompt repair

```text
Preserve: [non-negotiable concept]. Clarify subject: [...]. Establish scene: [...]. Make the moment active: [...]. Control composition: [...]. Define camera and light: [...]. Anchor style: [...]. Add only these constraints: [...].
```

## Controlled Variants

When the user wants options, generate three variants while holding the concept stable:

1. **Composition variant:** Change only shot size, placement, or scale relationship.
2. **Lighting variant:** Change only time, light direction/quality, contrast, or palette.
3. **Medium variant:** Change only rendering medium and surface treatment.

Explicitly state the changed axis. Do not create three unrelated concepts.

## Worked Examples

### Vague fantasy request

Input:

```text
生成一条很酷的中国龙。
```

Improved prompt:

```text
16:9 横幅。超广角远景，一条青黑鳞片的中国龙盘旋在暴雨云层中，漫长身体大部分被翻涌乌云遮住，只让龙首从云隙探出；双眼发出冷白光，雨水沿角与鳞片流下。下方现代城市仅占画面底部，街道上的人群仰头，建筑与龙首形成悬殊尺度对比。低机位仰拍，闪电从侧后方勾出轮廓，冷蓝灰色调，高反差但暗部保留细节，写实奇幻电影质感。不要文字、水印、第二条龙或卡通造型。
```

Why it works: It converts “cool” into scale, concealment, gaze, weather, viewpoint, rim light, palette, and exclusions.

### Product hero image

Input:

```text
做一张高级感的黑色香水广告图。
```

Improved prompt:

```text
4:5 竖版产品主视觉。单只几何切面黑色玻璃香水瓶立于深灰石材台面中央偏下，瓶身边缘有极窄冷白轮廓光，正面标签区域保持干净可替换。背景由黑到炭灰渐变，右后方一束硬质窄光穿过薄雾，在台面形成清晰斜线；瓶底有克制的镜面反射与细微水珠。85mm 商业摄影视感，平视略低机位，主体全清晰，极简、冷峻、精密，黑灰银单色体系。只出现一个瓶子；不生成品牌名、随机文字、花朵或人物。
```

Why it works: “Premium” becomes material, lighting, framing, restraint, palette, and text handling.

## Source Basis

This skill distills the method from the forum post [“如何写好一个生成图像的提示词”](https://linux.sb/topic/13965?p=1&floor=13), accessed 2026-08-20. The source advocates replacing wish-like wording with direct visual instructions and assembling prompts from subject, scene, action, composition, camera, style, and constraints. The workflow, diagnostics, templates, and examples here are newly organized for reusable Codex operation rather than copied from the post.
