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
├── src/                         # Core dataset & model code
│
├── notebooks/
│   ├── 01_data_exploration.ipynb
│   ├── 02_training_models.ipynb
│   ├── 03_sequence_inference.ipynb
│
├── models/
│   ├── configs/                 # JSON configs (10 architectures)
│   │   ├── config_GRU_64.json
│   │   ├── config_GRU_64_128.json
│   │   ├── ...
│   │
│   ├── trained_models/          # Final models (train/test)
│   │   ├── GRU_64/
│   │   ├── GRU_64_128/
│   │   ├── ...
│   │
│   └── trained_models_cv/       # NEW: Cross-Validation models
│       ├── fold_1/
│       ├── fold_2/
│       ├── fold_3/
│       ├── fold_4/
│       └── fold_5/
│
├── docs/
│   ├── figures/                 # Plots (600 dpi)
│   ├── performance/             # CSV performance logs
│   │   ├── PERFORMANCE_LSM_MODELS.csv
│   │   └── PERFORMANCE_LSM_MODELS_CV.csv
│   ├── dataset_dictionary.pdf
│   └── pipeline_diagram.png
│
├── data/
│   ├── dictionary/
│   ├── raw/                     # Master CSV
│   ├── raw_npy/                 # Full dataset (ignored in Git)
│   └── sample_npy/              # Demo subset
│   └── original_source/
│   └── cases/
│
├── CITATION.cff
├── LICENSE
└── README.md
```

## 🧾 Dataset Metadata (ES/EN)
MSL-150 Dataset v1.0 compiles core and domain-specific Mexican Sign Language (LSM) vocabulary organized by semantic categories. The dataset provides frame-level body and hand keypoints extracted with MediaPipe Holistic and includes synthetic samples to balance classes and enable reproducible research. This section documents categories, counts, variables, and the column schema (RH/LH/POSE) used for processing and analysis

 Category | Quantity | Spanish Vocabulary | English Vocabulary |
|---|---:|---|---|
| Basic Signs | 6 | sí, no, pregunta, duda, bien, mal | yes, no, question, doubt, good, bad |
| Adjectives | 10 | duro, suave, normal, frío, caliente, mejor, peor, estresado, rápido, lento | hard, soft, normal, cold, hot, better, worse, stressed, fast, slow |
| Days of the Week | 7 | lunes, martes, miércoles, jueves, viernes, sábado, domingo | Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday |
| Animals | 5 | perro, gato, camarón, pollo, abeja | dog, cat, shrimp, chicken, bee |
| Emotions | 2 | cansado, confundido | tired, confused |
| Time | 7 | ayer, ahora, hoy, mañana, nunca, siempre, diario | yesterday, now, today, tomorrow, never, always, daily |
| People | 6 | mamá, papá, esposo, esposa, hijo, hija | mom, dad, husband, wife, son, daughter |
| Months | 12 | enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre | January, February, March, April, May, June, July, August, September, October, November, December |
| Numbers | 10 | 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 | 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 |
| Questions | 4 | cómo, cuántos, para qué, por qué | how, how many, for what, why |
| Pronouns | 1 | yo | I |
| Verbs | 14 | beber, cocinar, recibir, estudiar, interpretar, ir, no ver, dormir, pelear, trabajar, descansar, comer, correr, caminar | drink, cook, receive, study, interpret, go, not see, sleep, fight, work, rest, eat, run, walk |
| Medical | 47 | ambulancia, jarabe, virus, aborto, accidente, hospital, doctor, enfermera, paciente, dolor, enfermo, terapia, pastillas, inyección, contagiar, revisar, calentura, cáncer, infección, infarto, lesión, embarazo, sangre, gripa, garganta, tos, débil, huesos, farmacia, emergencia, inflamación, análisis, coronavirus, cita, fractura, urgencia, orina, popó, mareo, vómito, convulsiones, gases, diarrea, moco, sed | ambulance, syrup, virus, abortion, accident, hospital, doctor, nurse, patient, pain, sick, therapy, pills, injection, infect, check, fever, cancer, infection, heart attack, injury, pregnancy, blood, flu, throat, cough, weak, bones, pharmacy, emergency, inflammation, analysis, coronavirus, appointment, fracture, urgency, urine, stool, dizziness, vomiting, convulsions, gas, diarrhea, mucus, thirst |
| Body Parts | 19 | ojo, nariz, oreja, boca, cuello, hombro, espalda, brazo, codo, muñeca, mano, panza, cintura, pene, vagina, piernas, rodilla, tobillo, pie | eye, nose, ear, mouth, neck, shoulder, back, arm, elbow, wrist, hand, belly, waist, penis, vagina, legs, knee, ankle, foot |Variables and Column Schema
Minimal identifiers and metadata:

VIDEO_SAMPLE, CLASSIFICATION, FRAME, TIMESTAMP (ms)
Note: Some original headers preserve VIDEO_SAMPLE  with a trailing space for backward compatibility.


Right Hand (RH):

21 landmarks × 3 coordinates: RIGHT_<LANDMARK_NAME>_{X,Y,Z}
<LANDMARK_NAME> follows MediaPipe HandLandmark enum (e.g., WRIST, THUMB_CMC, …, PINKY_TIP).


Left Hand (LH):

21 landmarks × 3 coordinates: LEFT_<LANDMARK_NAME>_{X,Y,Z}


Pose (body):

25 selected landmarks (excluding indices 25–32) × 4 values: <POSE_NAME>_{X,Y,Z,V}, where V = visibility (0–1).


Per-row totals (approx.):
Keypoints per frame: 63 (RH) + 63 (LH) + 100 (Pose) = 226
Columns per row: 4 base + 226 keypoints = 230
Process Description
Acquisition and sources:

Vocabulary and categories established from the internal dictionary and the functional taxonomy (14 categories).


Keypoint extraction:

MediaPipe Holistic v0.10; per-frame export of hand and body keypoints.
If a detection is missing, zeros are imputed to preserve dimensionality.


Sample generation:

Full set includes synthetic data to balance classes and ensure reproducibility.


Quality control:

Optional visual QA by overlaying landmarks.
Safe resume of processing to avoid duplicates using VIDEO_SAMPLE.


Scope and Intended Use
Academic research in computer vision and sign linguistics: vocabulary classification, sign recognition, hand/body kinematics, and phonological variation.
Ethics and Privacy
Samples are anonymized and/or synthetically derived for research purposes. Responsible use and respect for Deaf communities and LSM users are encouraged

## ⚙️ Technical Summary
- Total Samples: 120,000
- Frames per Sample: 30
- Keypoints per Frame: 226
- Tensor Shape: 120000 × 30 × 226
- Augmentation:rotation, illumination changes, temporal speed variation, Gaussian noise
- Models Evaluated:
    LSTM
    GRU


## 📚 How to Cite
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
## 🧩 Contact
For questions, dataset issues, or collaboration opportunities:

Armando de Jesús Becerril Carrillo
Universidad Anáhuac México Norte
ORCID: https://orcid.org/0009-0004-4420-1442

