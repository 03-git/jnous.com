title: Handler Substrate Selection
summary: Three-gate methodology for picking which model runs handler.sh. 240 trials, 3 models. nano-4b wins (TC 3.05, 6.5s wall). The 14b model cannot dispatch at all — 0% tool calls, confabulates output.
date: 2026-05-10
url: https://jnous.com/handler-substrate-selection.md
source: production empirical (240 trials, 3 models, three-gate methodology)
license: GPLv2


HANDLER SUBSTRATE SELECTION

RESULT

       Three candidate models for the subtract.sh handler dispatch layer:

       nano-4b            TC 3.05    6.5s wall     dispatches
       openreasoning-14b  TC 0       confabulates  0% tool calls
       super-49b          TC higher  34x slower    dispatches

       nano-4b wins. It dispatches tool calls reliably at 6.5 seconds
       wall clock. super-49b technically scores higher but takes 34x
       longer — the marginal quality is not worth the wait.

       openreasoning-14b cannot dispatch at all. Zero tool calls across
       all trials. It reasons about what it would do, then confabulates
       the output instead of calling the tool. More parameters, more
       reasoning, worse result.

THREE-GATE METHOD

       Gate 1: does it produce a tool call at all.
       Gate 2: is the tool call syntactically valid.
       Gate 3: does the tool call produce the correct result.

       A model that fails gate 1 cannot be rescued by prompt
       engineering. The failure is structural — it doesn't know
       how to emit tool-call format. No amount of instruction
       fixes that. Pick a different model.

DATA
       raw.githubusercontent.com/03-git/variance-lab/refs/heads/main/findings/17-handler-substrate-selection.txt
