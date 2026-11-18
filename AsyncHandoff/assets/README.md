# Project media

Everything shown on the project page is rendered **after de-jittering and anatomical IK** (the postprocessing stage released with the code). Native motion records are kept next to each video for inspection.

## Gallery — fifteen one-minute recordings

Five recordings each for SALAD, MotionHiFlow and MotionGPT3. Each recording is one persistent 20 Hz player running for 60 s with successive instructions; every target is played in full (70/70) with 0.0 s of unserved playback.

| File | Contents |
| :-- | :-- |
| `gallery.json` | Compact index used by the page: instructions, timing, bridge lengths and file names. |
| `fifteen-motion-studies.json` | Full case list with instructions, timing and hashes. |
| `<provider>-minute-<id>.mp4` | 60-second postprocessed video. |
| `<provider>-minute-<id>-poster.webp` | Poster frame. |
| `<provider>-minute-<id>-raw.zip` | Native motion, target arrays and timing records (unprocessed data). |
| `<provider>-minute-<id>-provenance.json` | Effective configuration, display-processing settings, fitting diagnostics and review. |
| `hero-trio.mp4` / `hero-trio-poster.webp` | Page teaser: unedited 4–24 s excerpts of SALAD-03, MotionHiFlow-02 and MotionGPT3-05, cropped and placed side by side. |
| `candidate-outcomes.json`, `demo-candidate-records.zip` | All 56 completed candidate runs, including unselected and unsuccessful ones. |
| `display-reconstruction-source.zip` | Reconstruction and rendering source. |

## Display postprocessing

1. Savitzky–Golay de-jittering of joint trajectories (window 7, order 2).
2. Twist-resolved local rotations with bounded SMPL-H limb fitting (≤ 0.12 rad).
3. Two passes of 7-tap relative-rotation smoothing on SO(3).
4. Anatomical bounds: neck/ankle cones (0.85/1.05 rad), hinge knees and elbows, neutral head/wrists/fingers.
5. Two-bone leg IK toward the source ankles with residual floor clearance, then fresh skinning (no vertex warping).

This is an output stage only. Native target features, frame order, ownership and timestamps are unchanged; nothing is fed back into the generators, admission checks or reported metrics. Mean display deviation from the source joints is 3.8–4.3 cm per provider. The recordings are qualitative examples, separate from the frozen benchmark, and not a matched comparison of providers or a native Chinese-language evaluation.

## Paper material

- `motivation.webp`, `framework.webp`: Figures 1 and 2 of the manuscript.
- `supplementary.pdf`: derivations, protocols, controls, failure taxonomy and demonstration records.
