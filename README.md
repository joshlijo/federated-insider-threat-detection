# 🛡️ Federated Insider Threat Detection using TinyBERT and FedBoost

This project implements a **federated learning framework** to detect insider threats using a hybrid of:
- ✍️ handcrafted behavioral features (logon frequency, session duration, weekend access)
- 🧠 TinyBERT-based logon sequence embeddings
- 🚀 Federated Boosting with LightGBM (FedBoost)

Designed to preserve **data privacy** and support **cross-silo collaboration** across departments, this approach simulates real-world enterprise constraints using the CERT Insider Threat Dataset v5.1.

---

## 📊 Key Results

| Metric | Federated Model (FedBoost) |
|--------|-----------------------------|
| ROC-AUC | 0.94 |
| F1-Score | 0.92 |
| Precision | High (optimized at 0.72 threshold) |
| Recall | High (low false negatives) |

- Federated model matched or outperformed centralized alternatives.
- SHAP-based interpretability validated key features.
- Ablation studies confirmed complementary value of TinyBERT + handcrafted features.

---

## 🏗️ System Architecture

1. **Data Preprocessing** (Logon, File, Decoy logs from CERT v5.1)
2. **Behavior Feature Engineering** (e.g., failed logins, session duration, weekend activity)
3. **TinyBERT Embedding Extraction** (sequence model on logon events)
4. **Feature Fusion** (combined feature vector)
5. **Federated Boosting (FedBoost)** using LightGBM
6. **Risk Scoring + Evaluation** (ROC, F1, Confusion Matrix)

> Federated simulation used 3–5 clients with prediction score aggregation over 3 rounds.

---

## 🧰 Tech Stack

- Python, Pandas, Scikit-learn
- LightGBM (FedBoost logic)
- TinyBERT (transformers from HuggingFace)
- SHAP (explainability)
- Matplotlib / Seaborn (visualization)

---

## 📁 Files

| File | Description |
|------|-------------|
| `FedBoost_TinyBERT_InsiderThreat_Detection.ipynb` | Full pipeline implementation |
| `requirements.txt` | Environment dependencies |
| `data/` | Placeholder folder for sample log files |
| `results/` | ROC, F1, PR curve visualizations |
| `docs/` | Final project report + presentation |

---

## 📂 Dataset

- **CERT Insider Threat v5.1** (public synthetic dataset from Carnegie Mellon)
- Used logs:
  - `logon.csv`
  - `file.csv`
  - `decoy_file.csv`

- User labels:
  - Malicious = 1 if user accessed a decoy file
  - Benign = 0 otherwise

---

## 🚀 Future Work

- Add email/device/web logs for multimodal behavior modeling
- Apply secure aggregation + differential privacy
- Extend to online detection with streaming logs
- Explore real-time risk scoring with LLM integration (FedLLM)

---

## 👤 Author

**Joshua Lijo Kokkadan**  
B.Tech – Computer Science (Cyber Physical Systems)  
VIT Chennai  
[Email: josh.kokkadan@gmail.com]  
