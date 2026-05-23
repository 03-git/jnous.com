title: Delegation vs Inline Execution
summary: Delegated parallel execution across 3 nodes completed identical tasks in 48% of wall clock. The only variable was topology.
date: 2026-03-28
url: https://jnous.com/delegation-vs-inline.md
source: production empirical (controlled comparison, identical task set)
license: GPLv2


DELEGATION VS INLINE EXECUTION

RESULT

       10 identical tasks. Same model. Same subscription cost.

                         Inline (1 node)    Delegated (3 nodes)
       Wall clock        126 seconds        65 seconds
       Output            134 lines          104 lines

WHAT HAPPENS

       Single-context inline forces sequential file reads. By task 7,
       the context window contains the residue of tasks 1-6. The model
       processes increasingly bloated context for each subsequent task.

       Delegated gives each node a fresh context window scoped to its
       assigned tasks. No accumulation, no residue, no cross-contamination.

TWO CEILINGS

       Single-context hits both simultaneously:

       Time       sequential execution scales linearly with task count
       Context    the window fills, degrading quality on later tasks

       Delegation hits neither. Each node works in parallel with a
       clean window.

DATA
       raw.githubusercontent.com/03-git/variance-lab/refs/heads/main/findings/02-delegation-vs-inline.txt
