---
name: pr-description
description: Create high-signal pull request descriptions from verified branch evidence. Use when drafting, reviewing, improving, or templating PR descriptions, especially when the user wants reviewers to understand why a PR exists and how to review it.
---

# PR Description

## Purpose

A PR description is a review-routing document. It should help reviewers understand why the PR exists, what changed, what deserves attention, where to look, and what confidence changed.

Do not draft from memory, issue text, or conversation context alone. Inspect the branch first, then write only claims supported by the diff.

## Workflow

1. Inspect the current state:
   - Current branch and base branch.
   - Stack context if the repo uses stacked branches.
   - Changed files and diff stat.
   - Commit summaries when useful.
   - Existing PR template if the repo has one.

2. Verify behavior from code:
   - Entry points, routes, commands, actions, or APIs.
   - User-visible behavior from UI/components or product surfaces.
   - System behavior from handlers, services, queries, jobs, migrations, or config.
   - Tests added, changed, or removed from actual test files and test names.

3. Draft from evidence:
   - Prefer concrete outcomes over implementation trivia.
   - Do not list every file.
   - Do not restate the same bullet in multiple sections.
   - Use issue/design links as supporting context, not as a substitute for a self-contained summary.

4. Audit every claim:
   - Each `Summary`, `What Changed`, `Code Map`, and `Test Coverage` claim should map to branch evidence.
   - Remove or soften claims inferred only from issue text, commit messages, or the conversation.
   - Avoid mentioning downstream work unless it is necessary to prevent a likely review misunderstanding.

## Default Shape

Use this as a starting point, then remove sections that do not earn their keep:

```md
## Summary

1-3 sentences explaining why this PR exists and what outcome it enables.

## What Changed

- Behavior or capability change.
- Behavior or capability change.
- Shared/refactor change only if it affects review scope.

## Review Notes

Optional. Include only specific decisions, tradeoffs, risks, or judgment calls reviewers should evaluate.

## Code Map

Optional. Include only for broad diffs.

- `path/or/area`: general responsibility.
- `path/or/area`: general responsibility.

## Test Coverage

- Automated coverage added, changed, or removed.
```

## Section Heuristics

### Summary

Answer why the PR exists and what outcome it enables. Keep it short. Do not turn it into a file list or implementation summary.

### What Changed

Describe user-visible or system-visible capabilities. A useful shape is:

- Adds or changes the entry point.
- Presents or changes important state/data.
- Allows or changes an action.
- Extracts or refactors shared code only when that changes review scope.

### Review Notes

Use this only when it changes how someone should review. Good review notes name decisions, tradeoffs, risks, or judgment calls. If the notes repeat `What Changed`, delete the section or fold the useful sentence into `What Changed`.

### Code Map

Use this for broad diffs where reviewers need navigation help. Keep it at feature-area level. The code map should route attention, not enumerate files.

### Test Coverage

Say what automated coverage was added, changed, or removed. Do not restate that CI runs format, lint, typecheck, or tests unless CI behavior is unusual for the repo.

## Optional Sections

Add these only when they are real:

- `Screenshots`: only when screenshots or recordings are attached.
- `Rollout Notes`: flags, migrations, backfills, operational sequencing, or deploy risk.
- `Known Limitations`: intentional constraints in the shipped change that reviewers might otherwise mistake for bugs.

## Quality Bar

- If two sections can contain the same bullet, one of them is wrong.
- Prefer positive scope over long "not included" lists.
- Keep reviewer attention on what matters for this PR.
- Make the description self-contained even when links are included.
- Before finalizing, read the description as a list of factual claims and check each claim against the branch.
