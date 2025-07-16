# Graph-spa: A Spatiotemporal Graph Neural Network based framework for ARDS Prediction and Interpretability

This repository contains code and experiments for training and evaluating a spatiotemporal graph neural network model on three large-scale ICU datasets: **HiRID**, **MIMIC-IV**, and **eICU-CRD**. The work aims to predict acute ARDS onset and supports interpretability through attribution mask generation.

---

## 📁 Repository Structure

### `/training`
Notebooks and scripts for training baseline and denoising autoencoder (DAE) variants of the model on each dataset.

- `01a_HiRID_baseline.ipynb`, `01b_HiRID_dae.ipynb`: HiRID training
- `02a_MIMIC_baseline.ipynb`, `02b_MIMIC_dae.ipynb`: MIMIC-IV training
- `03a_EICU_baseline.ipynb`, `03b_EICU_dae.ipynb`: eICU training
- `04_extval_MIMIC_EICU.ipynb`, `05_extval_EICU_MIMIC.ipynb`: External validation notebooks
- `layer.py`, `net.py`, `loader.py`: baseline model architecture and data loading
- `layer_dev.py`, `net_dev.py`: Dynamic adjacency version
- `mimicandeicufeatures.txt`: Feature list used for MIMIC and eICU processing

---

### `/results`
Notebooks to generate all figures and statistical analyses reported in the paper.

#### 📊 Main Figures

- `01_Fig2a_plot_hirid.ipynb`, `02_Fig2b_plot_mimic4.ipynb`, `03_Fig2c_plot_eICU.ipynb`: Dataset-specific performance plots
- `04_Fig3a_adjacencyplots.ipynb`, `04_Fig3bc_plot.ipynb`: Adjacency Comparison
- `05_Ablation_statistical_analysis.ipynb`: Statistical comparisons for ablation experiments
- `06_Fig4ab_Attribution_Masks.ipynb`, `06_Figure4cde_HiRID_attribution_plot.ipynb`: Attribution mask visualizations
- `07_Fig05a_HiRID.ipynb`, `07_Fig05b_MIMIC.ipynb`, `07_Fig05c_eICU.ipynb`: Co-occurrence analysis.

#### 🧪 Extended Figures and Supplement

- `08_FigS01a_plot_mimic_eicu.ipynb`, `09_FigS01b_plot_eicu_mimic.ipynb`: Supplementary external validation plots
- `10_FigS02_mimic_eicu_attribution_plot.ipynb`, `11_MIMIC_and_eICU_Attribution_Masks.ipynb`: Additional attribution mask insights

---
## 📦 Data Access Instructions

---

### 🔁 Results Reproducibility

To reproduce all result figures in `/results`:

1. **Download** the precomputed result files from Zenodo:  
   👉 [https://zenodo.org/records/15924818](https://zenodo.org/records/15924818)  
2. **Extract** the archive into the `results/` folder of this repository.
3. **Run** the jupyter notebooks to generate the plots.

---

### 🧪 Training Data Preparation

To run the `/training` notebooks you need the raw ICU time‑series:

- **HiRID, MIMIC‑IV, eICU‑CRD**  
  Available on PhysioNet [https://physionet.org/](https://physionet.org/) (credentialed access required).  
- **MIMIC‑IV & eICU‑CRD**  
  After download, preprocess with the METRE pipeline [https://github.com/weiliao97/METRE](https://github.com/weiliao97/METRE) to extract and normalize features.

---

### 📌 Dependencies

This repository is implemented using **Python 3.11.5** and requires the packages in requirements.txt:

Install all requirements using:

```bash
pip install -r requirements.txt
```

### 🔍 Contact

For questions or collaboration inquiries, please contact:

**Shashank Yadav**  
PhD Candidate, University of Arizona  
Email: [shashank@arizona.edu]
