---
name: style-fusion-prompter
description: 跨媒介“角色视觉语言 × 场景视觉语言”双风格共存融合提示词生成技能。支持融合两套不同手绘风格编号（#001–#279），或融合手绘风格编号与写实风格，并可按需注入图型（122种）与主题色（36种），严格输出造型解耦、物理光影与叙事共存的高质量生图提示词。
---

# Style Fusion Prompter (跨媒介风格融合提示词生成器)

专注生成**“角色视觉语言 × 场景视觉语言”**共存的高张力、跨媒介双风格融合提示词。坚决反对平庸折中，确保角色与场景两套视觉语言独立鲜明，同时在物理空间、光影、接触与叙事上高度统一。

---

## 核心设计哲学

1. **双语言独立共存，拒绝平庸磨平**：
   - 画面中必须同时存在两套清晰可辨的视觉媒介质感；
   - 角色部分忠实遵循【角色视觉语言】的造型、线条、材质与媒介感；
   - 场景部分忠实遵循【场景视觉语言】的透视、光影、肌理与环境感；
   - 严禁把两者平均磨成普通的混合风格插画，严禁互相完全同化。

2. **物理逻辑统一，拒绝贴纸拼贴**：
   - 两种视觉语言保持鲜明反差，但共享**同一个物理世界**：统一的光源方位、色温、天气、环境反射、空气透视；
   - 角色与场景之间必须具备真实可信的物理接触、站立重心、受力传导、前后遮挡与投射阴影；
   - 绝非“把一个角色贴图贴在另一个风格的背景上”，而是角色真正生活在这个场景之中。

3. **叙事瞬间明确，动作逻辑严谨**：
   - 画面必须围绕【主题】形成清晰的叙事时刻，优先保障“谁、在哪里、正在做什么”一目了然；
   - 若存在跑、跳、拉、推、攀爬等动作，重心的支撑与发力方向必须符合物理常识，动作逻辑优于单纯夸张。

---

## 输入规范与风格解析

### 1. 输入维度
用户可提供以下信息（支持自由组合）：
- **角色风格**：全库手绘风格编号（`#001`–`#279`）或指定写实风格（如“写实摄影”、“电影级实拍”）；
- **场景风格**：全库手绘风格编号（`#001`–`#279`）或指定写实风格（如“超写实雨夜都市摄影”、“自然纪实摄影”）；
- **主题**：画面具体叙事事件、人物身份与动态；
- **情绪 / 氛围**：画面的情感基调（如“孤独而温暖”、“荒诞幽默”、“史诗史诗感”、“静谧治愈”）；
- **（可选）图型**：122 种图型版式编号（`SC-001`–`SC-090`, `IG-001`–`IG-032`）；
- **（可选）主题色**：36 种经典主题色编号（`C-01`–`C-36`）；
- **（可选）画幅比例**：默认 `3:4`，或按需指定（如 `16:9`、`9:16`、`1:1`、`5:2`、`2.35:1`）。

### 2. 智能推荐策略（未指定时）
- **若用户仅给出主题**：由 AI 结合主题语义，在全库 279 种手绘风格与写实风格中**主动推荐一组最具反差美感与张力的【角色风格 × 场景风格】配对**（例如：极简扁平漫画角色 × 电影级超写实废墟，或水墨写意人物 × 包豪斯几何空间），并推荐 1 款主题色，给出具象化推荐理由后直接输出完整提示词。
- **若用户仅指定角色风格**：保留角色风格，AI 结合主题推荐最具戏剧反差的场景风格。
- **若用户仅指定场景风格**：保留场景风格，AI 结合主题推荐最具契合度的角色风格。

---

## 标准提示词输出模板

### 中文标准提示词

```text
生成一幅“角色视觉语言 × 场景视觉语言”共存的跨媒介融合画面。
- 【角色视觉语言】：{角色风格编号与名称，附带造型、线条与材质特征，例如：#018 Minimal Deadpan Dialogue Cartoon，极简黑白线条、死鱼眼表情与极度扁平的简笔造型}
- 【场景视觉语言】：{场景风格编号与名称或写实风格，附带环境特征，例如：超写实电影感摄影 / #268 工笔画细腻矿物设色山水}
- 【主题】：{画面具体事件、人物与动作描述}
- 【情绪】：{核心情绪与空间氛围}
[- 【图型】：{可选图型编号与排版特征，若无则省略本行}]
[- 【主题色】：{可选主题色编号与名称，若无则省略本行}]
[- 【画幅比例】：{画幅比例，默认 3:4}]

画面中必须同时存在两套清晰可辨的视觉语言。
不要把两者平均磨成普通的混合风格插画。
角色部分使用【角色视觉语言】表现，场景部分使用【场景视觉语言】表现。这里的“场景”包括环境空间、地形、建筑、植物、天空、水面、天气、地面、道具以及整体空间氛围。
【角色视觉语言】与【场景视觉语言】都必须忠实保留各自的核心特征，包括但不限于：造型逻辑、比例系统、线条方式、笔触特征、体块组织、几何倾向、材质表达、表面肌理、色彩体系、明暗方式、细节密度、空间处理方式、平面化或立体化程度以及各自独有的媒介感。不要额外强行加入与原风格无关的统一化修饰。
两种视觉语言必须保持明显差异，但共享同一个空间、光源、色温、天气、空气、构图和叙事时刻。
视觉统一应通过遮挡关系、接触关系、投影关系、地面关系、前后空间关系、局部反光、环境综合色和空气透视来完成，而不是把两种视觉语言磨成同一种质感。
角色必须真正存在于场景中，与场景形成自然互动，不能像贴纸一样浮在画面上。角色与场景之间需要有清楚可信的接触、站立、受光、投影、遮挡和空间关系。重点不是“一个角色站在另一个风格的背景前”，而是让角色真正进入并生活在这个场景世界中。
画面必须围绕【主题】形成一个明确的叙事瞬间，优先保证“谁、在哪里、正在做什么”清楚可读。不要为了展示风格而加入大量与主题无关的装饰元素。
如果画面中存在明显动作，如跑、跳、扑、拉、推、攀爬、追逐、搏斗、搬运或其他动态行为，需要保证发力点、重心、支撑关系、接触位置、受力方向、物体运动方向、遮挡和透视合理，动作逻辑优先于单纯夸张效果。
不要生硬拼贴，不要左右分栏，不要上下分区，不要贴纸叠加，不要主体悬浮，不要错误遮挡，不要不同光源互相冲突，不要让角色风格被完全同化成场景风格，也不要让场景风格被完全同化成角色风格。
最终效果应呈现：
- 两种不同视觉语言自然存在于同一个世界中
- 角色风格与场景风格差异清晰
- 空间与光线逻辑统一
- 角色与场景互动自然
- 主题事件明确可读
```

