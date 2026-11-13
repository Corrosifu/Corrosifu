<p align="center">
  <img src="img/banner.svg" alt="Bilal Bounadja — AI Engineer, Machine Learning, Trustworthy AI. Building reliable AI systems, from research to deployment." width="100%">
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/bilal-bounadja-data/"><img src="https://img.shields.io/badge/LinkedIn-18181b?style=flat-square&logo=linkedin&logoColor=a78bfa" alt="LinkedIn"></a>
  <a href="mailto:bilal.bndj@gmail.com"><img src="https://img.shields.io/badge/Contact-18181b?style=flat-square&logo=gmail&logoColor=a78bfa" alt="Contact"></a>
  <img src="https://img.shields.io/badge/Data%20Scientist-Sanofi-18181b?style=flat-square&logo=sanofi&logoColor=a78bfa" alt="Data Scientist at Sanofi">
  <img src="https://img.shields.io/badge/MS%20Data%20%26%20GenAI%20Engineering-EFREI%20(in%20progress)-18181b?style=flat-square" alt="MS Data and Generative AI Engineering, EFREI, in progress">
  <img src="https://img.shields.io/badge/MSc%20Robotics%20%26%20AI-Sorbonne%20%C3%97%20ENSAM%202023-18181b?style=flat-square" alt="MSc Robotics and AI, Sorbonne Université and ENSAM, 2023">
  <img src="https://komarev.com/ghpvc/?username=Corrosifu&label=Profile%20views&style=flat-square&labelColor=18181b&color=8b5cf6" alt="Profile views">
  <a href="https://github.com/Corrosifu?tab=followers"><img src="https://img.shields.io/github/followers/Corrosifu?style=flat-square&labelColor=18181b&color=8b5cf6&label=Followers&logo=github&logoColor=a78bfa" alt="GitHub followers"></a>
</p>

I build machine-learning systems end to end, with a focus on **language models, retrieval and trustworthy answers**.
I measure what works: baselines, honest metrics and documented limitations.

## Featured projects

<p align="center">
  <a href="https://github.com/Corrosifu/RAG_Fact_Checking"><img src="img/card-rag.svg" alt="RAG Fact-Checking: scientific QA over arXiv papers that verifies its own answers with NLI" width="410"></a>
  <a href="https://github.com/Corrosifu/Spam_Detection"><img src="img/card-spam.svg" alt="Spam Detection: from heuristics to fine-tuned DistilBERT, F1 from 0.72 to 0.995" width="410"></a><br>
  <a href="https://github.com/Corrosifu/Projet_MLA"><img src="img/card-adversarial.svg" alt="Adversarial ML: reproduction of Goodfellow et al. with tests; an FGSM-trained model fails under PGD" width="410"></a>
  <a href="https://github.com/Corrosifu/covid19_diagnosis"><img src="img/card-covid.svg" alt="COVID-19 Prediction: positivity from routine blood tests on incomplete data, accuracy 0.909, recall 0.706, AUC 0.824" width="410"></a>
</p>

---

<h2><a href="https://github.com/Corrosifu/RAG_Fact_Checking"><img src="img/title-rag.svg" alt="Flagship: RAG Fact-Checking" width="100%"></a></h2>

Small local language models write fluent answers that are sometimes not backed by their sources. This system answers questions about scientific papers **and shows which sentences of the answer are confirmed by the evidence**.

<p align="center">
  <a href="https://github.com/Corrosifu/RAG_Fact_Checking/actions/workflows/ci.yml"><img src="https://img.shields.io/github/actions/workflow/status/Corrosifu/RAG_Fact_Checking/ci.yml?branch=main&style=flat-square&label=CI&labelColor=18181b" alt="CI status"></a>
  <img src="https://img.shields.io/github/last-commit/Corrosifu/RAG_Fact_Checking?style=flat-square&labelColor=18181b&color=8b5cf6&label=last%20commit" alt="Last commit">
  <img src="https://img.shields.io/github/stars/Corrosifu/RAG_Fact_Checking?style=flat-square&labelColor=18181b&color=8b5cf6&label=stars" alt="GitHub stars">
  <img src="https://img.shields.io/badge/tests-146-8b5cf6?style=flat-square&labelColor=18181b" alt="146 tests">
  <img src="https://img.shields.io/badge/runs%20on-CPU-8b5cf6?style=flat-square&labelColor=18181b" alt="Runs on CPU">
</p>

