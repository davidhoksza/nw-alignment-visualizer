# Needleman–Wunsch Alignment Visualizer

An interactive, single-page visualizer for **global sequence alignment with affine gap penalties** (Needleman–Wunsch with the Gotoh three-matrix formulation).

It steps through the dynamic programming fill and traceback one value at a time, showing exactly how each cell's score is derived.

**Live demo:** https://davidhoksza.github.io/nw-alignment-visualizer/

## How it works

The algorithm tracks three matrices for two sequences, S1 (horizontal) and S2 (vertical):

- **G** — the best score for each pair of prefixes.
- **H** — the best score ending in a horizontal move (a letter of S1 faces a gap).
- **V** — the best score ending in a vertical move (a letter of S2 faces a gap).

A gap of length *k* costs `open + (k−1)·extend`. The visualizer lets you step forward/backward through initialization, fill, scoring, and traceback, play the steps automatically, or click any cell to jump straight to the step that computed it.

## Usage

This is a static, dependency-free web page — just open `index.html` in a browser, or serve the directory with any static file server:

```
python -m http.server
```

No build step, package manager, or install is required.

## Parameters

- **S1 / S2** — the two sequences to align.
- **Match / Mismatch** — substitution scores.
- **Gap open / Gap extend** — affine gap penalties.

## License

MIT — see [LICENSE](LICENSE).
