---
name: cinematic-image-prompt-builder
description: Convert rough image ideas into structured Chinese cinematic image-generation prompts. Use when the user wants prompt help for image generation, visual concept design, cinematic scenes, portraits, architecture, creatures, products, game/worldbuilding concepts, story keyframes, or a reusable prompt workflow/skill for tools such as Midjourney, 即梦, 豆包, 可灵, 通义万相, or ChatGPT Image.
---

# Cinematic Image Prompt Builder

## Purpose

Turn a user's rough visual idea into a complete, positive, copy-ready Chinese image-generation prompt. Optimize for single-image generation while keeping the image suitable as a first asset for later image-to-video work.

## Core Workflow

1. Extract the user's subject, scene, purpose, mood, visual style, required elements, and preferred aspect ratio.
2. Identify the image task type:
   - 宏大场景型: large-scale scenes, war, disaster, giants, cities, mythic or sci-fi spaces.
   - 人物主体型: portraits, characters, costumes, professions, emotional figures.
   - 空间建筑型: architecture, interiors, streets, ruins, bases, commercial spaces.
   - 生物怪物型: creatures, monsters, beasts, animals, ecological designs.
   - 产品商业型: product images, packaging, brand visuals, tech products, food and drink.
   - 概念设定型: game concepts, worldbuilding, props, vehicles, costumes, design sheets.
   - 叙事瞬间型: film stills, story illustrations, key events, action beats, interactions.
3. If critical details are missing, ask at most 3-6 concise questions. If the user wants immediate output, make sensible defaults and say they can refine it later.
4. Build the prompt with the universal structure from `references/templates.md`.
5. Load only the needed reference:
   - Use `references/templates.md` when choosing a main or branch template.
   - Use `references/vocabulary.md` when filling camera angle, shot size, composition, lighting, color, material, or texture terms.
   - Use `references/examples.md` when the user asks for examples, teaching, or a case breakdown.
6. Prefer positive visual targets over negative prompts.
7. Output a complete Chinese prompt the user can copy directly into an image model.

## Positive Prompting Rule

Do not center the output on what the user does not want. Convert negative requirements into positive visual descriptions:

- 不要过度 CG -> 真实摄影曝光、自然光照、实体材质、克制电影质感。
- 不要背景乱 -> 背景元素克制，主体周围保留清晰呼吸空间。
- 不要廉价 -> 高级商业摄影、精确光线控制、干净构图、明确视觉中心。
- 不要人物畸形 -> 人体比例自然、姿态清楚、手部结构可信。

## Prompt Structure

Use this field order unless the user's task clearly needs fewer sections:

```text
【画面目标】
【核心题材】
【画面一句话】
【镜头角度】
【镜头尺寸】
【画幅比例】
【景别】
【构图】
【景深】
【主体一——...】
【核心身份】
【体型/外貌/轮廓】
【材质/纹理】
【动作/状态】
【画面作用】
【主体二——...】
【核心身份】
【外貌/材质/动作】
【画面作用】
【核心机位位置】
【环境/场景】
【天气与氛围】
【前景】
【中景】
【远景】
【背景】
【主光源/方向】
【光线软硬质感】
【辅助光/互动光】
【特效光/气氛光】
【整体色温/基调】
【主色系统】
【色彩饱和体系】
【高光与阴影倾向】
【对比度与质感】
【细节密度】
【最终画面质感】
```

## Question Strategy

Ask only what changes the final picture. Prioritize:

- 主体是谁或是什么？
- 场景在哪里？
- 用途是什么？
- 更偏真实摄影、电影剧照、商业摄影、概念艺术还是游戏原画？
- 横图、竖图还是方图？
- 是否有必须出现的关键元素？

## Output Style

Respond in Chinese by default. Keep the final prompt structured and directly usable. Add short teaching notes only when the user asks to learn the camera, lighting, or composition language.
