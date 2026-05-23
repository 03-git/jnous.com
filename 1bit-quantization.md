title: 1-Bit Quantization
summary: 1-bit quantization breaks the 8GB deployment ceiling. Bonsai 8B runs on 8GB M2 Mini where Q4 and Q8 cannot load. 494 measurements.
date: 2026-04-25
url: https://jnous.com/1bit-quantization.md
source: production empirical (494 measurements, 3 conditions + 1 preliminary, Bonsai 8B, 8GB M2 Mac Mini)
license: GPLv2


1-BIT QUANTIZATION

RESULT

       An 8B parameter model at Q4 quantization requires more than 8GB
       RAM to serve. It does not load on an 8GB machine.

       The same model at 1-bit quantization loads and serves on 8GB.
       494 measurements confirm it runs, responds, and produces usable
       output where Q4 and Q8 cannot even start.

       The 8GB machine goes from "cannot run local inference" to
       "can run local inference." That is a binary threshold, not
       a performance gradient.

WHY THIS MATTERS

       8GB is the floor for consumer hardware. Phones, tablets, entry
       laptops, Raspberry Pi-class boards. Everything below the
       professional tier. 1-bit makes local inference possible on
       hardware people already own.

       The quality tradeoff exists. 1-bit output is worse than Q8.
       But Q8 output on a machine that cannot load the model is
       zero. Worse than zero is still more than zero.

DATA
       raw.githubusercontent.com/03-git/variance-lab/refs/heads/main/findings/08-1bit-quantization.txt
