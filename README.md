# pr-description

Codex skill for drafting high-signal pull request descriptions from verified branch evidence.

The skill emphasizes:

- Inspecting branch state before drafting.
- Writing review-facing claims that are supported by the diff.
- Avoiding duplicate sections and noisy file lists.
- Using optional sections only when they help reviewers.

Install with the skills.sh CLI:

```sh
npx skills add CasperEngl/pr-description-skill
```

See the skills.sh installation docs: https://www.skills.sh/docs

Invoke it with requests like:

```text
$pr-description draft a PR description for this branch
$pr-description improve this PR description
$pr-description create reusable PR description guidance
```
