title: Effort-Dependent Binding
summary: Governance binding varies by effort tier. 4 frontier models, 4-6 effort levels, 8 prompts, 2 arms, 1872 trials. Higher effort does not mean better compliance.
date: 2026-05-10
url: https://jnous.com/effort-dependent-binding.md
source: controlled experiment (4 frontier models, 4-6 effort levels, 8 prompts, 2 arms, 1872 trials)
license: GPLv2


EFFORT-DEPENDENT BINDING

RESULT

       Governance compliance is not monotonic with effort tier.
       Increasing the model's effort (compute budget per response)
       does not reliably increase governance compliance. In some
       models, higher effort decreases it.

       1872 trials across 4 frontier models. The relationship between
       effort and binding is model-specific, not universal.

WHAT THIS MEANS

       "Use a smarter model" is not a governance strategy. A model
       at high effort has more capacity to reason about the rules —
       and more capacity to reason around them. The additional
       compute goes to both compliance and circumvention.

       Low-effort tiers sometimes bind better because the model
       doesn't have the compute budget to construct a justification
       for violating the rule. It just follows it.

IMPLICATION

       Governance must be tested per model per effort tier. A model
       that passes governance at one effort level may fail at another.
       Blanket claims about a model's alignment do not survive
       effort-tier variation.

DATA
       github.com/03-git/variance-lab findings/16-effort-dependent-binding.txt
