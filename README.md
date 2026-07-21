# Hong Kong Study Content Skill

Version: `v3.0`

This repository contains a Codex skill for Hong Kong study-abroad content operations.

## What changed in v3.0

- Shrunk the main `SKILL.md` so it only keeps entry rules, routing, workspace boundaries, and hard stops.
- Moved detailed workflow rules into `references/content-spec.md` and `references/operation-system.md`.
- Added table-of-contents blocks to the reference files so Codex can navigate them faster.
- Shortened `agents/openai.yaml` so the UI metadata is compact and does not duplicate the full skill logic.
- Removed the stray `.DS_Store` file from the skill folder.

## What changed in v2.0

- Added operation judgment before broad topic production, so bare topics and "我想写这篇" requests are evaluated before entering the full content workflow.
- Added account-stage awareness through `operations/account-stage.md`, including cold-start assumptions, platform priorities, and topic-fit criteria.
- Added `references/operation-system.md` for topic scoring, content data review, monthly planning, and old-content update decisions.
- Expanded platform routing: "只要公众号" and "只要小红书" now mean complete platform asset packages by default unless images or extra files are explicitly excluded.
- Added audience segmentation, soft conversion standards, SEO/search-term handling, Xiaohongshu carousel diversity rules, and split-package execution guidance.
- Added operations output folders for content reviews and monthly plans.

## What changed in v1.0

- Created the initial `hong-kong-study-content` Codex skill for Hong Kong study-abroad content production and routing.
- Defined the core workflow system for topic planning, research, WeChat article writing, image planning, AI image prompts, Xiaohongshu adaptation, short-video scripts, final checks, and file archiving.
- Established the workspace asset structure: production files in `context/` and topic planning in `topic-bank/香港留学选题库.md`.
- Added the first `references/content-spec.md` with file naming, platform output formats, image ratio rules, prompt standards, and publication-check templates.
- Added initial `agents/openai.yaml` metadata for the skill.
- Seeded the workspace with early Hong Kong study-abroad content examples and topic-bank entries.

## How to use

- Broad topics or bare titles go through operation judgment first.
- Platform-only requests return that platform's full asset set unless images are explicitly excluded.
- Single-file requests stay narrow.
- Topic planning belongs in `topic-bank/`.
- Production files belong in `context/`.
- Reviews and plans belong in `operations/`.

## Main references

- `hong-kong-study-content/SKILL.md`
- `hong-kong-study-content/references/content-spec.md`
- `hong-kong-study-content/references/operation-system.md`
