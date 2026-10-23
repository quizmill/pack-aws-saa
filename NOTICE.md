# Notices

## Original questions

Every question in this pack has `source: "original"` (ids
`aws-saa-<tier>-d<domain>-<n>`, tag `scenario`). They were written for this
pack and are not derived from any community question bank, from AWS's
official practice questions or Official Pretest, or from any third-party
practice exam or "dump". Each one is grounded in the public AWS
documentation page named in its `sourceRef`; the AWS docs are cited, not
reproduced.

## Exam blueprint

The manifest's `exam` block and category weights come from the official
exam guide and certification page, checked on 2026-10-23:

- **AWS Certified Solutions Architect – Associate (SAA-C03) exam guide**
  <https://docs.aws.amazon.com/aws-certification/latest/solutions-architect-associate-03/solutions-architect-associate-03.html>
  - "The exam includes 50 questions that affect your score." and "The exam
    includes 15 unscored questions that do not affect your score." —
    65 questions in total (`exam.questionCount: 65`).
  - "Your results for the exam are reported as a scaled score of
    100–1,000." and "The minimum passing score is 720." — `exam.passPct: 72`
    with `exam.scaled: true` (the raw-to-scaled mapping is not public, so
    the app's readiness estimate is a raw-accuracy target, not a scaled
    score).
  - Content domains, used as this pack's categories with their weights:
    Domain 1 Design Secure Architectures (30% of scored content), Domain 2
    Design Resilient Architectures (26%), Domain 3 Design High-Performing
    Architectures (24%), Domain 4 Design Cost-Optimized Architectures (20%).
  - Each question's `task-N.N` tag is the guide's task statement it
    exercises (Task 1.1 "Design secure access to AWS resources" through
    Task 4.4 "Design cost-optimized network architectures").
- **AWS Certified Solutions Architect – Associate certification page**
  <https://aws.amazon.com/certification/certified-solutions-architect-associate/>
  - "Exam duration: 130 minutes" (`exam.durationMinutes: 130`; the exam
    guide itself does not state a duration) and "65 questions; either
    multiple choice or multiple response".

## Not included

No AWS-copyrighted material is included in this pack. AWS Skill Builder's
official practice questions, the Official Pretest, and any commercial
question banks are proprietary and are **not** redistributed here. Study
those directly on AWS Skill Builder — they are the authoritative source.

AWS and the AWS certification names are trademarks of Amazon.com, Inc. or
its affiliates. This pack is unofficial and not affiliated with or endorsed
by AWS.
