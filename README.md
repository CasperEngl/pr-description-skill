# pr-description

Codex skill for drafting high-signal pull request descriptions from verified branch evidence.

The skill emphasizes:

- Inspecting branch state before drafting.
- Writing review-facing claims that are supported by the diff.
- Avoiding duplicate sections and noisy file lists.
- Using optional sections only when they help reviewers.

Install by placing this directory in your Codex global skills directory, usually:

```sh
~/.agents/skills/pr-description
```

Invoke it with requests like:

```text
$pr-description draft a PR description for this branch
$pr-description improve this PR description
$pr-description create reusable PR description guidance
```
