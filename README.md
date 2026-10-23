# pack-aws-saa — a quizmill learning pack

Practice for the **AWS Certified Solutions Architect – Associate (SAA-C03)**
exam (65 questions, 130 min, pass 720/1000, scaled). This pack holds
**60 original exam-style scenarios**, 15 in each of the four exam domains,
spread over the Easy, Hard and Very hard tiers.

> **Unofficial.** Not affiliated with or endorsed by AWS. This is community
> study material — every question is `draft`; cross-check against the AWS
> docs and the official practice set.

## Where the questions come from

Every question was **written for this pack** (`source: "original"`, tag
`scenario`, ids `aws-saa-<tier>-d<domain>-<n>`) from the public AWS
documentation and the official exam guide. None is imported or adapted from
a community bank, AWS's official practice questions, or any exam dump. Each
question's `sourceRef` is the AWS doc page it rests on, and its explanation
ends with the same link. See [`NOTICE.md`](NOTICE.md).

The questions follow the exam's form: a situation with its constraints
("LEAST operational overhead", "MOST cost-effective"), four full-sentence
options with one best answer, or five options for "Select TWO" (eight of the
60). Every wrong option is a real AWS feature misapplied or a near-miss that
fails one constraint, carries a one-sentence note saying why it fails, and
the question's explanation covers the key and the tempting distractors.

## Categories & tiers

Categories are the **official exam domains**, with the exam guide's weights
as category `weight`s, so the app's readiness estimate is weighted like the
real exam. Each question is also tagged with the guide's task statement
(`task-1.1` … `task-4.4`).

| Domain | Weight | Questions (Easy / Hard / Very hard) |
| --- | ---: | --- |
| Design Secure Architectures | 30% | 15 (4 / 7 / 4) |
| Design Resilient Architectures | 26% | 15 (4 / 7 / 4) |
| Design High-Performing Architectures | 24% | 15 (4 / 7 / 4) |
| Design Cost-Optimized Architectures | 20% | 15 (4 / 7 / 4) |

The manifest's `exam` block switches on the timed exam: it deals from the
Very hard tier at the real exam's pace (130 minutes for 65 questions,
pro-rated to the 16 Very hard questions available).

## Known limitations

- **Seed bank.** 60 questions is a start, not a mock exam: the domains are
  balanced by count rather than by blueprint weight, and some task
  statements have one or two questions.
- **Draft.** No human review yet. An automated blind solve (answering
  without the keys) agreed with all 60 keys; two stems it flagged as loose
  were tightened.

## Use it

```
npm run pack:use packs/aws-saa   # after copying this dir into the engine's packs/
npm run dev                      # http://localhost:3000
```

Or point the engine at this directory directly. To deploy as its own app,
the included `.github/workflows/deploy.yml` builds it onto the quizmill
engine (static app in `aws-saa-app/`, named after the manifest id) and
publishes to Cloudflare Pages (project `aws-saa`) once the repo's
`CLOUDFLARE_*` secrets are set.
