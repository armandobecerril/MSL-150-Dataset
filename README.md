# MSL-150: Mexican Sign Language (MSL) Keypoint Dataset for Domain-Specific Vocabulary

MSL-150 is a public keypoint-only dataset of 150 Mexican Sign Language (MSL) signs,
processed with MediaPipe Holistic and curated for reproducible research in:

- Sign language recognition
- Keypoint-based gesture modeling
- Sequential and grammar-level sign interpretation

This dataset forms part of the research:  
**“Recurrent Neural Networks for the Interpretation of Mexican Sign Language in Domain-Specific Communication Scenarios.”**

---

## 📦 Dataset Contents

Zenodo archive (DOI: https://doi.org/10.5281/zenodo.17783312) includes:

-  MSL-150_keypoints.csv # 226 keypoints × frames per sample
-  npz_samples/ # 120,000 npz samples (augmented)
-  dataset_dictionary.pdf # variable descriptions and metadata
-  trained_model_v1.h5 # final GRU model
-  model_config.json # architecture & hyperparameters


All samples were extracted using MediaPipe Holistic v0.10.

---

## 👤 Signer Information

- 1 native MSL signer  
- 150 isolated sign classes  
- 800 samples per class  
- Videos recorded in controlled indoor conditions  
- 226 MediaPipe keypoints per frame  

*Important:*  
This is an exploratory pilot dataset and does **not** represent signer variability.  
It is intended only for reproducibility and controlled experimentation.

---

## 📂 Repository Structure

src/ # Python code for loading, training, testing
notebooks/ # Jupyter notebooks for experimentation
docs/ # Documentation and diagrams
models/ # Model and config files
data/dictionary # Metadata and variable descriptions

---

## ⚖️ License
MIT License.  
You must cite the dataset if used in academic work.

---

## 📚 How to Cite

See `CITATION.cff` or use:

@dataset{Becerril2025_msl150,
author = {Armando de Jesús Becerril Carrillo},
title = {MSL-150: Mexican Sign Language Keypoint Dataset},
year = {2025},
doi = {10.5281/zenodo.17783312},
url = {https://doi.org/10.5281/zenodo.17783312}

}