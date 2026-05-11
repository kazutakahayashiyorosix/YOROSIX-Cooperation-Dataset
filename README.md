# YOROSIX Cooperation Dataset v6.3

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)
[![Status](https://img.shields.io/badge/status-research-orange.svg)]()

**World's first large-scale cooperation behavior dataset** with 99.14% AUC-ROC prediction accuracy.

A 1000-node cooperation network from real-world problem-solving platform with behavioral digital twins and ripple propagation structures.

---

## What is this?

YOROSIX is building **Layer-0 Cooperation Intelligence Infrastructure** — the foundational data layer for AI systems to understand and predict human cooperation.

This dataset enables:

- **Robot Cooperation**: Train social intelligence for multi-robot coordination
- **Physical AI**: Provide "social brain" data for embodied AI systems
- **Social Simulation**: Model organizational cascade dynamics
- **Policy Simulation**: Predict cooperation propagation under policy changes
- **Risk Prediction**: Financial/organizational collapse forecasting

---

## Dataset Overview

This release contains a 1000-node cooperation network with the following files:

| File | Description | Size |
|------|-------------|------|
| `ml_node_features_v6_3.csv` | Node feature vectors (14 dimensions) | ~120 KB |
| `ml_edge_list_v6_3.csv` | Network edges and connection weights | ~325 KB |
| `ml_node_label_dataset_v6_3.csv` | Binary labels for expansion prediction | ~10 KB |
| `bdf_f1pple_score_v0_3.csv` | F1-Ripple collaboration scores (0-1) | ~15 KB |
| `bdc_action_sequence_v6-3.json` | Temporal action sequences | ~4.5 MB |
| `gnn_expand_prob_v6_3.csv` | GNN-predicted expansion probabilities | ~19 KB |

---

## Performance Metrics

The GNN model trained on this dataset achieves:

- **AUC-ROC**: 0.9914
- **Accuracy**: 0.9672
- **Robust** across multiple network topologies (scale-free, small-world, random)

For full technical details, see our papers (in progress):
- NeurIPS 2026: Ripple Cascade Prediction with GNN
- AIES 2026: Ethical Framework for Cooperation Intelligence
- Communications AI & Computing: Layer-0 Framework
- ACM TIST: Systems & Deployment

---

## Use Cases

### 1. Robot Cooperation Training

Use BDT features and ripple scores to train robots for natural team coordination. See `examples/robot_cooperation.ipynb`.

### 2. Social Simulation

Model how cooperation propagates through organizations or networks. See `examples/social_simulation.ipynb`.

### 3. Risk Prediction

Predict organizational collapse, financial cascades, or policy impacts.

---

## Quick Start

```bash
# Clone repository
git clone https://github.com/yorosix/YOROSIX-Cooperation-Dataset.git
cd YOROSIX-Cooperation-Dataset

# Install dependencies
pip install -r requirements.txt

# Run examples
jupyter notebook examples/
```

```python
import pandas as pd

# Load the data
nodes = pd.read_csv('data/ml_node_features_v6_3.csv')
edges = pd.read_csv('data/ml_edge_list_v6_3.csv')
labels = pd.read_csv('data/ml_node_label_dataset_v6_3.csv')
ripple_scores = pd.read_csv('data/bdf_f1pple_score_v0_3.csv')

print(f"Nodes: {len(nodes)}")
print(f"Edges: {len(edges)}")
print(f"Cooperation rate: {labels['label_node_expand'].mean():.2%}")
```

---

## Demo Videos

- **Physical AI Integration Demo**: https://youtu.be/vAn5PLdeOUc
- **Social Simulation Demo**: https://youtu.be/7cGA1iXOiMU

---

## Academic Usage

Free for research and academic purposes under CC BY-NC-SA 4.0.

**Citation:**

```bibtex
@dataset{hayashi2026yorosix,
  title={YOROSIX Cooperation Dataset v6.3},
  author={Hayashi, Kazutaka},
  year={2026},
  publisher={YOROSIX},
  url={https://github.com/yorosix/YOROSIX-Cooperation-Dataset}
}
```

---

## Commercial Licensing

Commercial use requires enterprise license. We offer:

- **Data Licensing**: Annual access to expanded datasets
- **API Access**: Real-time cooperation prediction
- **Custom Models**: Tailored GNN models for your use case
- **Consulting**: Implementation support

**Contact**: kazutaka.hayashi@yorosix.com

---

## License

- **Academic / Research**: [CC BY-NC-SA 4.0](LICENSE)
- **Commercial**: Custom enterprise license (contact us)

---

## About YOROSIX

YOROSIX builds **Layer-0 Cooperation Intelligence Infrastructure** — combining cooperative AI, GNN-based social network analysis, and Web3 infrastructure.

Founded by Kazutaka Hayashi, who has spent 15 years researching cooperative behavior and social network dynamics.

**Vision**: Make cooperation intelligence as fundamental as the internet.

---

## Contact

**Kazutaka Hayashi**, Founder & CEO
Email: kazutaka.hayashi@yorosix.com

---

## Acknowledgments

This dataset is derived from the YOROSIX cooperation platform, where users solve problems together and generate cooperation behavior data through DAO-style interactions.

We thank the YOROSIX community for their participation.

---
