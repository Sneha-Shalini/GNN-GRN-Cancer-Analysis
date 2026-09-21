# Gene Regulatory Network Analysis for Cancer Using Graph Neural Networks (GNN)

> Modeling Gene Regulatory Networks as graphs to identify cancer driver genes using Graph Neural Networks | TCGA | PyTorch Geometric

### 🔬 Overview
Cancer arises from dysregulation of complex gene interactions. This project constructs a Gene Regulatory Network (GRN) where **genes are nodes and regulatory interactions are edges**, and applies Graph Neural Networks to learn non-linear regulatory patterns for cancer driver gene prediction.

**Domain:** Cancer Genomics, Systems Biology, Graph Deep Learning

### ❓ Problem Statement
Traditional ML (Random Forest, SVM) treats genes as independent features and ignores network topology. GNNs can leverage both **gene expression (node features)** and **regulatory topology (graph structure)** to improve cancer gene prediction.

### 📊 Dataset
- **Source:** TCGA-BRCA (Breast Invasive Carcinoma) RNA-Seq
- **Nodes:** ~2,500 genes (Transcription Factors + Target Genes)
- **Edges:** Regulatory interactions from TRRUST v2 & STRING DB
- **Node Features:** Normalized gene expression (FPKM)

### ⚙️ Methodology

**1. GRN Construction**
- Extracted DEGs from TCGA tumor vs normal
- Built adjacency matrix from TRRUST + co-expression correlation

**2. Graph Representation**
- Graph: `G = (V, E)` where V = genes, E = regulatory links
- Node feature matrix: `X` [genes x expression samples]

**3. GNN Model Architecture**

**4. Training & Evaluation**
- 5-Fold Cross Validation
- Loss: Binary Cross-Entropy, Optimizer: Adam (lr=0.001)
- Metrics: Accuracy, F1-Score, AUROC, AUPRC

### 📈 Key Results
| Metric | Score |
|--------|-------|
| Accuracy | 89.2% |
| AUROC | 0.91 |
| F1-Score | 0.87 |

**Top Predicted Hub Genes:** TP53, MYC, BRCA1, FOXA1, GATA3 - validated as known breast cancer drivers.

### 🛠️ Tech Stack
`Python | PyTorch Geometric | NetworkX | Pandas | NumPy | Scikit-learn | Matplotlib`

### 📁 Repository Structure
