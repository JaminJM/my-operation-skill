# Content Package Specification

Use this reference for full Hong Kong study-abroad content packages.

## Full Output Order

1. 选题判断
2. 内容参考与事实依据
3. 公众号文章
4. 图片规划
5. 图片 Prompt
6. 小红书版本
7. 小红书图片规划与图片 Prompt
8. 短视频脚本
9. 发布前检查
10. 文件归档

If the user asks only for one part, output only that part.

## File Output Structure

Separate topic planning from content production:

- Topic planning, topic recommendations, and unused ideas belong in `topic-bank/香港留学选题库.md`.
- `context/` is only for topics that have entered content production.

When generating actual content assets in a local workspace, save outputs under:

```text
context/<选题名称>/
```

Use separate Markdown files for final content and prompts:

```text
context/香港受养人签证攻略/
├── 01-公众号文章.md
├── 02-公众号图片规划.md
├── 03-公众号图片prompts.md
├── 04-小红书文案.md
├── 05-小红书图片规划.md
├── 06-小红书图片prompts.md
├── 07-短视频脚本.md
├── 08-发布前检查.md
└── sources.md
```

Rules:

- Do not create a `context/` folder for topic planning alone.
- Before creating a new `context/` folder, check for an existing exact or similar topic folder.
- Create only files that match generated deliverables.
- Keep publishable copy separate from image prompts.
- Put official links, source notes, and research timestamps in `sources.md`.
- Do not overwrite existing files silently; use `-v2` or ask before replacing.
- Update `topic-bank/香港留学选题库.md` when a topic finishes production. Use only `未开始` and `已完成` statuses.
- After saving, report the created file paths to the user.

## WeChat Article Template

This is not a fixed article skeleton. Adapt structure to the topic and content pattern research.

```markdown
# 标题

## 标题参考

- 标题方案 A
- 标题方案 B
- 标题方案 C

正文从这里开始。根据选题选择最合适的结构，不强制使用“导语/先说结论/常见误区/行动建议”。
```

## WeChat Structure Rules

Do:

- Choose a structure based on topic type, public content references, and reader state.
- Keep normal articles around 1,200-1,800 Chinese characters unless the user asks for depth.
- Treat 1,200-1,800 as a density target, not a padding target. The article should feel publishable on its own, not like a slide outline.
- Use 3-5 major sections for most articles.
- Use short paragraphs and strong subheadings.
- Use unnumbered title options so the user can delete or select them easily.
- Move dense details into images when visual explanation is easier than prose, while keeping the article's narrative and judgment complete.

Do not:

- Reuse the same fixed structure for every article.
- Number title options.
- Create ten numbered major sections unless explicitly requested.
- Put "信息更新时间" in publishable article copy.
- Force sections called "导语", "先说结论", "常见误区", or "行动建议" into every article.
- Over-correct into an article that is too thin after shortening.

Recommended structure patterns:

- Scene-first: a common reader situation -> why it matters -> how to decide.
- Decision cards: 3-5 cards that help the reader judge fit.
- Contrast: two choices or two misconceptions side by side.
- Q&A: direct answers to real reader questions.
- Timeline: before application, during study, after graduation.
- Visual-led: short article plus strong explanatory images.

Minimum substance check:

- Each major section should contain one real judgment, example, scenario, or decision criterion.
- If the article is below about 1,100 Chinese characters, check whether it still has enough reader value.
- Images can carry tables and checklists, but the article should still be readable without opening every image.
- Shorten by deleting filler, not by deleting useful examples or tradeoffs.

## Content Reference Notes Template

Put this in `sources.md` when full-package or writing workflows use web research:

```markdown
## 内容参考观察

- 参考渠道：
- 高表现内容常见切入：
- 重复出现的读者问题：
- 可以借鉴的结构：
- 需要避免的套路：
- 本篇采用的结构：
- 适合放进图片的信息：
```

Do not copy source wording. Use this section to document observed structure and reader demand.

## Image Plan Template

```markdown
| 序号 | 放置位置 | 图片类型 | 作用 | 核心内容 | 比例 | 备注 |
|---|---|---|---|---|---|---|
| 1 | 公众号推文封面 | 封面信息图 | 建立主题识别 | ... | 2.35:1 | 公众号封面固定比例，不使用小红书比例 |
| 2 | 文章中第一个需要解释的部分 | 信息图/流程图/对比图/清单图 | 解释正文信息 | ... | 16:9 | 除封面外，公众号正文图片统一 16:9 |
| N | 全文概括海报（备用，不放入公众号正文） | 竖版总结海报 | 概括全文，便于后续生成海报 | ... | 9:16 | 必须提供，但不插入公众号正文 |
```

Use these image type mappings:

- 流程步骤 -> 流程图
- 时间节点 -> 时间轴
- 材料/条件 -> 清单式信息图
- 多方案选择 -> 对比表
- 风险提醒 -> 避坑卡片
- 数据/趋势 -> 图表式信息图

WeChat image ratio rules:

- 公众号推文封面 must be `2.35:1` exactly. Suggested canvas examples: `900x383 px`, `1175x500 px`, or `2350x1000 px`.
- All WeChat in-article images except the cover must be `16:9`.
- Always include one full-article summary poster prompt with ratio `9:16`; mark it as `全文概括海报（备用，不放入公众号正文）`.
- Never reuse Xiaohongshu carousel ratios for the WeChat cover.
- The ratio in the image plan must match the ratio written inside the corresponding AI image prompt.

WeChat image order rules:

- Write the image plan after the final article structure is decided.
- If dense content can be explained better visually, design the image plan before over-expanding article prose.
- Put the WeChat cover first.
- List all in-article images in the same order as their placement sections appear in the article.
- Put the full-article summary poster last because it is not inserted into the article.
- The prompt document must follow the exact same numbering, image names, and order as the image plan.
- If the article section order is `误区` before `时间线`, then the image plan and prompt file must also put the `误区` image before the `时间线` image.

