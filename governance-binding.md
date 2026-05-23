title: Governance Binding
summary: Governance binds at N=30. 81% overall, reflex-dependent, delivery-path sensitive. Some reflexes bind at 96-100%. One doesn't belong in this adapter.
date: 2026-04-19
url: https://jnous.com/governance-binding.md
source: variance-lab harness (SmolLM2 1.7B Q8, N=30, temp=0.3, v6 iter 100)
license: GPLv2


GOVERNANCE BINDING

RESULT

       Kernel adapter v6, 242/300 correct (81%) at N=30, temp=0.3.

       Reflex              Binding
       r4 (verify)          96%
       r5 (canonical)      100%
       boundary             93%
       f-additive           97%
       f-confab             87%
       reflex.1 (kernel)    48%

       reflex.1 scores 48% because it requires shell-ipc-routing
       knowledge that belongs in a different adapter, not governance.

DELIVERY-PATH SENSITIVITY

       How governance reaches the model matters. Binding strength
       varies by delivery path — system prompt, adapter weights,
       fine-tune, in-context examples produce different binding
       rates for the same governance rules.

WHAT BINDS VS WHAT DOESN'T

       Binary rules bind: "verify before acting", "canonical source
       is the signing domain." The model either checks or doesn't.

       Judgment rules bind weakly: "name the kernel primitive before
       proposing a library" requires domain knowledge the governance
       adapter doesn't carry. That knowledge belongs in a domain
       adapter.

DATA
       raw.githubusercontent.com/03-git/variance-lab/refs/heads/main/findings/05-governance-binding.txt
