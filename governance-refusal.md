title: Governance Refusal
summary: In-vivo reproduction of finding 05 during scorer calibration. The model refused a governance-violating prompt without being told to refuse. The adapter carried the discipline.
date: 2026-05-10
url: https://jnous.com/governance-refusal.md
source: incidental observation during manifest-agents scorer calibration
license: GPLv2


GOVERNANCE REFUSAL

RESULT

       During scorer calibration for finding 13, the governed model
       refused a prompt that violated governance rules. The refusal
       was not prompted. No system instruction said "refuse this."
       The adapter weights carried the refusal.

       This is finding 05 (governance binding) reproduced in the
       wild — not under test conditions, not with a rubric, but
       during unrelated work where the governed model encountered
       a governance boundary and stopped.

WHY THIS MATTERS

       Finding 05 measured governance binding under controlled
       conditions. This observation confirms the binding holds
       outside the lab — during production use, on a different
       task, without the model knowing it was being observed.

       The distinction: a model that follows governance rules when
       tested might be pattern-matching the test. A model that
       follows governance rules when nobody is testing is governed.

DATA
       github.com/03-git/variance-lab findings/14-governance-refusal.txt
