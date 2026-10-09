---
name: blackmyth-wukong-transfer
slug: blackmyth-wukong-transfer
displayName: 黑神话实况转绘
version: 1.0.0
summary: "把实拍照片一键转成《黑神话：悟空》游戏截图风格：东方神话山水、古刹石窟、云雾缭绕、紧箍咒与金箍棒，附可复用的转绘提示词模板。"
license: MIT
icon: icon.png
description: "Transform real-world reference photos into Black Myth: Wukong in-game screenshot prompts or generated images with maximum BMW rendering fidelity. Use when the user provides mountain, temple, stone forest, ancient building, misty landscape, forest, waterfall, or travel photos and asks for Black Myth Wukong screenshot transfer, photo-to-mythic-China prompt writing, image-to-image prompts, destined-one and staff elements, or reusable real-photo-to-BMW workflows."
---

# 黑神话实况转绘

Convert real-world reference photos into **Black Myth: Wukong gameplay screenshots**. The priority is **MAXIMUM BMW IN-GAME RENDERING FIDELITY**: dark epic Chinese mythology, misty mountains, ancient temples and grottoes, intricate armor — UE5-grade cinematic game rendering, not generic wuxia, not cartoon.

This is a fan-made, non-commercial workflow for personal learning, research, and prompt testing only. It is not affiliated with, endorsed by, sponsored by, or approved by Game Science, Black Myth: Wukong, or any related rights holders. Do not use outputs for commercial sale, advertising, merchandising, paid services, or uses that imply official authorization.

## Output Mode

- If the user asks for prompts, return the final prompt in one code block unless they ask for explanation.
- If the user asks to generate images, use the available image generation workflow.
- If generating from a reference photo, generate first, then provide the final prompt unless the user asks for image only.
- If both prompt and image are requested, generate first, then provide the prompt.
- Use Chinese for user-facing final prompts, but keep the English rendering-control blocks exactly because they strongly steer image models.

## Reference Analysis

Before writing the prompt, identify only what affects transfer:

- Core subject: mountain, temple, stone forest, ancient building, waterfall, forest path, lake, desert, snow peak.
- Recognizable features to preserve: mountain silhouette, rock formation, building structure, water shape, tree lines.
- Mythic mapping: map the real scene to BMW chapter vibes — 黑风山 (forest temple), 黄风岭 (desert wind), 小西天 (snow temple), 盘丝岭 (spider caves), 花果山 (peach paradise).
- Scene type: journey, temple rest, boss-approach, overlook, meditation.
- Environment: time, weather, mist level.
- UI needs: minimal — health/stamina/gourd flask, or location banner, or no UI.
- Modern elements that must be converted or removed: railings → stone balustrades, signs → stone steles, wires → removed, concrete → aged stone.

Preserve the reference photo's identity. Mythologize it into a Journey-to-the-West moment, not a fantasy poster.

## Planning Workflow

Before filling the final prompt, decide:

1. 场景类型与章节映射：行旅 / 古刹 / 雪山 / 石窟 / 桃源，对应哪一回氛围
2. 环境设定：时间 / 天气 / 云雾浓度（雾是黑神话的灵魂）
3. 角色模式：默认将照片人物转译为天命人式行者（紧箍咒、毛发细节、铠甲布衣，金箍棒在手或在背）；或无角色纯山水
4. 神话元素：石灯笼 / 古刹 / 石窟佛像 / 妖雾 / 桃花 / 雪，按场景点缀
5. UI 需求：极简血条·体力·葫芦 / 地名横幅（如"黑风山"）/ 无 UI
6. 构图：远景 / 中景 / 近景，保持史诗感与东方留白

Do not output this planning checklist unless the user asks. Reflect the decisions in the final prompt.

## Prompt Template

When a reference image is provided, always derive concrete content from the image. Never output placeholders.

Use this order for prompt-only output and image-generation prompts:

