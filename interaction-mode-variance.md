title: Interaction Mode Variance
summary: Passenger mode consumes 41x more tokens than governor mode. 88 sessions, single operator, single model. The human's posture determines the cost.
date: 2026-03-30
url: https://jnous.com/interaction-mode-variance.md
source: production empirical (88 Claude Code sessions, single operator)
license: GPLv2


INTERACTION MODE VARIANCE

RESULT

       Four interaction modes. Same operator. Same model. Token consumption
       varies by 41x depending on how the human engages.

       Passenger      human stops steering, model explores unconstrained
       Collaborator   human and model alternate, shared direction
       Governor       human directs, model executes
       Pipe           human sends structured input, model returns structured output

       Ordering: passenger > collaborator > governor > pipe.

WHY THIS MATTERS

       The model doesn't change. The human's posture does. Passenger mode
       is not the model being wasteful — it's the human being absent.
       Governor mode is not the model being efficient — it's the human
       being present.

       Token cost is a function of human attention, not model capability.

DATA
       raw.githubusercontent.com/03-git/variance-lab/main/findings/03-interaction-mode-variance.txt
