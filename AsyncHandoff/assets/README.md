# Project media

## Current continuous-motion gallery

The current gallery contains **15 selected 60-second recordings**: five each from SALAD, MotionHiFlow and MotionGPT3. Each recording uses one persistent player and successive instructions. Chinese requests are accompanied by the English prompts actually supplied to the models.

- `fifteen-motion-studies.json`: all selected cases, instructions, timing and hashes.
- `<provider>-minute-<id>.mp4`: complete 60-second visualization.
- `<provider>-minute-<id>-raw.zip`: original native motion, target arrays and timing records.
- `<provider>-minute-<id>-provenance.json`: effective demo configuration, display processing and review.
- `candidate-outcomes.json` and `demo-candidate-records.zip`: completed unsuccessful and unselected candidate outcomes.
- `display-reconstruction-source.zip`: exact reconstruction/rendering source, with original host paths retained.

The display uses anatomical SMPL-H retargeting, temporal filtering and two-bone foot-clearance IK. This prevents reconstruction artifacts from being mistaken for the generated skeleton. It is display postprocessing, **not a measurement of unprocessed motion quality**. Native target features and their frame order are unchanged in the raw records. Selected qualitative controller settings are recorded separately from all frozen benchmark experiments. The cases are independent examples, not a matched comparison of the providers or a native Chinese-language benchmark.

## Archived visualizations

Earlier previews below are retained for traceability and are not the current gallery. Their historical diagnostic values refer to those particular fits.


Paper figures and supplementary material accompany a selected continuous multi-instruction demonstration. The original frozen benchmark results are separate from this qualitative run.

## Two views of the same recorded motion

- `two-minute-continuous.mp4`: preserved original independent per-frame SMPL-H fit.
- `two-minute-stable-anatomy.mp4`: temporal SMPL-H fitting with anatomical rotation bounds and outlier stabilization (archived preview).
- `two-minute-regularized.mp4`: earlier temporal-only fit, retained as a separate visualization artifact.
- `media-provenance.json`: prompts, seeds, command timing, checkpoint identity, processing settings and hashes for both views.

Both videos depict the same 2,400 recorded source poses on the same 2,405-frame, 20 Hz wall-clock rendering grid. Native motion features, root trajectory, target order and command timing are unchanged. The page labels both views and preserves playback position when switching.

The regularized fit uses fixed neutral body shape and fixed hand pose, 128-frame windows with a 96-frame stride, joint-acceleration weight 0.035 and body-pose acceleration weight 4e-6. Mean/P95 joint reconstruction errors are 1.60/3.38 cm. These are surface-fitting diagnostics, not motion-generation benchmark results. Neither view repairs source semantics, contacts or return boundaries.

`motivation.webp` and `framework.webp` are the current manuscript figures. `supplementary.pdf` supplies derivations, execution details, additional controls and evidence scope. All pre-existing experiment numbers and original media are retained.

That archived preview additionally bounds neck, knee, elbow and ankle rotations and holds unobserved distal head, wrist and toe rotations neutral. Seven isolated fitted outliers are replaced by bounded SO(3) interpolation from adjacent reliable fits; their source-frame indices are listed in the provenance. This is mesh visualization processing only.

## Compound Chinese-instruction cases

The additional SALAD demonstration uses 50 sampling steps and guidance 7.5. Chinese requests are accompanied by the actual English translations supplied to both generators; it is not a native Chinese-language evaluation. `compound-chinese-selected.mp4` is the first 25.05 seconds of a single four-command run, preserving two consecutive full targets without within-action cuts or speed changes. `compound-chinese-salad.mp4` retains the full recording, including subsequent candidates that were not selected as semantic showcase examples. `compound-provenance.json` records all four original instructions, timings, settings, selection and visualization processing. All four targets were delivered in the recorded run, but delivery does not establish that every requested subaction was followed accurately.
