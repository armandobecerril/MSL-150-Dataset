# MSL-150: Mexican Sign Language (MSL) Keypoint Dataset for Domain-Specific Vocabulary

**MSL-150** is a public **keypoint-only** dataset of **150 Mexican Sign Language (MSL)** signs,
processed with **MediaPipe Holistic** and curated to support **reproducible research** in:

- Sign language recognition  
- Keypoint-based gesture modeling  
- Sequence learning and grammar-level interpretation  

This dataset accompanies the research:  
**“Recurrent Neural Networks for the Interpretation of Mexican Sign Language in Domain-Specific Communication Scenarios.”**

---

## 📦 Dataset Contents (Zenodo)

The complete dataset is hosted on Zenodo under DOI:  
👉 **https://doi.org/10.5281/zenodo.17783312**

The Zenodo archive includes:

- **MSL-150_Mexican_Sign_Language_Dataset.csv**  
  226 keypoints × 30 frames per sequence × 120,000 sequences

- **npy_samples_full/ (120,000 .npy files)**  
  One `.npy` file per frame (30 per sample), organized by class and sample index  

- **dataset_dictionary.pdf**  
  Variable descriptions and metadata

- **trained_model_v1.h5**  
  Final GRU model used in the publication

- **model_config.json**  
  Model architecture, hyperparameters, and preprocessing information

All samples were extracted using **MediaPipe Holistic v0.10** under controlled recording conditions.

---

## 🧪 Representative Sample Included in This Repository

To allow reviewers and users to test the full code **without downloading 14+ GB**, this repository includes a **small representative subset**:

data/sample_npy/
-  ambulancia/
-  dolor/
-  doctor/
-  hoy/
-  yo/


Each folder contains **one sequence** (30 frames → 30 `.npy` files) illustrating:

- folder hierarchy  
- temporal structure (sequence length = 30)  
- feature dimensionality (226 per frame)  
- expected preprocessing pipeline  

**The full dataset must be obtained from Zenodo.**

---

## 👤 Signer Information

- **1 native MSL signer**  
- **150 isolated sign classes**  
- **800 samples per class** (1 original + 799 augmented)  
- **Full HD (1080p) videos recorded at 30 FPS**  
- Controlled lighting, background, and positioning  
- **226 MediaPipe keypoints per frame**

> ⚠️ **Important:**  
> This is an **exploratory pilot dataset** and reflects a *single-signer, controlled-environment* setup.  
> It is intended solely for **reproducibility, benchmarking, and methodological comparison**, not for clinical deployment.

---

## 📂 Repository Structure

MSL-150/
├── src/                 # Core Python modules for dataset loading, model training & evaluation
│   ├── data_loader.py
│   ├── model_lstm.py
│   ├── model_gru.py
│   └── utils.py
│
├── notebooks/           # Jupyter notebooks for experiments and reproducible workflows
│   ├── 01_data_exploration.ipynb
│   ├── 02_training_LSTM.ipynb
│   └── 03_sequence_inference.ipynb
│
├── models/              # Saved models, configs, runtime logs
│   ├── trained_model_v1.h5
│   ├── model_config.json
│   └── metrics/
│
├── docs/                # Technical documentation and diagrams
│   ├── dataset_dictionary.pdf
│   └── pipeline_diagram.png
│
├── data/                # Light metadata only (⚠️ large dataset lives in Zenodo)
│   ├── samples_demo/    # 3–5 sample npy/npz files for GitHub
│   └── dictionary/
│       └── variables.json
│
├── CITATION.cff
├── README.md
└── LICENSE


---

## ⚙️ Technical Summary

- **Total Samples:** 120,000  
- **Frames per Sample:** 30  
- **Features per Frame:** 226 MediaPipe keypoints  
- **Final Tensor Shape:** `120000 × 30 × 226`  
- **Augmentation:** rotation, illumination, speed variation, Gaussian noise  
- **Models:** LSTM (64–128), GRU (64–128)  
- **Top model accuracy:**  
  - Validation accuracy: **0.9978**  
  - Test precision: **0.9957**  
  - Narrative sequential recall: **63.64%**

---

## ⚖️ License

This dataset and code are released under the **MIT License**.  
If you use this dataset, you **must** cite it.

---

## 📚 How to Cite

### **BibTeX**

```bibtex
@dataset{Becerril2025_msl150,
  author = {Armando de Jesús Becerril Carrillo},
  title = {MSL-150: Mexican Sign Language Keypoint Dataset},
  year = {2025},
  doi = {10.5281/zenodo.17783312},
  url = {https://doi.org/10.5281/zenodo.17783312}
}
