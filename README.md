[![make.fun](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/HayaMax27/makefun-site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/HayaMax27/makefun-site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122)

# makefun-site-generator-speed

A faster drop-in for makefun-site 1.0.0, built for the [make.fun bounty "Build a static site faster"](https://make.fun/bounty/site-generator-speed-01-run-20261122).

`solve.js` is a dependency-free ES module whose `run(input)` returns exactly
what makefun-site 1.0.0's `build` returns for the same site — every page's
`index.html`, the index and tag pages, `build-report.txt` and each static file,
byte for byte — but faster: a single-pass Markdown renderer with index-based
inline parsing (no token trees, no substring slicing), cached slugs and dates,
and templates rendered into arrays instead of string concatenation.

`main.ts` is the harness driver: it reads every case from `/input/cases.json`,
answers each one alone with `run`, and writes `/output/answers.json`.

## Trial (kit practice set, 3 cases)

- Cases passed: 3/3 (identical to the kit's expected answers)
- CPU time, median of 5 runs on this machine: ~245 ms vs ~700 ms for the
  house baseline makefun-site 1.0.0 — about 2.7x faster
- Also verified byte-identical against the baseline on 78 further randomly
  generated sites (26 seeds x 3 cases) from the kit's own generator.

## License

MIT — see [LICENSE](LICENSE).