<p align="center">
  <a href="img/rag-architecture.png"><img src="img/rag-architecture.png" alt="Architecture: build the knowledge base, ask a question with answer verification, fact-check a claim" width="900"></a>
</p>

**See it work** — a faithful answer confirmed, then a partly invented one flagged:

<p align="center">
  <img src="img/rag-demo.gif" alt="Demo: a local model answers a question and each sentence is checked against the sources" width="560">
</p>

<p align="center">
  <a href="img/rag-fact-check.png"><img src="img/rag-fact-check.png" alt="Fact-check result: SUPPORTED, with the exact evidence sentences and their NLI probabilities" width="520"></a>
</p>

**What testing on real papers taught me**

- Feeding whole PDF chunks to the NLI model produced confident wrong verdicts (a true claim refuted at 84 %); sentence-level evidence windows removed them.
- A single bibliography entry can break a verdict: with neural retrieval, a true claim came out inconclusive because a reference entry (title, journal, pages, year) was retrieved and the NLI model scored it 0.92 contradiction. References are now removed before indexing (616 to 476 chunks on my 10-paper corpus) and the verifier skips bibliography-like sentences. It is a heuristic tuned on that corpus.
- On a 0.5B generator, the verifier flagged 5 of 6 sentences of a partly invented answer and confirmed 2 of 2 of a faithful one. Hand-checked samples, not a benchmark: next step is a public claim-verification dataset.