```text
Black Myth: Wukong gameplay screenshot - MAXIMUM BMW IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual Black Myth: Wukong UE5 gameplay footage, NOT generic wuxia, NOT cartoon, NOT a fantasy movie poster.

RENDERING STYLE - BMW IN-GAME (CRITICAL):
UE5-grade cinematic game rendering; dark epic Chinese mythology; intricate realistic materials — weathered stone, aged wood, detailed armor; volumetric mist and god rays; dramatic but GAME-DIEGETIC composition; muted earthy palette with gold and ember accents; NO flat illustration, NO bright cartoon colors, NO generic fantasy glow.

SCENE：保留<参考图核心构图、主体、山形、建筑等识别特征>，映射为<章节氛围>；现代元素做神话化转译或移除；画面尺寸比例：9:16，1440x2560
CHARACTER：<默认：照片人物转译为天命人式行者，紧箍咒、铠甲布衣、金箍棒，材质对标黑神话>；<一句话写清动作与气场>
MYTHIC ELEMENTS：<3-7 个场景适配元素，只列名称，如：石灯笼、古刹、石窟、妖雾、残阳、雪>
UI：<按需加入极简血条·体力·葫芦图标 / 地名横幅；或无 UI>；所有可读 UI 使用中文；UI 要像游戏内状态，不要做成海报标题

LIGHTING - BMW GAME ENGINE STYLE:
Dramatic directional light through mist: dawn gold, dusk ember, or cold moonlight; volumetric god rays; deep shadows with warm rim light; mist glowing where light passes; Overall CINEMATIC but grounded, never flat.

COLOR PALETTE - BMW <场景类型>:
Stone/wood: muted greys, aged browns, moss greens
Accents: ember orange, ritual gold, blood red — used sparingly
Sky: overcast ink-wash greys or burning dusk

MATERIALS - BMW GAME SURFACES:
Weathered stone: rough aged texture with moss; Aged wood: dark grain, worn edges; Armor: dark metal with gold trim, battle-worn; Fur/hair: fine detailed strands.

ATMOSPHERE - MYTHIC CHINA:
Layered mist between ridges; floating dust/embers/petals/snow; distant temple bells implied, not shown; ancient stillness with lurking danger.

STRICT SELF-CHECK TARGET:
The final image must pass: dark epic Chinese mythic atmosphere; UE5-grade detailed materials; mist and volumetric light as the soul of the frame; characters read as BMW destined-one travelers, not modern photo people; UI, if any, is minimal game state with Chinese text, never a poster title; reference composition, mountain/landmark relations preserved; no bright cartoon look, no generic wuxia softness, no fantasy-movie gloss.

FINAL EMPHASIS - MUST LOOK LIKE ACTUAL BMW GAMEPLAY:
Dark epic mythology. Weathered detailed materials. Mist and god rays. NOT generic wuxia, NOT cartoon, NOT a fantasy poster.
```

## Required Prompt Fields

Every final prompt must include:

- Scene description: concrete character, action, environment, composition, preserved reference features, and chapter-vibe mapping.
- Character mode: default destined-one traveler, or no character.
- `COLOR PALETTE`: muted earthy tones with ember/gold accents.
- `MATERIALS`: weathered stone, aged wood, battle-worn armor.
- `ATMOSPHERE`: layered mist, floating particles, ancient stillness.
- `STRICT SELF-CHECK TARGET`: a compact pass/fail target that names mythic atmosphere, detailed materials, mist, and reference preservation.
- Opening and final emphasis blocks, unchanged in meaning.

## Style Anchor Rules

Start every image prompt with these two lines:

```text
Black Myth: Wukong gameplay screenshot - MAXIMUM BMW IN-GAME RENDERING FIDELITY.
This must look EXACTLY like actual Black Myth: Wukong UE5 gameplay footage, NOT generic wuxia, NOT cartoon, NOT a fantasy movie poster.
```

Then include `RENDERING STYLE - BMW IN-GAME (CRITICAL)` before scene content. Include `STRICT SELF-CHECK TARGET` before final emphasis. End every prompt with `FINAL EMPHASIS - MUST LOOK LIKE ACTUAL BMW GAMEPLAY`.

Do not scatter extra style essays across the prompt. Rendering control lives in the opening, lighting, color, materials, atmosphere, and final emphasis blocks.

## BMW Rendering Calibration

Default to Black Myth: Wukong gameplay:

- Mist is the soul: layered volumetric mist, god rays through it, glowing particles.
- Palette restrained: ink-wash greys, aged browns, moss greens; ember orange and ritual gold as rare accents.
- Materials hyper-detailed: weathered stone, carved wood, ornate armor, fur strands.
- Architecture: Tang/Song-style temples, stone grottoes, pagodas half-hidden in mist.
- The Destined One: golden headband, fur details, staff on back or in hand, battle-worn armor.
- Mythic creatures, when present, are awe-inspiring, never cute.
- UI minimal: health/stamina bars, gourd flask icon, Chinese location banners.
