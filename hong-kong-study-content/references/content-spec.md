# Content Package Specification

## Table of Contents

- Full Output Order
- File Output Structure
- WeChat Article Template
- WeChat Structure Rules
- Content Reference Notes Template
- Image Plan Template
- Image Prompt Template
- Xiaohongshu Conversion Template
- Xiaohongshu Image Planning
- Xiaohongshu Visual Diversity System
- Xiaohongshu Image Prompt
- Short Video Template
- Publication Check Template

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

If the operation judgment or final strategy recommends splitting the WeChat article into multiple Xiaohongshu posts, create a compact split execution package when the user confirms the split route:

```text
小红书拆分执行包/
├── 01-小红书拆分执行总稿.md
└── 02-小红书拆分图片prompts合集.md
```

If the user gives a topic/title without limiting language, produce the full package. If the user asks for a platform only, output that platform's complete asset set, not just copy. "只要公众号" includes `01-公众号文章.md`, `02-公众号图片规划.md`, `03-公众号图片prompts.md`, and `08-发布前检查.md`. "只要小红书" includes `04-小红书文案.md`, `05-小红书图片规划.md`, and `06-小红书图片prompts.md`. Output only one file when the user explicitly names one file/output or excludes images, such as "只要正文", "只要文案", "不要图片", or "不用配图".

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
├── 00-选题运营判断.md
├── 01-公众号文章.md
├── 02-公众号图片规划.md
├── 03-公众号图片prompts.md
├── 04-小红书文案.md
├── 05-小红书图片规划.md
├── 06-小红书图片prompts.md
├── 07-短视频脚本.md
├── 08-发布前检查.md
├── 小红书拆分执行包/
└── sources.md
```

Rules:

- Do not create a `context/` folder for topic planning alone.
- For full content packages from a topic/title, include `00-选题运营判断.md` before drafting the publishable files.
- For platform-only requests, create the full platform package: copy plus image planning and image prompts.
- For true single-file requests, create only the named file.
- If Xiaohongshu拆分 is confirmed, prefer a compact split execution package with one execution draft file and one consolidated prompt file. Do not create one separate file per split post unless requested.
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
- 搜索高频词/SEO 词：
- 可以借鉴的结构：
- 需要避免的套路：
- 本篇主受众：
- 本篇采用的结构：
- 适合放进图片的信息：
- 软性转化方式：
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
- Keep the account visually recognizable across posts through typography discipline, information density, restrained icons, and Hong Kong study-abroad subject matter; do not rely on one repeated palette as the only brand signal.
- For Xiaohongshu and multi-post packages, vary color systems and layout families across different posts so the profile grid does not look like one template repeated.
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
- 不要把每篇都做成固定三张：封面 + 表格/任务卡 + 官方截图。这个结构只能在内容确实需要时使用。
- 按内容任务决定轮播长度：观点/争议类可 1-2 张，清单/对比类常用 3-5 张，流程/时间线/预算/申请规划类可 5-7 张。少图但有点击力，比硬凑图更好。
- 轮播角色按需选择：封面、核心判断、流程、清单、对比、误区、案例、决策卡、时间线、预算表、行动卡、官方依据。不是每篇都要覆盖所有角色。
- 官方截图不是固定第 3 张。只有政策、费用、排名、签证、项目要求等需要增强信任时才加入；如果截图本身不好读，把官方链接放正文、评论引导或 `sources.md`，不要为了统一格式硬放图。
- 图片规划必须写明“建议图片数”和原因，尤其说明为什么不是固定三张。
- 每张图都要有明确保存价值，不要为了凑图而加图。
- 小红书图片可以和公众号图片不同，但同一篇小红书笔记内必须统一风格。
- 单篇轮播内部要统一；不同小红书笔记之间要有可见差异。不要让连续多篇都使用同一套暖白底、深蓝/深绿标题、金色/港铁红点缀。
- 生成小红书图片规划或 prompt 时，必须先写出本篇的「视觉家族」：色彩方向、版式方向、图形语言、与近期内容的差异点。
- 多篇合集或拆分包中，每篇都要分配不同的视觉家族；最多只能保留一个共同品牌锚点，例如字体气质、信息图密度、细线图标、页脚小标签，不能把主色、背景色、卡片样式也全部固定。
- 小红书每张图的建议比例必须写入对应英文 prompt，例如 `aspect ratio 3:4 vertical Xiaohongshu carousel image`。

小红书正文与链接规则：

- 如果图片规划、素材清单或 `sources.md` 列出了官方链接，正文里也要出现对应的官网核对句或 Markdown 链接，不能只把链接放在素材区。
- 小红书正文要根据选题选择结构，不要批量复用同一套 "开头问题 -> 列点 -> 总结 -> 评论区 CTA"。同一批内容里应混合使用场景切入、误区切入、判断卡、对比、时间线、预算拆解、官方依据提醒、评论互动等结构。
- 小红书标题、开头、封面文字、正文和标签应自然植入 2-5 个搜索词；不堆词，不牺牲口语感。
- 每篇只使用一个柔和咨询引导，不要每篇都用同一句评论区 CTA。

## Xiaohongshu Visual Diversity System

Use this system whenever creating Xiaohongshu image plans, prompts, split execution packages, or batches of posts.

Brand commonality should come from:

- Clear Chinese editorial typography.
- High information density but not crowded.
- Real advisory judgment, not decorative mood boards.
- Restrained icon style and clean hierarchy.
- Hong Kong study-abroad context shown through useful symbols only: timeline, checklist, map contour, skyline, application folder, visa/work path, budget sheet, decision matrix.

Post-to-post variety should come from:

- Different color families.
- Different cover composition.
- Different information layout.
- Different visual metaphor matched to the topic.
- Different emphasis mood: assessment, warning, route, budget, family, decision, timeline, comparison.

Recommended visual families to rotate:

| Visual family | Suitable topics | Color direction | Layout direction |
|---|---|---|---|
| Assessment sheet | 背景评估、低 GPA、选校定位 | mist blue + charcoal + soft lime accent | form sheet, scoring grid, diagnostic cards |
| Policy pathway | IANG、签证、身份、流程 | teal green + porcelain white + restrained red | route map, timeline, document flow |
| Warning memo | 避坑、误区、申请风险 | muted coral + graphite + pale gray | memo board, warning strips, mistake/fix pairs |
| Budget ledger | 学费、生活费、奖学金、成本回报 | muted amber + ink gray + off-white | ledger table, receipt cards, calculator blocks |
| Decision board | 一年制值不值、适合谁、去不去香港 | lavender gray + deep plum + cream | decision cards, pros/cons board, fit matrix |
| Application calendar | 申请季、时间线、deadline | steel blue + fresh green + white | calendar grid, milestone timeline, progress tracker |
| Family planning | 家长、受养人、陪读、家庭预算 | warm clay + sage green + ivory | family plan map, condition checklist, household cards |
| Comparison desk | 港校/英澳/新加坡、专业选择 | black ink + sky blue + light sand | split-screen comparison, matrix, side-by-side cards |
| Evidence file | 官方信息、材料清单、申请文件 | slate gray + paper white + tab colors | folder tabs, document stack, checklist file |
| Career map | 留港就业、IANG 后续、行业路径 | petrol blue + mint + signal orange | career path map, subway-line path, milestone cards |

Rules:

- Choose one visual family per Xiaohongshu note and state it before the prompts.
- Within one carousel, keep the chosen visual family consistent.
- Across a batch, do not repeat the same visual family or same dominant palette in adjacent posts unless the user explicitly asks for a series look.
- Avoid more than two posts in one batch using warm ivory/off-white as the dominant background.
- Avoid making navy/deep green + gold + Hong Kong red the default palette. Use it only when it is the best fit for the topic.
- Layout can repeat occasionally, but if layout repeats, color and visual metaphor should change. If color is similar, layout must change clearly.
- Do not make the profile grid look chaotic: use similar typography weight, clean margins, restrained icons, and concise Chinese text as the common system.
- Add negative prompt instructions such as: "do not reuse the same warm ivory navy gold Hong Kong red palette from previous posts; avoid generic template look; avoid identical card grid composition unless specified."

## 小红书图片 Prompt

For each Xiaohongshu image, output:

```markdown
本篇视觉家族：
- 色彩方向：
- 版式方向：
- 图形语言：
- 与近期内容的差异点：

本篇图文策略：
- 主受众：
- 结构节奏：
- 建议图片数及原因：
- 搜索词植入：
- 软性转化 cue：

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
- 小红书主页视觉多样性：
- 受众匹配：
- SEO 埋词：
- 软性转化：
- 官方链接是否进入正文：
- 是否避免固定三图模板：
- 仍需人工确认：
```

High-risk claims to soften or verify:

- "一定能获批"
- "保证录取"
- "最快 X 天办好" when not officially guaranteed
- "所有学生都适用"
- "无需任何材料"
- "官方已经明确" without official source
