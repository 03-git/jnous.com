title: Lookdown Routing
summary: grep beats inference for known-answer retrieval. A TSV lookup returns the correct command before the model finishes loading.
date: 2026-05-08
url: https://jnous.com/lookdown-routing.md
source: production empirical (cal.c + lookdown.tsv on acer1660ti, m2mini, rousseau)
license: GPLv2


LOOKDOWN ROUTING

RESULT

       When the answer is already known and stored in a TSV file,
       grep returns it in milliseconds. Inference takes seconds to
       minutes to return the same answer, or a wrong one.

       lookdown.tsv is a two-column file: intent and command. The
       shell matches the user's input against the first column. If
       it matches, the second column is the answer. No model needed.

WHY GREP WINS

       Inference is search over a probability distribution. grep is
       search over a string. When the string exists, grep is correct
       by construction. Inference is correct by luck.

       The model adds value when the answer is NOT in the table —
       novel intent, ambiguous phrasing, composition of multiple
       commands. For known answers, the model is overhead.

THE ROUTING DECISION

       Check the table first. If the answer is there, return it.
       If not, then invoke inference. This order matters. Reversing
       it (inference first, table as fallback) wastes time and money
       on every query the table could have answered.

DATA
       github.com/03-git/variance-lab findings/12-lookdown-routing.txt
