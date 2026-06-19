# Research Summary

## Title
Autonomous GUI Semantic Cognition via Interaction Evidence

## Core Claim
Without human annotation, an AI system can autonomously explore unknown GUI environments,
accumulate interaction evidence, induce functional semantics, and generalize to unseen icons.

## Pipeline
Unknown GUI → Autonomous Exploration → Interaction Evidence → Semantic Induction → Knowledge Construction → Generalization

## Scale
- **5** GUI environments (GitHub, YouTube, Wikipedia, Google Drive, Notion)
- **127** interactive elements discovered
- **200** interaction trajectories collected
- **127** semantic labels induced

## Key Finding
Functional semantics emerge from **behavioral evidence** (before/after visual changes, DOM deltas),
not from icon appearance alone. The system constructs a semantic knowledge graph linking
concepts → affordances → subfunctions.

## Limitations
- Prototype scope: one-day research demo, not production system
- No model training; uses Qwen2.5-VL-3B for induction + evidence rules
- Accuracy prioritized less than reproducibility and explainability
