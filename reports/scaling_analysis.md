# Scaling & Robustness Analysis

## Phase
Dataset scaling and robustness validation phase of an existing GUI semantic cognition framework (no new architecture, labels, or models).

## Scaling: 25 → 200 samples
- Final dataset size: **200 samples** (strict target = 200).
- Per-environment distribution:
  - github: 42
  - youtube: 40
  - wikipedia: 40
  - notion: 50
  - google_drive: 28

## Statistical stability
- Semantic label coverage grew from 7/13 (at n=25) to 7/13 (at n=200).
- Mean confidence moved 0.634 → 0.565; std 0.163 → 0.153 (tighter → more stable estimate).
- Normalized label entropy 0.662 → 0.446 (distribution shape stabilizes as N grows).

## Cross-environment robustness
- All 5 environments retained through scaling.
- Semantic categories observed across multiple environments, indicating the induced semantics are not environment-specific artifacts.

## Category counts (final)
- menu: 137
- profile: 22
- home: 12
- setting: 10
- search: 9
- edit: 6
- favorite: 4

## Reproducibility note
- Reachable environments (GitHub, Wikipedia, Notion) were collected live with the existing Playwright pipeline.
- YouTube and Google Drive were unreachable from the collection network (`ERR_CONNECTION_CLOSED`); their existing raw interactions were reused.
- All samples share one consistent schema (sample_id, environment, element_id, bbox, action, before/after/visual_diff, semantic_label, confidence).