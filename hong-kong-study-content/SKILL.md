---
name: hong-kong-study-content
description: Hong Kong study-abroad content routing and production skill for Chinese education operators. Use when the user asks to judge, plan, research, write, adapt, optimize, review data, make monthly plans, update old content, create image plans/prompts, draft short-video scripts, or archive content for Hong Kong study-abroad operations.
---

# Hong Kong Study Content Production Skill

Use this skill for Hong Kong study-abroad content operations. The job is to infer the user's real deliverable, choose the smallest suitable workflow, and finish the work with minimum repeated clarification.

## Core Principles

- Accuracy before marketing.
- Reader comfort before word count.
- Official information before assumptions.
- Practical guidance before promotional language.
- Do not create anxiety, guaranteed outcomes, or fake urgency.
- Do not reuse the same article or Xiaohongshu structure for every topic.
- Use images as information products, not decoration.

## Reference Files

Read only the reference needed for the selected route:

- `references/operation-system.md`: topic operation judgment, account-stage fit, data review, monthly planning, and update/republish decisions.
- `references/content-spec.md`: full packages, WeChat and Xiaohongshu output formats, article rules, image plans, image prompts, short video scripts, file naming, and final checks.

If a reference file is unavailable, use the short fallback rules in this file and state the limitation.

## Workspace Rules

Generated files belong in the user's operations workspace, not inside this skill folder.

When filesystem access is available, locate the workspace root by using the current working directory when it contains `context/`, `operations/`, or `topic-bank/`; otherwise use the nearest parent project workspace that contains those folders.

- Content production: save under `context/<topic>/`.
- Topic planning: use `topic-bank/香港留学选题库.md`.
- Data reviews: use `operations/content-reviews/`.
- Monthly plans: use `operations/monthly-plans/`.

Before creating a new content folder, check for exact or similar existing folders. Do not overwrite existing files silently; create a versioned file or ask before replacing.

## Routing

Default to the minimum sufficient workflow. Ask at most one clarification question only when missing information would materially change the output.

| User intent | Signals | Action |
|---|---|---|
| Topic judgment | "值得做吗", "能不能做", "帮我判断" | Read `operation-system.md`; score and recommend doing, adjusting, delaying, or rejecting. |
| Broad topic or bare title | "我想写这篇", "写这篇", "做这个选题", only a title/topic | Run operation judgment first; if suitable or adjusted, continue to a full package. |
| Topic planning | "有什么选题", "最近写什么", "选题库" | Check topic bank for duplicates; generate new candidates; append to `topic-bank/香港留学选题库.md`; do not create `context/`. |
| Full package | "完整", "整套", "全流程", broad topic with no limiting phrase | Read both references; produce operation judgment, research notes, WeChat article/images/prompts, Xiaohongshu copy/images/prompts, short video, final check, and archive. |
| WeChat platform package | "只要公众号", "只写公众号", "公众号就行", "做公众号" | Produce WeChat article plus WeChat image planning/prompts and final check. |
| WeChat article only | "只要正文", "只要推文内容md文件", "不要图片", "不用配图" | Produce only the article file unless facts require `sources.md`. |
| Xiaohongshu platform package | "只要小红书", "小红书笔记", "改成小红书" | Produce Xiaohongshu copy plus carousel planning/prompts by default. |
| Xiaohongshu copy only | "只要小红书文案", "不要图片", "不用配图" | Produce only Xiaohongshu copy. |
| Image plan or prompt | "图片规划", "配图", "图片prompt", "AI绘图提示词" | Produce only the requested visual planning/prompt asset unless copy is also requested. |
| Short video | "短视频脚本", "口播", "60秒视频", "视频号" | Produce the requested script. |
| Optimization | User provides draft and asks "优化", "润色", "降AI味", "改一下" | Preserve intent; improve structure, tone, claims, and platform fit; do not add extra platform assets unless requested. |
| Data review | "内容复盘", "数据复盘", "48小时数据", "本周数据", "月复盘" | Read `operation-system.md`; produce the matching quick, weekly, or monthly review. |
| Monthly plan | "下个月规划", "运营规划", "内容日历" | Read `operation-system.md`; use account stage, topic bank, recent reviews, and recent content. |
| Old-content update | "哪些内容要更新", "更新重发", new ranking/policy/year | Read `operation-system.md`; inspect existing `context/`; recommend update priority or create a new version if requested. |

Mixed requests should be resolved to the smallest publishable asset set. For example, "改成小红书配图" means Xiaohongshu copy plus carousel planning/prompts; "图片prompt" alone means prompt only.

## Research Rules

For Hong Kong universities, admissions, visas, immigration, IANG, permanent residence, tuition, scholarships, employment data, government policies, rankings, or time-sensitive topics, verify current information before writing.

When web access is available, inspect comparable public content before drafting and use the scan to understand reader demand, search language, structure, and visual packaging. Do not copy wording, titles, or proprietary frameworks.

Clearly separate confirmed facts from analysis or suggestions.

## Output Rules

- Platform-only means the complete platform asset set unless the user explicitly asks for copy only or no images.
- Single-file requests should create only the named output.
- For full packages or visual deliverables, use the file names and templates in `references/content-spec.md`.
- If operation judgment says `暂缓` or `不建议做`, do not automatically produce the full package unless the user insists.
- After saving files, tell the user which files were created or updated and where.

## Quality Check

Before final delivery, check:

- accuracy and source reliability;
- unsupported or overconfident claims;
- audience fit;
- article structure and reading comfort;
- repeated template risk;
- image necessity, aspect ratios, and prompt order;
- whether official/source links appear where readers need them;
- whether the output matches the selected route.

## Hard Stops

- Do not turn planning-only requests into full content packages.
- Do not create extra files outside the selected route.
- Do not store topic planning under `context/`.
- Do not write unverified claims as facts.
- Do not silently overwrite existing work.
- Do not put generated content inside this skill directory.
