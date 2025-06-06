# Multi-layer Social Network Consensus Data Set

This repository provides data sets and examples for evaluating consensus-reaching models on multi-layer social networks. The data includes synthetic and real-world inspired network structures, as well as corresponding initial opinions and emotions of decision-makers.

---

## 📁 Directory Overview

- `Illustrative Example/`:  
  Contains one example data set used for demonstrating the consensus-reaching process. It includes:
  - A `_data.pkl` file with initial opinions and emotions of all decision-makers.
  - A `_multilayer_network.npz` file with the adjacency matrices of the multi-layer social network.

- `Comparison Experiment/`:  
  Includes three benchmark data sets representing different real-world inspired multi-layer social networks used in comparison experiments. Each data set has:
  - A `_data.pkl` file storing initial opinions and emotions.
  - A `_multilayer_network.npz` file storing the network structure.

---

## 📄 File Format

### 1. Initial Opinions and Emotions (`*_data.pkl`)

Each `.pkl` file stores a dictionary with two keys:
- `"opinions"`: a NumPy array of shape `(num_layers, num_experts, num_alternatives, num_aspects)`  
- `"emotions"`: a NumPy array of shape `(num_layers, num_experts)` (values range from -1 to 1)

#### Example loading code:
```python
import pickle

# Load the data file
with open(data_name + "_data.pkl", "rb") as f:
    data = pickle.load(f)

# Extract opinion and emotion data of all decision makers
opinions = data["opinions"]
emotions = data["emotions"]
```

### 2. Multi-layer Network Structure (`*_multilayer_network.npz`)

Each `.npz` file contains adjacency matrices for a multi-layer social network.  
Each layer is stored as a separate 2D NumPy array representing the adjacency matrix of that layer.

- `adj_layer_0`: adjacency matrix for layer 0  
- `adj_layer_1`: adjacency matrix for layer 1  
- ...  
- `adj_layer_L`: adjacency matrix for layer L

#### Example loading code:
```python
import numpy as np

# Load the multi-layer network file
data = np.load(data_name + "_multilayer_network.npz")

# Extract all adjacency matrices in order
adj_matrices = [data[f"adj_layer_{i}"] for i in range(len(data.files))]
```

---
## 📬 Contact & Citation

If you have any questions regarding the data set or encounter any issues using it, feel free to contact us:

- 📫 **Contact**: 230239729@seu.edu.cn

If you use this data set in your research, please cite the following paper:

> **Dynamic Consensus Model for Large-scale Group Decision-making Considering the Co-evolution of Opinions and Emotions in Multi-layer Social Network**  
> Zhengyi An, et al.  

### BibTeX citation:
```bibtex
@article{An20XXDynamic,
  title   = {Dynamic Consensus Model for Large-scale Group Decision-making Considering the Co-evolution of Opinions and Emotions in Multi-layer Social Network},
  author  = {Zhengyi An, Xianghui Hu and Yichuan Jiang},
  journal = {XXXXXX},
  year    = {20XX}
}
