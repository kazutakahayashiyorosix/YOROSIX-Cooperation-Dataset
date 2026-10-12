# YOROSIX Cooperation Dataset v6.3 (synthetic)

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Data: synthetic](https://img.shields.io/badge/data-synthetic-orange.svg)]()

A **synthetic** cooperation network of 1,000 nodes, generated with the YOROSIX synthetic generator v6.3 to match the schema of the YOROSIX request-and-reply platform (requests, replies, shares, thanks, and browsing behaviour). It is meant for developing and testing methods for cooperation data: routing, propagation, labelling and quality checks.

> **Read this first.** No record in this dataset is a real user or a real event. The cooperation labels and the propagation structure are produced by the generator. Results obtained on this dataset say how a method behaves on the generator's model of cooperation, not how real people cooperate.

---

## What is in it

| File | Contents |
|---|---|
| `data/ml_node_features_v6_3.csv` | 1,000 nodes × 14 behavioural features (activity counts, dwell time, scroll rate, thanks) |
| `data/ml_edge_list_v6_3.csv` | 33,165 directed edges (`source`, `target`) |
| `data/ml_node_label_dataset_v6_3.csv` | Binary label `label_node_expand` (30.8% positive) |
| `data/bdf_f1pple_score_v0.3.csv` | Ripple score per node (0–1) |
| `data/gnn_expand_prob_v6_3.csv` | Expansion probability and rank from a GNN trained on this dataset |
| `data/bdc_action_sequence_v6-3.json` | 44,264 time-stamped actions (500 posts, 6,471 replies, 26,694 shares, 10,599 thanks) over a simulated week |
| `examples/` | Two notebooks: team selection for multi-robot coordination, and cascade simulation |

Column definitions are in [`data/README_DATA.md`](data/README_DATA.md).

## About the reported GNN score

A GNN trained on this dataset reaches AUC-ROC 0.99 on `label_node_expand`. **This number is not a measure of real-world predictive accuracy.** The labels are generated from quantities that also appear among the features, so a high score mainly shows that the model recovers the generator's rule. It should not be quoted as evidence that cooperation can be predicted with 99% accuracy.

## Status of real platform data

Real platform logs are not released. The current real logs are too small and too concentrated in operator and test accounts to certify cooperation labels; see the platform data card in [quality-gates-cooperation-labels](https://github.com/kazutakahayashiyorosix/quality-gates-cooperation-labels) (`usable_as_supervised_data: false`). This synthetic release exists so that methods can be built and checked before real data is available.

## Quick start

```bash
git clone https://github.com/kazutakahayashiyorosix/YOROSIX-Cooperation-Dataset.git
cd YOROSIX-Cooperation-Dataset
pip install -r requirements.txt
jupyter notebook examples/
```

```python
import pandas as pd
nodes  = pd.read_csv("data/ml_node_features_v6_3.csv")
edges  = pd.read_csv("data/ml_edge_list_v6_3.csv")
labels = pd.read_csv("data/ml_node_label_dataset_v6_3.csv")
print(len(nodes), len(edges), labels["label_node_expand"].mean())
```

## Related work

- Quality gates for cooperation-mode labels (code and preprint): https://github.com/kazutakahayashiyorosix/quality-gates-cooperation-labels
- Passive Behavioral Tracing (code and preprint): https://github.com/kazutakahayashiyorosix/passive-behavioral-tracing
- Ripple structures (simulation code): https://github.com/kazutakahayashiyorosix/Ripple_Structures_and_Behavioral_Digital_Twins

## Citation

```bibtex
@misc{hayashi2026yorosixsynthetic,
  title  = {YOROSIX Cooperation Dataset v6.3 (synthetic)},
  author = {Hayashi, Kazutaka},
  year   = {2026},
  note   = {Synthetic dataset},
  url    = {https://github.com/kazutakahayashiyorosix/YOROSIX-Cooperation-Dataset}
}
```

## License and contact

Free for research and non-commercial use under [CC BY-NC-SA 4.0](LICENSE). For other uses, contact Kazutaka Hayashi, YOROSIX, Osaka, Japan (kazutaka.hayashi@yorosix.com).

## Changes

- **2026-10-12** — README corrected. The earlier README described this dataset as collected from a real-world platform, called it the world's first large-scale cooperation dataset, and presented the GNN's AUC as prediction accuracy. All three statements were wrong: the data is synthetic and the AUC reflects recovery of the generator's rule. The data files themselves are unchanged.
