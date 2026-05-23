title: Interaction Mode Rerun
summary: 52.7x passenger/governor token ratio under pre-committed rubric. N=501 qualifying sessions from 1075 JSONL files. The original 41x holds and widens.
date: 2026-04-19
url: https://jnous.com/interaction-mode-rerun.md
source: variance-lab harness (1075 JSONL files, pre-committed rubric, 501 qualifying single-model sessions)
license: GPLv2


INTERACTION MODE RERUN

RESULT

       Replication of finding 03 under a pre-committed rubric.

                          Means     Medians    Outlier-removed
       Passenger/Governor  52.7x     21.6x      50.4x

       Ordering holds: passenger > collaborator > governor > pipe.

METHOD

       Rubric committed before analysis (commit 49d86f7). Applied to
       1075 Claude Code JSONL session files. 501 qualifying single-model
       sessions after rubric-mandated filters. Two-pass adversarial
       review across six Claude voters (three model generations, two
       nodes, two effort tiers).

       The original finding (N=88, 41x, means only) was flagged RERUN
       in editorial audit because it used post-hoc mode classification.
       This rerun pre-committed the classification rubric, expanded
       the corpus 5.7x, and the ratio widened.

WHY IT WIDENED

       Larger corpus captured more extreme passenger sessions. Governor
       mode has a natural ceiling — the human is present, directing,
       constraining. Passenger mode has no ceiling — the model explores
       until the context window fills or the human returns.

DATA
       github.com/03-git/variance-lab findings/06-interaction-mode-rerun.txt
