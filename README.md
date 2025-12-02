# MSL-150: Mexican Sign Language (MSL) Keypoint Dataset for Domain-Specific Vocabulary

MSL-150 is a **public keypoint-only dataset** of 150 Mexican Sign Language (MSL) signs,
processed using **MediaPipe Holistic**, curated to support reproducible research in:

- Sign language recognition  
- Keypoint-based gesture modeling  
- Sequential and grammar-level sign interpretation  

This dataset is part of the doctoral research:  
**“Recurrent Neural Networks for the Interpretation of Mexican Sign Language in Domain-Specific Communication Scenarios.”**

---

## 📦 Dataset Contents (Zenodo, Full Version)

🔗 **Full dataset DOI:** https://doi.org/10.5281/zenodo.17783312  
⚠️ *Due to size limitations, only a small demo subset is stored in GitHub.*

Zenodo includes:

- **MSL-150_keypoints.csv** — 226 keypoints × frames per sample  
- **npz_samples/** — 120,000+ augmented samples (799 synthetic per class)  
- **dataset_dictionary.pdf** — variable and metadata glossary  
- **trained_model_v1.h5** — final GRU architecture  
- **model_config.json** — hyperparameters & training settings  

All data was extracted using **MediaPipe Holistic v0.10**.

---

## 👤 Signer Information

- **1 native MSL signer**  
- **150 isolated sign classes**  
- **800 original videos per class (full dataset)**  
- **799 augmented samples per class (full dataset)**  
- **200 sample excerpts per class included in GitHub (demo only)**  
- **Full HD (1080p) at 30 FPS**, controlled lighting and background  
- **226 MediaPipe keypoints per frame**

> ⚠️ **Important:**  
> This is an **exploratory pilot dataset** recorded from a **single signer** in a **controlled environment**.  
> GitHub contains only lightweight demo samples.  
> The complete dataset must be obtained through Zenodo.

---

## 📂 Repository Structure

```text
MSL-150/
├── src/                     # Core Python modules (loading, training, evaluation)
│   ├── data_loader.py
│   ├── model_lstm.py
│   ├── model_gru.py
│   └── utils.py
│
├── notebooks/               # Jupyter notebooks for experimentation
│   ├── 01_data_exploration.ipynb
│   ├── 02_training_LSTM.ipynb
│   └── 03_sequence_inference.ipynb
│
├── models/                  # Saved models, configs, and metrics
│   ├── trained_model_v1.h5
│   ├── model_config.json
│   └── metrics/
│
├── docs/                    # Diagrams, documentation, variable dictionaries
│   ├── dataset_dictionary.pdf
│   └── pipeline_diagram.png
│
├── data/                    # Lightweight GitHub subset (📌 NOT the full dataset)
│   ├── samples_demo/        # ~200 samples/class extracted from original dataset
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
