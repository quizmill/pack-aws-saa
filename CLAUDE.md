# pack-aws-saa — authoring rules

A quizmill content pack for the AWS Certified Solutions Architect – Associate
(SAA-C03) exam. Public repo: write commit messages, PR bodies and comments
in terms of what a change does for a learner or pack author.

## Files

- `pack.json` — manifest (schema v2). `categories` are the four exam domains
  with the exam guide's weights; `exam` holds the guide's numbers. Both are
  cited in `NOTICE.md` — change one, update the other.
- `questions.json` — the bank. `scenarios.json` is `[]` until a shared stem
  is needed.
- `.github/workflows/deploy.yml` — calls the engine's reusable
  `deploy-pack.yml`; deploys on push to `main` only.

## Content rules

- **Every question is original**, written from the public AWS docs and the
  official exam guide. No imports from community banks, AWS official
  practice questions or pretests, or exam dumps — not even "adapted".
- Every question has `source: "original"`, `reviewStatus: "draft"`, and a
  `sourceRef` to the AWS doc page it rests on. The explanation ends with
  `Read more: <url>` pointing at a page that supports the claim. Check the
  URL returns 200 before committing.
- Ids are `aws-saa-<tier>-d<domain>-<n>`; tags are `saa-c03`,
  `domain-<n>`, `task-<n.n>` (the guide's task statement), the tier, and
  `scenario`. Never reuse or renumber an id: learner progress is keyed on it.
- Exam style: a situation with its constraints, four options (five for
  "Select TWO"), one best answer. Multi-answer stems say "(Select TWO.)"
  and use `correctKeys`.
- **Distractors must be plausible**: a real AWS feature misapplied, or a
  near-miss that meets every constraint but one. No joke options, no
  anti-patterns nobody would pick, and no distractor that announces its own
  defect ("without encryption", "manually").
- **No length cue**: the key is no longer than 1.25× the longest distractor.
- Every distractor carries a one-sentence `explanation` (≤ 300 characters)
  saying why it fails; keyed options carry none. The question
  `explanation` gives the reasoning for the key and why the tempting
  distractors fail.
- Keep the domain mix close to the blueprint weights as the bank grows.

## Before a PR

- Validator green, run from the engine on Node 22:
  `mise exec node@22 -- npx --yes quizmill@latest validate .`
  (or `npm run pack:validate -- <path>` in a `quizmill/quizmill` checkout).
  Quote its output in the PR.
- **No screenshots, PNGs, build output or other generated files** in this
  repo. Describe how the engine renders a change in a sentence instead.
