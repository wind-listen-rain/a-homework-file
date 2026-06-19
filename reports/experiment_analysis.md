# Experiment Analysis

## Semantic Distribution
- **menu**: 92 elements
- **profile**: 12 elements
- **home**: 8 elements
- **search**: 6 elements
- **setting**: 5 elements
- **edit**: 2 elements
- **favorite**: 2 elements

## Evidence Quality
- Trajectories with significant visual change (>5000px): 60
- URL navigation events: 200
- Successful click/hover: 118

## Interpretation
Higher visual change areas correlate with menu/popup affordances.
Navigation changes suggest search/home/profile semantics.
The system uses these behavioral cues — not icon shape — for induction.

## Zero-Shot Generalization
See `results/zero_shot/` for predictions on an unseen GUI toolbar.
