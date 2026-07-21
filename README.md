# Hong Kong Study Content Skill

Version: `v3.0`

This repository contains a Codex skill for Hong Kong study-abroad content operations.

## What changed in v3.0

- Shrunk the main `SKILL.md` so it only keeps entry rules, routing, workspace boundaries, and hard stops.
- Moved detailed workflow rules into `references/content-spec.md` and `references/operation-system.md`.
- Added table-of-contents blocks to the reference files so Codex can navigate them faster.
- Shortened `agents/openai.yaml` so the UI metadata is compact and does not duplicate the full skill logic.
- Removed the stray `.DS_Store` file from the skill folder.

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
