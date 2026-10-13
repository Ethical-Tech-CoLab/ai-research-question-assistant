# Decision-model recommendation: bounded citation and rubric checks

Date: 2026-10-11. Public-source proposal; no measured experiment.
Reviewed [README](https://github.com/Ethical-Tech-CoLab/ai-research-question-assistant/blob/23e297a614960a8bcc51596906ae99ffc85e3353/README.md).
This is a documentation-led assessment of the paper and reusable-prompt
workflow, not evidence of an implemented model API.

## Starting point

Keep generative models and researchers responsible for developing questions.
Jev is not a substitute for writing hypotheses, searching literature or
reasoning through a research design. The useful bounded seam is the proposed
critical-review layer: assess a claim against a retrieved source, or flag a
missing rubric item for human inspection.

Check exact quote presence first. Return supports / contradicts / not
established / insufficient evidence. Domain-only citation markers in the source
are not verified URLs and must not be treated as retrieved evidence.

## Preserve the scientific contract

Do not label a research gap as real because no retrieved paper mentions it.
Do not equate venue reputation with truth, model confidence with originality,
or a second model's agreement with independent review. Retain researcher
reflection about how AI shaped the question.

## Trial

Compare the current human/prompt workflow with local classifiers, Jev's
[citation pattern](https://docs.typesafe.ai/cookbooks/citation_check.md),
Microsoft-Decision-1 and Sage on approved public text. The
[official authoring skill](https://docs.typesafe.ai/agent-skill.md) can guide an
integration audit; installing it is optional, not part of this proposal.

Split by paper/research-question family. Include misleading titles, unsupported
causal claims, negation, source disagreement and missing full text. Measure
unsupported-claim acceptance, relevant-evidence recall, calibration and review
time. Keep reviewers blind to provider and preserve unresolved disagreement.

## Gate

Begin with offline annotations; do not rewrite the published source-of-truth
document or credibility rubric. Require higher useful review coverage at an
acceptable full cost, including retrieval and human correction. No measured
savings or qualified model is claimed. Exact proprietary checkpoints are not
available locally; use separately licensed local alternatives if needed.
