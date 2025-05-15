# Multi-layer Social Network Consensus Dataset

This repository provides datasets and examples for evaluating consensus-reaching models on multi-layer social networks. The data includes synthetic and real-world inspired network structures, as well as corresponding initial opinions and emotions of decision-makers.

---

## 📁 Directory Overview

- `Illustrative Example/`:  
  Contains one example dataset used for demonstrating the consensus-reaching process. It includes:
  - A `.pkl` file with initial opinions and emotions of all decision-makers.
  - A `.npz` file with the adjacency matrices of the multi-layer social network.

- `Comparison Experiment/`:  
  Includes three benchmark datasets representing different real-world inspired multi-layer social networks used in comparison experiments. Each dataset has:
  - A `_data.pkl` file storing initial opinions and emotions.
  - A `_multilayer_network.npz` file storing the network structure.

---

## 📄 File Format

### Initial Opinions and Emotions (`*_data.pkl`)

Each `.pkl` file stores a dictionary with two keys:
- `"opinions"`: a NumPy array of shape `(num_experts, num_alternatives, num_aspects)`  
- `"emotions"`: a NumPy array of shape `(num_experts,)` (values range from -1 to 1)

#### Example loading code:
```python
import pickle

with open(data_name + "_data.pkl", "rb") as f:
    data = pickle.load(f)

opinions = data["opinions"]
emotions = data["emotions"]
