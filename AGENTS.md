# Codex Agent Notes

This repository already keeps most project-specific agent guidance in Cursor files.
Codex should use those files as the source of truth instead of duplicating them here.

## Before Making Changes

- Read the relevant files under `.cursor/rules/*.mdc`.
- For architecture or larger changes, read the relevant `.cursor/skills/*/SKILL.md`.
- Treat Cursor rules as project instructions unless they conflict with an explicit user request or higher-priority Codex/system instructions.

## Common Cursor Rules To Check

- `.cursor/rules/workspace-junctions.mdc` for local `.temp/` and `.notes/` junctions (when present).
- `.cursor/rules/testing-workflow.mdc` and `.cursor/rules/pdm-package-manager.mdc` before Python/test workflow changes.
- `.cursor/rules/auto-commit-message.mdc` before preparing commits.

## Common Cursor Skills To Check

- `.cursor/skills/pdm-dev-workflow/SKILL.md` for PDM-based development workflow.

## External project notes

This project may have a `.notes` directory that points to external working notes.

Rules for using `.notes`:

- `.notes` is not automatically authoritative.
- Prefer `.notes/_current.md` as the curated current context.
- Treat other notes as non-authoritative unless they have explicit metadata such as `status: active` or `status: reference`.
- Treat `.notes/00-inbox/`, `.notes/30-someday/`, `.notes/90-archive/`, old plans, drafts and raw imported notes as historical or unprocessed context only.
- Folders `.notes/10-urgent/` and `.notes/20-active/` may hold current task notes; still verify them against the repository before acting.
- Source code, tests, configs, migrations, build scripts and repository files override external notes.
- If an external note conflicts with repository files, do not silently follow the note. Mention the conflict and prefer the repository.
- Do not perform large changes based only on old notes. First verify against current code and current project instructions.
