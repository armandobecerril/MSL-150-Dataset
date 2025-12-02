# MSL-150: Mexican Sign Language (MSL) Keypoint Dataset for Domain-Specific Vocabulary

**MSL-150** is a **public keypoint-only dataset** of *150 Mexican Sign Language (MSL) signs*,  
extracted using **MediaPipe Holistic**, designed for reproducible research in:

- Sign language recognition  
- Keypoint-based gesture modeling  
- Sequential & narrative-level sign interpretation  
- RNN/sequence models (LSTM, GRU)

This dataset is part of the doctoral research project:  
**“Recurrent Neural Networks for the Interpretation of Mexican Sign Language in Domain-Specific Communication Scenarios.”**

---

## 📦 Full Dataset (Zenodo)

🔗 **DOI:** https://doi.org/10.5281/zenodo.17783312  

⚠️ *Due to size constraints, only a small demo subset is included in GitHub.*  
The complete dataset must be obtained from **Zenodo**.

Zenodo contains:

- **MSL-150_Mexican_Sign_Language_Dataset.csv** — 13.9 GB keypoint master file  
- **npz_samples/** — 120,000+ samples (1 original + 799 augmented per class)  
- **dataset_dictionary.pdf** — description of all 226 variables  
- **trained_model_v1.h5** — final GRU sequence model  
- **model_config.json** — hyperparameters & training metadata  

All keypoints were extracted using **MediaPipe Holistic v0.10**.

---

## 👤 Signer Information

- **1 native MSL signer**  
- **150 isolated sign classes**  
- **800 video sequences per class (full dataset)**  
- **799 augmented samples per class**  
- **200 lightweight samples/class included in GitHub (demo subset)**  
- **Full HD 1080p @ 30 FPS**, uniform lighting and background  
- **226 MediaPipe keypoints per frame**

> ⚠️ **Important:**  
> MSL-150 is an **exploratory pilot dataset**, recorded from a **single signer** in a **controlled environment**.  
> The GitHub dataset is **only a lightweight demo subset**, intended for testing code and notebooks.  
> The full dataset must be retrieved from Zenodo.

---

## 📂 Repository Structure

```text
MSL-150/
├── src/                     # Core dataset & model code
│   ├── data_loader.py
│   ├── model_lstm.py
│   ├── model_gru.py
│   └── utils.py
│
├── notebooks/               # Jupyter notebooks (full pipeline)
│   ├── 01_data_exploration.ipynb
│   ├── 02_training_LSTM.ipynb
│   └── 03_sequence_inference.ipynb
│
├── models/                  # Saved models, configs, metrics
│   ├── trained_model_v1.h5
│   ├── model_config.json
│   └── metrics/
│
├── docs/                    # Documentation, diagrams, dictionaries
│   ├── dataset_dictionary.pdf
│   └── pipeline_diagram.png
│
├── data/                    # ⚠️ Lightweight GitHub subset ONLY
│   ├── samples_demo/        # ~200 samples/class extracted from the full dataset
│   └── dictionary/
│       └── variables.json
│
├── CITATION.cff
├── README.md
└── LICENSE
⚙️ Technical Summary
Total Samples: 120,000

Frames per Sample: 30

Keypoints per Frame: 226

Tensor Shape: 120000 × 30 × 226

Augmentation:

rotation

illumination changes

temporal speed variation

Gaussian noise

Models Evaluated:

LSTM (64–128)

GRU (64–128)

Best Performing Model:

Validation accuracy: 0.9978

Test precision: 0.9957

Narrative-sequence recall: 63.64%

⚖️ License
Released under the MIT License.

You may use this dataset freely for research and educational purposes.
If you use it in a publication, you must cite it.

📚 How to Cite
CITATION.cff
Located in the repository root (GitHub + Zenodo).

BibTeX Citation
bibtex
Copy code
@dataset{Becerril2025_msl150,
  author = {Armando de Jesús Becerril Carrillo},
  title = {MSL-150: Mexican Sign Language Keypoint Dataset},
  year = {2025},
  doi = {10.5281/zenodo.17783312},
  url = {https://doi.org/10.5281/zenodo.17783312}
}
🧩 Contact
For questions, dataset issues, or collaboration opportunities:

Armando de Jesús Becerril Carrillo
Universidad Anáhuac México Norte
ORCID: https://orcid.org/0009-0004-4420-1442