### English Standard Prompt

```text
Generate a cross-media fusion artwork where "Character Visual Language × Scene Visual Language" coexist.
- [Character Visual Language]: {Character style name and core traits, e.g., #018 Minimal Deadpan Dialogue Cartoon, minimalist black and white linework and deadpan cartoon anatomy}
- [Scene Visual Language]: {Scene style name and core traits, e.g., Ultra-realistic cinematic photography / #268 Gongbi fine-brush mineral color landscape}
- [Theme]: {Concrete theme description, characters, and actions}
- [Mood]: {Core emotional mood and spatial atmosphere}
[- [Layout]: {Layout ID and description, omit if none}]
[- [Theme Color]: {Theme color ID and name, omit if none}]
[- [Aspect Ratio]: {Aspect ratio, default 3:4}]

Two clearly distinguishable visual languages must coexist in the image simultaneously.
Do NOT average or blend the two into a generic hybrid illustration.
The character elements must be rendered strictly in [Character Visual Language], while the scene elements must be rendered strictly in [Scene Visual Language]. Here, "scene" includes environmental space, terrain, architecture, vegetation, sky, water, weather, ground, props, and overall spatial ambiance.
Both [Character Visual Language] and [Scene Visual Language] must faithfully retain their respective core characteristics, including but not limited to: modeling logic, proportional systems, linework methods, brushstroke traits, volume organization, geometric tendencies, material expressions, surface textures, color systems, shading/lighting techniques, detail density, spatial treatment, degree of flatness vs. three-dimensionality, and their distinct tactile media sensations. Do NOT artificially force any uniform stylistic modifications irrelevant to each original style.
The two visual languages must maintain noticeable contrast, yet share the exact same space, light source, color temperature, weather, atmosphere, composition, and narrative moment.
Visual unity must be achieved through occlusions, physical contact, contact shadows, ground contact, fore/background depth, subtle bounce light, environmental ambient color, and aerial perspective, rather than blending the two visual languages into an identical material texture.
The character must truly exist and naturally interact within the scene world, rather than floating like a detached sticker. There must be credible physical contact, grounded posture, lighting, cast shadows, occlusions, and depth relationships between the character and the environment. The focus is NOT "a character simply standing in front of a different-styled background", but rather having the character truly inhabit and live within this environment.
The image must center around [Theme] to form a distinct narrative moment, prioritizing clarity of "who, where, and what they are doing". Do NOT introduce clutter or irrelevant decorative elements merely to exhibit the styles.
If dynamic actions are present (e.g., running, jumping, leaping, pulling, pushing, climbing, chasing, wrestling, carrying, or dynamic movements), ensure the center of gravity, support points, contact points, force vectors, motion trajectory, occlusion, and perspective are physically convincing; dynamic logic takes priority over superficial exaggeration.
Do NOT create awkward collages, do NOT split left-right or top-bottom columns, do NOT layer like stickers, do NOT let subjects float, avoid erroneous occlusions and conflicting light sources, do NOT assimilate the character style into the scene style, and do NOT assimilate the scene style into the character style.
The final result should achieve:
- Two distinct visual languages coexisting harmoniously in the same world
- Clear differentiation between character style and scene style
- Unified spatial, perspective, and lighting logic
- Natural, believable physical interaction between character and scene
- Clear, legible thematic narrative event
```

---

## 交付与后续操作引导 (CTA)

每次输出双语风格融合提示词后，主动附带极简双轨引导：

```markdown
---

💡 **风格融合设计方案已就绪！您可以选择：**
1. **【方式 A · 自主生图】**：复制上方提示词，粘贴至您喜爱的生图工具（如 GPT Image 2/2.5、Midjourney、Stable Diffusion 等）直接出图；
2. **【方式 B · 全自动生图】**：直接对我说 **“全自动出图”**，我将调用生图工具为您全自动生成风格融合画面！
```
