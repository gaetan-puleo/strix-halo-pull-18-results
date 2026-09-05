# Strix Halo PR #18 Results

Benchmark and correctness results for [halo-box/strix-llama.cpp PR #18](https://github.com/halo-box/strix-llama.cpp/pull/18), measured on a Ryzen AI Max+ 395 with Radeon 8060S graphics.

## Interactive Report

[Open the benchmark atlas](https://gaetan-puleo.github.io/strix-halo-pull-18-results/)

The report groups all 61 canonical quants under nine model families and includes PP512, PP1024, PP2048, PP4096, and TG128 at depths 0, 12k, 32k, 64k, and 128k.

## Method

- ROCm 7.14, gfx1151
- `-b 2048 -fa 1 -ngl 999 --load-mode mmap -r 4`
- Dense models: `-ub 512`
- MoE models: `-ub 2048`
- First repetition discarded
- Reported values are mean and sample deviation from repetitions 2-4

## Data

- [`results-trimmed.csv`](results-trimmed.csv): all 1,525 configurations and retained samples
- [`results-all.md`](results-all.md): long-form Markdown table
- [`results-all-wide.md`](results-all-wide.md): 61-row wide matrix
- [`model-correctness-vs-master.md`](model-correctness-vs-master.md): per-model merged-versus-master validation
- [`model-correctness-vs-master.csv`](model-correctness-vs-master.csv): machine-readable correctness metrics

All 61 tested models produced bit-identical saved logits against the control build. The full ROCm backend suite passed 13,986 out of 13,986 tests.
