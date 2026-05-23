title: Review vs Verification
summary: Model code review and functional verification have asymmetric yield. Cheaper model found the crash path. Expensive model missed it. 1768 lines C, 5 reviews, 4 models.
date: 2026-05-07
url: https://jnous.com/review-vs-verification.md
source: production empirical (three-gate code review of cal.c, 1768 lines C, 5 reviews across 4 models and 3 effort tiers)
license: GPLv2


REVIEW VS VERIFICATION

RESULT

       Five model code reviews of a 1768-line C framebuffer application.
       Four models, three effort tiers.

       The cheaper model (sonnet, low effort) found the DRM framebuffer
       crash path. The expensive model (opus, xhigh effort) missed it.

       Functional verification on target hardware (acer1660ti, i915)
       confirmed the crash path was real.

EFFORT-TIER INVERSION

       Higher effort does not mean higher yield. The expensive model
       produced more text, more suggestions, more analysis — and
       missed the thing that crashes the program.

       The cheaper model was terse, checked fewer things, and caught
       the one that mattered.

       This is the second observation of effort-tier inversion in this
       corpus (the first was finding 17, handler substrate selection).

THREE-GATE METHOD

       Gate 1: does it compile.
       Gate 2: does it survive first run.
       Gate 3: rubric scoring against pre-committed criteria.

       Model review is gate 3 work. Functional verification is gate 2.
       Gate 2 caught what gate 3 missed.

DATA
       github.com/03-git/variance-lab findings/11-review-vs-verification.txt
