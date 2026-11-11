<div align="center">

# Bilal Bounadja

**ML / AI Engineer · NLP & RAG · Data Scientist**

MSc Robotics & AI — Sorbonne Université (2023)

[![LinkedIn](https://img.shields.io/badge/LinkedIn-24292f?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bilal-bounadja-data/)
[![Email](https://img.shields.io/badge/Contact-24292f?style=flat-square&logo=gmail&logoColor=white)](mailto:bilal.bndj@gmail.com)

</div>

I build machine-learning systems end to end — from data and models to evaluation, APIs and tests — with a focus on **language models, retrieval and trustworthy answers**. I care about measuring what works: baselines, honest metrics and documented limitations.

<p align="center">
  <a href="https://github.com/Corrosifu/RAG_Fact_Checking/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/Corrosifu/RAG_Fact_Checking/ci.yml?branch=main&style=flat-square&label=CI&labelColor=24292f" alt="CI status"></a>
  <img src="https://img.shields.io/badge/tests-118-2da44e?style=flat-square&labelColor=24292f" alt="118 tests">
  <img src="https://img.shields.io/badge/runs%20on-CPU-0969da?style=flat-square&labelColor=24292f" alt="Runs on CPU">
  <img src="https://img.shields.io/badge/local%20LLM-no%20API%20key-8250df?style=flat-square&labelColor=24292f" alt="Local LLM, no API key">
</p>

<p align="center">
  <img src="img/rag-demo.gif" alt="Demo: a local model answers a question and each sentence is checked against the sources" width="640"><br>
  <sub>RAG Fact-Checking — a local model answers, then every sentence is checked against the sources.</sub>
</p>

---

## Featured projects

| Project | What it shows | Stack |
|---|---|---|
| [**RAG Fact-Checking**](https://github.com/Corrosifu/RAG_Fact_Checking) (2025) | Retrieval-augmented QA over arXiv papers that **checks its own answers** against the sources; runs on CPU | Python · BM25 + dense retrieval · NLI · FastAPI · Streamlit · Docker · pytest · CI |
| [**Spam Detection: from heuristics to transformers**](https://github.com/Corrosifu/Spam_Detection) (2025) | Heuristic, Bayesian, classical-ML and transformer methods compared on CEAS-08, up to fine-tuned DistilBERT | scikit-learn · XGBoost · Hugging Face Transformers |
| [**COVID-19 case prediction**](https://github.com/Corrosifu/covid19_diagnosis) (2024) | Tabular ML on incomplete clinical data: imputation, SMOTE, recall-oriented evaluation | pandas · scikit-learn · XGBoost |
| [**Adversarial examples (paper reproduction)**](https://github.com/Corrosifu/Projet_MLA) (2025) | Re-implementation of Goodfellow et al. (FGSM) and a robustness comparison, with the parts that did not work documented | TensorFlow / Keras |

---

## RAG Fact-Checking — flagship project

**Problem.** Small local language models write fluent answers that are sometimes not backed by their sources. This system answers questions about scientific papers *and* tells you which sentences of the answer are confirmed by the evidence.

**How it works**

<p align="center">
  <a href="img/rag-architecture.png"><img src="img/rag-architecture.png" alt="Architecture: build the knowledge base, ask a question with answer verification, fact-check a claim" width="900"></a>
</p>

- **Ingestion:** arXiv API → documents → word-window chunks.
- **Hybrid retrieval:** BM25 + dense embeddings, fused with Reciprocal Rank Fusion; optional cross-encoder reranking.
- **Generation:** extractive fallback (no model) or a small local LLM (Qwen2.5-0.5B) on CPU.
- **Verification:** an NLI model checks each sentence of the answer, and any user claim, against short evidence windows; it returns the exact supporting or contradicting sentences. Conflicting evidence yields *not enough info* instead of a guess.
- **Engineering:** installable package, CLI, FastAPI service, Streamlit UI, Docker, **118 tests**, linting and CI.

**What I learned by testing on real papers** (and fixed)

- Feeding whole PDF chunks to the NLI model produced confident wrong verdicts (a true claim refuted at 84 %); switching to sentence-level evidence windows removed them.
- On a 0.5B generator, the verifier flagged 5 of 6 sentences of a partly invented answer and confirmed 2 of 2 sentences of a faithful one.
- Limits are documented in the repo: small hand-checked samples, not a benchmark. Next step: evaluate on a public scientific claim-verification dataset.

<p align="center">
  <a href="img/rag-fact-check.png"><img src="img/rag-fact-check.png" alt="Fact-check result: SUPPORTED, with the exact evidence sentences and their NLI probabilities" width="560"></a><br>
  <sub>Fact-check tab: verdict plus the exact evidence sentences, with their sources and probabilities.</sub>
</p>

---

## Other projects

### Spam detection — from heuristics to DistilBERT (2025)
Compared frequency heuristics, Naive Bayes, KNN, logistic regression, random forest, XGBoost and a fine-tuned DistilBERT on a 4,000-email sample of CEAS-08 (single 80/20 split, F1 as the main metric).

| Model | F1 (text only) | F1 (text + extra features) |
|---|---|---|
| KNN | 0.80 | 0.76 |
| Logistic regression | 0.98 | 0.97 |
| Random forest | 0.98 | 0.99 |
| XGBoost | 0.98 | 0.98 |
| DistilBERT (fine-tuned) | 0.995 | 0.996 |

<p align="center">
  <img src="img/spam-confusion-matrix.png" alt="Confusion matrix of the DistilBERT model: 344 and 452 correct, 4 false positives, 0 false negatives" width="420">
</p>

Confusion matrix of the DistilBERT model (text + extra features) on 800 test emails: no spam missed, 4 legitimate emails flagged.

Fine-tuned DistilBERT is the most accurate but the most expensive to train and serve. Caveat documented in the repo: it starts from a checkpoint already tuned on spam data, and the scores come from a single split.

### COVID-19 case prediction from routine lab tests (2024)
Predicted RT-PCR positivity from laboratory results of the Hospital Israelita Albert Einstein dataset: dropped columns with over 90 % missing values, imputed the rest, rebalanced the classes with SMOTE, and compared Random Forest, SVM, XGBoost, KNN, logistic regression and stacking.

| Accuracy | Recall | AUC | KS |
|---|---|---|---|
| 0.909 | 0.706 | 0.824 | 0.648 |

<p align="center">
  <img src="img/covid-feature-importance.png" alt="Feature importance of the tree-based model; the engineered has_disease feature ranks first" width="520">
</p>

Limits: small test set, heavy missingness, no external validation.

### Adversarial examples — reproducing Goodfellow et al. (2025)
Re-implemented the Fast Gradient Sign Method and showed that an RBF network is more robust than linear models. The GoogLeNet / Tiny-ImageNet experiment could not be reproduced and is documented as such.

---

## Experience

### Data science intern — Jaeger-LeCoultre (2023) · supply-chain forecasting
Built demand-forecasting models (XGBoost, Random Forest, LSTM) on multi-source data (BigQuery, SQL Server), with business units defining use cases and KPIs.
**Result:** best model XGBoost, improving the weighted MAPE (wMAPE) by 45 % compared with the business teams' own forecasts.

### Research intern — Sorbonne Université (2022) · reinforcement learning for autonomous parking
Literature review of model-based RL; implemented a bicycle-model parking problem in HighwayEnv and compared LQR, DDPG and DQN controllers.

### Project — TurtleBot autonomous racing (2022)
ROS + Gazebo: LIDAR/camera/IMU fusion, OpenCV colour detection, PID tuning for obstacle avoidance and trajectory tracking.

---

## Skills

![Python](https://img.shields.io/badge/Python-24292f?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-24292f?style=flat-square&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-24292f?style=flat-square&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-24292f?style=flat-square&logo=scikitlearn&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging%20Face-24292f?style=flat-square&logo=huggingface&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-24292f?style=flat-square&logo=fastapi&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-24292f?style=flat-square&logo=docker&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-24292f?style=flat-square&logo=microsoftazure&logoColor=white)
![BigQuery](https://img.shields.io/badge/BigQuery-24292f?style=flat-square&logo=googlebigquery&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-24292f?style=flat-square&logo=postgresql&logoColor=white)
![Git & CI](https://img.shields.io/badge/Git%26CI-24292f?style=flat-square&logo=git&logoColor=white)

- **ML & NLP:** classical ML (XGBoost, random forests), transformers fine-tuning, retrieval (BM25, dense, reranking), NLI-based verification, evaluation
- **Engineering:** packaging, testing (pytest), CI, REST APIs, containers, deployment on Azure
- **Data:** pandas, SQL (BigQuery, SQL Server), time-series forecasting, Power BI
- **Also:** reinforcement learning, computer vision (OpenCV), ROS / Gazebo, C / C++, LaTeX

## Education
- **MSc Robotics & Artificial Intelligence (SAR)** — Sorbonne Université, 2023
