
# 🏥 BD Academy — Training Recommendation System
> Hybrid NLP recommendation pipeline for personalized healthcare training  
> *Capstone Project — Prototype v0.8*

---

## 🎯 Project Goal

BD Academy needed a way to automatically recommend the right training modules to healthcare professionals (HCPs) across Europe — matching each person's role, specialty, language, skill level, and training objective to the most relevant modules in their catalogue.

This project delivers an **end-to-end recommendation pipeline** combining TF-IDF, SBERT semantic embeddings, rule-based boosters, and MMR re-ranking to produce ranked, diverse, and interpretable recommendations for each HCP profile.

---

## ⚙️ How the Pipeline Works
```
HCP Profile (CSV)
      ↓
Text Preprocessing & Feature Extraction
      ↓
TF-IDF + LSA Similarity (35%) + SBERT Semantic Similarity (65%)
      ↓
Score Fusion + 7 Rule-Based Boosters
(language, domain, OPCO, skill, contract, format, duration penalty)
      ↓
MMR Re-Ranking (diversity enforcement)
      ↓
Top-5 Ranked Recommendations
```

---

## 📊 Evaluation Results

| Metric | Score |
|---|---|
| Precision@5 | **0.8478** |
| NDCG@5 | **0.7561** |
| ILD (Diversity) | 0.3486 |
| Catalogue Coverage | 47% |

---

## 🧪 Test Cases (v0.8)

| ID | Profile | Verdict | Top Score |
|---|---|---|---|
| TC-01 | French Physician — PICC Line | ✅ PASS | 0.6350 |
| TC-02 | German Pharmacist — Pyxis ES | ✅ PASS (Best Case) | 0.6504 |
| TC-03 | UK ICU Nurse — TTM | ⚠️ PARTIAL PASS | 0.8903 |
| TC-04 | UK ICU Specialist — Vague objective | 🔶 FRAGILE (Expected) | 0.4949 |
| TC-05 | Italian System Manager — Vacutainer | ⚠️ PARTIAL PASS | 0.4807 |

---

## 📂 Repository Structure
```
bd-academy-recommendation-system/
├── BD_last_Pipeline.ipynb                 # Main pipeline notebook
├── BD_Dataset1_Training_Modules_v3.csv    # Training module catalogue
├── BD_Dataset2_HCP_Profiles_v3.csv        # HCP profiles
├── BD_Prototype_v0_8_TestCases.pdf        # Test cases & status report
└── README.md
```

---

## 🛠️ Tech Stack

| Tool | Role |
|---|---|
| **Python** | Core language |
| **Sentence-BERT (SBERT)** | Semantic similarity embeddings |
| **TF-IDF + LSA** | Keyword-based similarity (offline fallback) |
| **scikit-learn** | Feature engineering, cosine similarity |
| **pandas / numpy** | Data processing |
| **MMR** | Diversity re-ranking |

---

## 🚀 How to Run
```bash
git clone https://github.com/isidmohand-netizen/bd-academy-recommendation-system.git
cd bd-academy-recommendation-system
pip install sentence-transformers scikit-learn pandas numpy
jupyter notebook BD_last_Pipeline.ipynb
```

---

## 👤 Author

**Idir Sid Mohand** — MSc MDAI, Grenoble  
[GitHub](https://github.com/isidmohand-netizen)
```

---

Copy everything, paste it in the editor, then commit with:
```
Update README with project overview and results