[**→ Repository, documentation and limitations**](https://github.com/Corrosifu/RAG_Fact_Checking)

<details>
<summary><b>Results at a glance</b> — spam detection, COVID-19 prediction and adversarial ML</summary>

<br>

<h3><a href="https://github.com/Corrosifu/Spam_Detection"><img src="img/title-spam.svg" alt="Spam detection" width="100%"></a></h3>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/Corrosifu/Spam_Detection?style=flat-square&labelColor=18181b&color=8b5cf6&label=last%20commit" alt="Last commit">
  <img src="https://img.shields.io/github/stars/Corrosifu/Spam_Detection?style=flat-square&labelColor=18181b&color=8b5cf6&label=stars" alt="GitHub stars">
</p>

(CEAS-08, 4,000-email sample, single 80/20 split — caveats in the repository)

| Model | F1 (text only) | F1 (text + extra features) |
|---|---|---|
| KNN | 0.80 | 0.76 |
| Logistic regression | 0.98 | 0.97 |
| Random forest | 0.98 | 0.99 |
| XGBoost | 0.98 | 0.98 |
| DistilBERT (fine-tuned from a spam-tuned checkpoint) | 0.995 | 0.996 |

<p align="center">
  <img src="img/spam-confusion-matrix.png" alt="Confusion matrix of the DistilBERT model: no spam missed, 4 legitimate emails flagged" width="360"><br>
  <sub>DistilBERT on 800 test emails: no spam missed, 4 legitimate emails flagged.</sub>
</p>

<h3><a href="https://github.com/Corrosifu/covid19_diagnosis"><img src="img/title-covid.svg" alt="COVID-19 case prediction" width="100%"></a></h3>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/Corrosifu/covid19_diagnosis?style=flat-square&labelColor=18181b&color=8b5cf6&label=last%20commit" alt="Last commit">
  <img src="https://img.shields.io/github/stars/Corrosifu/covid19_diagnosis?style=flat-square&labelColor=18181b&color=8b5cf6&label=stars" alt="GitHub stars">
</p>

(Hospital Israelita Albert Einstein data): accuracy 0.909 · recall 0.706 · AUC 0.824 · KS 0.648. Limits: small test set, heavy missingness, no external validation.

<p align="center">
  <img src="img/covid-feature-importance.png" alt="Feature importance of the tree-based model; the engineered has_disease feature ranks first" width="480">
</p>

<h3><a href="https://github.com/Corrosifu/Projet_MLA"><img src="img/title-adversarial.svg" alt="Adversarial ML" width="100%"></a></h3>

<p align="center">
  <img src="https://img.shields.io/github/last-commit/Corrosifu/Projet_MLA?style=flat-square&labelColor=18181b&color=8b5cf6&label=last%20commit" alt="Last commit">
  <img src="https://img.shields.io/github/stars/Corrosifu/Projet_MLA?style=flat-square&labelColor=18181b&color=8b5cf6&label=stars" alt="GitHub stars">
</p>

(MNIST, `eps = 0.25`, [reproduction of Goodfellow et al. 2015](https://github.com/Corrosifu/Projet_MLA)): adversarial training lowers the error of a maxout network on FGSM examples from 91.9 % to 10.8 % (paper: 89.4 % to 17.9 %), but a 20-step PGD attack still reaches **98.2 %**. The model mostly learned to resist the attack it was trained on. One seed, untuned recipe; the repository lists what is and is not reproduced.

</details>

---

## Stack

**AI & ML** &nbsp; <img src="https://img.shields.io/badge/Python-18181b?style=flat-square&logo=python&logoColor=a78bfa" alt="Python"> <img src="https://img.shields.io/badge/PyTorch-18181b?style=flat-square&logo=pytorch&logoColor=a78bfa" alt="PyTorch"> <img src="https://img.shields.io/badge/TensorFlow-18181b?style=flat-square&logo=tensorflow&logoColor=a78bfa" alt="TensorFlow"> <img src="https://img.shields.io/badge/scikit--learn-18181b?style=flat-square&logo=scikitlearn&logoColor=a78bfa" alt="scikit-learn"> <img src="https://img.shields.io/badge/Hugging%20Face-18181b?style=flat-square&logo=huggingface&logoColor=a78bfa" alt="Hugging Face"> <img src="https://img.shields.io/badge/XGBoost-18181b?style=flat-square" alt="XGBoost"> <img src="https://img.shields.io/badge/RAG-18181b?style=flat-square" alt="RAG"> <img src="https://img.shields.io/badge/NLP-18181b?style=flat-square" alt="NLP">

**Backend & MLOps** &nbsp; <img src="https://img.shields.io/badge/FastAPI-18181b?style=flat-square&logo=fastapi&logoColor=a78bfa" alt="FastAPI"> <img src="https://img.shields.io/badge/Docker-18181b?style=flat-square&logo=docker&logoColor=a78bfa" alt="Docker"> <img src="https://img.shields.io/badge/pytest-18181b?style=flat-square&logo=pytest&logoColor=a78bfa" alt="pytest"> <img src="https://img.shields.io/badge/GitHub%20Actions-18181b?style=flat-square&logo=githubactions&logoColor=a78bfa" alt="GitHub Actions"> <img src="https://img.shields.io/badge/Git-18181b?style=flat-square&logo=git&logoColor=a78bfa" alt="Git"> <img src="https://img.shields.io/badge/SQL-18181b?style=flat-square&logo=postgresql&logoColor=a78bfa" alt="SQL">

**Cloud & DevOps** &nbsp; <img src="https://img.shields.io/badge/Azure-18181b?style=flat-square&logo=microsoftazure&logoColor=a78bfa" alt="Azure"> <img src="https://img.shields.io/badge/Google%20BigQuery-18181b?style=flat-square&logo=googlebigquery&logoColor=a78bfa" alt="Google BigQuery"> <img src="https://img.shields.io/badge/GitLab-18181b?style=flat-square&logo=gitlab&logoColor=a78bfa" alt="GitLab"> <img src="https://img.shields.io/badge/Power%20BI-18181b?style=flat-square" alt="Power BI">

## Experience

- <img src="img/logos/sanofi.png" alt="Sanofi" height="34"> **Sanofi** · data scientist (current).
- <img src="img/logos/jlc.png" alt="Jaeger-LeCoultre" height="34"> **Jaeger-LeCoultre** · data science intern (2023) — supply-chain demand forecasting (XGBoost, Random Forest, LSTM on BigQuery and SQL Server); improved the weighted MAPE by **45 %** compared with the business teams' own forecasts.
- <img src="img/logos/sorbonne.png" alt="Sorbonne Université" height="34"> **Sorbonne Université** · research intern (2022) — reinforcement learning for autonomous parking: LQR, DDPG and DQN controllers in HighwayEnv.
- **TurtleBot autonomous racing** (2022) — ROS and Gazebo, LIDAR/camera/IMU, OpenCV colour detection, PID tuning.

## Education

- <img src="img/logos/efrei.png" alt="EFREI" height="34"> **Mastère Spécialisé Data & Generative AI Engineering** — EFREI (in progress)
- <img src="img/logos/sorbonne.png" alt="Sorbonne Université" height="34"> <img src="img/logos/ensam.png" alt="Arts et Métiers" height="34"> **MSc Robotics & Artificial Intelligence (SAR)** — Sorbonne Université, 2023, joint programme with ENSAM (Arts et Métiers)
