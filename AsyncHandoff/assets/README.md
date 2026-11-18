# Project media

Paper figures and supplementary material accompany a selected continuous multi-instruction demonstration. The original frozen benchmark results are separate from this qualitative run.

## Two views of the same recorded motion

- `two-minute-continuous.mp4`: preserved original independent per-frame SMPL-H fit.
- `two-minute-regularized.mp4`: weak temporal regularization during SMPL-H surface fitting to reduce fitting jitter.
- `media-provenance.json`: prompts, seeds, command timing, checkpoint identity, processing settings and hashes for both views.

Both videos depict the same 2,400 recorded source poses on the same 2,405-frame, 20 Hz wall-clock rendering grid. Native motion features, root trajectory, target order and command timing are unchanged. The page labels both views and preserves playback position when switching.

The regularized fit uses fixed neutral body shape and fixed hand pose, 128-frame windows with a 96-frame stride, joint-acceleration weight 0.035 and body-pose acceleration weight 1e-6. Mean/P95 joint reconstruction errors are 1.60/3.37 cm. These are surface-fitting diagnostics, not motion-generation benchmark results. Neither view repairs source semantics, contacts or return boundaries.

`motivation.webp` and `framework.webp` are the current manuscript figures. `supplementary.pdf` supplies derivations, execution details, additional controls and evidence scope. All pre-existing experiment numbers and original media are retained.
