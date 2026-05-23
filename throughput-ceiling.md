title: Throughput Ceiling
summary: Aggregate inference throughput plateaus at a hardware-determined ceiling. Adding concurrency past the plateau wastes energy without gaining tokens.
date: 2026-04-25
url: https://jnous.com/throughput-ceiling.md
source: production empirical (scaling curve, 8 concurrency levels, M1 Max 64GB)
license: GPLv2


THROUGHPUT CEILING

RESULT

       Aggregate tokens/second across concurrent inference requests
       follows a curve: linear scaling at low concurrency, sublinear
       in the middle, flat at the top. The ceiling is set by hardware —
       memory bandwidth and compute — not by software configuration.

       Adding concurrent requests past the plateau does not increase
       aggregate throughput. Each individual request slows down.
       Total output stays the same. Latency per request increases.

WHAT SETS THE CEILING

       Memory bandwidth. The model weights must travel from RAM to
       compute for every token generated. At concurrency 1, the bus
       serves one stream. At concurrency N, the bus serves N streams
       from the same bandwidth. The ceiling is when the bus saturates.

       No software optimization moves the ceiling. Faster RAM does.
       Fewer bits per parameter (1-bit quantization) does. A different
       machine does.

IMPLICATION

       Knowing the ceiling for a given machine tells you the maximum
       useful concurrency. Running beyond it is pure waste — more
       power, more heat, same output.

DATA
       raw.githubusercontent.com/03-git/variance-lab/main/findings/10-throughput-ceiling.txt
