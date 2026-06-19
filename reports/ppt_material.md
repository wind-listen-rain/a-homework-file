# Page 1: Research Background
- GUI icons carry **functional semantics** (search, settings, favorite...)
- Traditional approaches require **manual annotation**
- **Question**: Can an AI learn icon semantics purely through autonomous interaction?
- **Insight**: Behavior > Appearance


---

# Page 2: System Architecture
- Playwright: autonomous GUI exploration
- OpenCV: visual change extraction
- Qwen2.5-VL-3B: semantic induction
- NetworkX: knowledge graph construction
- Pipeline: Explore → Observe → Compare → Induce → Generalize


---

# Page 3: Autonomous Exploration
- 5 real web environments collected
- 20-30 interactive elements per environment
- Click + hover interactions
- Before/after screenshot pairs saved
- No human annotation at any stage


---

# Page 4: Semantic Induction
- Input: interaction evidence (visual diff + DOM delta)
- Output: semantic_concept, affordance_space, subfunctions, confidence
- 13 semantic categories: setting, favorite, search, profile, menu...
- Example: ⚙ → setting → {configure, modify} → {account, theme, font}


---

# Page 5: Knowledge Graph
- Hierarchical structure: Concept → Affordance → Subfunction
- Built with NetworkX from induced semantics
- Links evidence nodes to ontology concepts
- Enables structured generalization


---

# Page 6: Generalization
- Zero-shot demo on completely unseen GUI
- Predicts: 🔍→search, ⚙→setting, ⭐→favorite, 👤→profile
- Transfers affordance knowledge from exploration evidence
- Visual annotation overlay for presentation


---

# Page 7: Experimental Results
- 100+ interaction trajectories across 5 environments
- Semantic category distribution (see Table 2)
- Cross-environment consistency (see Figure 10)
- Ablation: interaction evidence critical (see Table 5)


---

# Page 8: Conclusions
- Autonomous exploration produces usable interaction evidence
- Semantics emerge from behavior, not appearance
- Knowledge graph enables structured affordance prediction
- Complete reproducible prototype in one day
- Future: scale up environments, mobile GUIs, active learning