General image prompt order rule:

- For every platform, the prompt document must follow its image planning document exactly: same numbering, same image names, same sequence, same ratios.

Visual-first rules:

- Images may carry detailed explanations, not just titles.
- A concise article plus one strong explanatory image is acceptable.
- A thin article plus many detailed images is not acceptable for WeChat; keep enough substance in the text.
- Prefer decision trees, comparison tables, checklists, and timelines for heavy information.
- Do not make the article long just because image prompts are also required.

## Image Prompt Template

For each image, output:

```markdown
### 图 1：图片名称

用途：
位置：
比例：
是否包含文字：

Prompt:
[English prompt preferred for visual generation, but include the exact Chinese title and short Chinese copy that should appear inside the image. Must include the exact aspect ratio, image role, core message, layout structure, number of panels/cards/steps if any, visual elements, icon meanings, style, color system, lighting/composition, Chinese text rendering instructions, and negative instructions. If the plan says the image explains four mistakes, the English prompt must name all four mistakes and include their Chinese labels.]

中文设计备注：
[List the exact Chinese text used in the image so the human can check or edit it later in Canva/Figma/PS.]
```

Recommended visual style:

- Clean editorial infographic for Chinese education content.
- Modern Hong Kong study-abroad advisory brand.
- Choose a background and color system that fits the topic and platform; do not force a white background.
- Keep all images in the same article package visually unified: same illustration style, color system, icon language, and layout logic.
- Minimal line icons, subtle map or skyline references only when useful.
- No cartoonish characters unless requested.
- No fake official logos, no university logos unless user provides permission/assets.

Prompt clarity rules:

- Do not write ambiguous prompts that only describe mood or style.
- Do not put important semantic content only in `中文设计备注`.
- For comparison images, name each side and the exact comparison criteria.
- For timeline images, name every milestone in the prompt.
- For checklist images, name every checklist category in the prompt.
- For myth-busting or risk-warning images, name every misconception or risk in the prompt.
- Default to asking the image model to render Chinese titles and short Chinese copy directly inside the image.
- Keep Chinese copy concise enough for image generation: title, section labels, step names, short bullets, and caution notes.
- Only ask for text placeholders when the user explicitly requests a no-text image, blank template, or editable layout.
- Always repeat the exact Chinese text in `中文设计备注` so the user can check and revise it later.
- For the full-article summary poster, include `aspect ratio 9:16 vertical poster` in the English prompt and summarize the article's main conclusion, key sections, and final action advice.

## Xiaohongshu Conversion Template

```markdown
## 小红书标题

- ...
- ...
- ...

## 小红书正文

开头钩子：...

正文：
- ...
- ...

结尾互动：...

## 标签

#香港留学 #香港申请 ...
```

## 小红书图片规划

```markdown
| 序号 | 图片角色 | 图片类型 | 核心信息 | 建议比例 | 备注 |
|---|---|---|---|---|---|
| 1 | 封面 | 标题封面/主题视觉 | ... | 3:4 或 1:1 | 负责吸引点击 |
```

小红书图片规则：

- 根据内容判断图片数量，不固定张数。
- 优先考虑轮播阅读逻辑：封面、核心结论、流程/清单、对比、误区、行动建议。
- 每张图都要有明确保存价值，不要为了凑图而加图。
- 小红书图片可以和公众号图片不同，但同一篇小红书笔记内必须统一风格。
- 小红书每张图的建议比例必须写入对应英文 prompt，例如 `aspect ratio 3:4 vertical Xiaohongshu carousel image`。

## 小红书图片 Prompt

For each Xiaohongshu image, output:

```markdown
### 小红书图 1：图片名称

图片角色：
比例：
核心信息：
是否包含文字：

Prompt:
[Prompt for an AI-generated Xiaohongshu-style image or infographic. Must include the exact aspect ratio, image role, core message, layout structure, number of cards/steps if any, visual elements, icon meanings, style, color system, exact Chinese text to render, and negative instructions. Keep style consistent across the carousel. Do not put important meaning only in the Chinese design notes.]

中文设计备注：
[Repeat the exact Chinese title and bullet text used in the image for later human checking or editing.]
```

Xiaohongshu tone:

- More direct and personal than WeChat.
- Use short lines.
- Keep factual caution.
- Avoid fake personal experience if none was provided.
- Prefer saveable images over long explanatory paragraphs when the point is checklist-like, comparative, or procedural.
- Do not make every Xiaohongshu note follow the same hook/body/ending pattern if the topic needs a different rhythm.

## Short Video Template

```markdown
## 短视频标题

1. ...
2. ...

## 60 秒脚本

| 时间 | 画面 | 口播 | 屏幕文字 |
|---|---|---|---|
| 0-3s | ... | ... | ... |
```

Short video rules:

- Put the main pain point in the first 3 seconds.
- Make one video cover one core question.
- Use spoken Chinese, not article paragraphs.
- Add factual caveats briefly, without breaking rhythm.

## Publication Check Template

```markdown
## 发布前检查

- 内容参考：
- 最新性：
- 官方来源：
- 高风险表述：
- 营销味：
- 公众号阅读体验：
- 结构重复风险：
- 文章长度：
- 标题选项：
- 图片必要性：
- 图片比例：
- 图片顺序：
- 图片 Prompt 清晰度：
- 仍需人工确认：
```

High-risk claims to soften or verify:

- "一定能获批"
- "保证录取"
- "最快 X 天办好" when not officially guaranteed
- "所有学生都适用"
- "无需任何材料"
- "官方已经明确" without official source
