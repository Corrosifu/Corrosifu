![Bilal Bounadja](img/Bilal_bounadja_page-0001.jpg)


# Hello 🖐️ , I’m Bilal Bounadja, welcome to my portfolio, if you have any questions feel free to contact me.

👨‍💻 Data Scientist.

---

## About Me

- 🎓 Master’s degree diploma in Robotics and AI (SAR), Sorbonne Université, graduated in 2023
- 🌱 Passionate about Scientific Research, AI, Biology and Learning new stuff
- ⚡ Always curious and continuously learning new technologies and methodologies
- 📫 Contact: [Bilal.bndj@gmail.com] | [LinkedIn](https://www.linkedin.com/in/bilal-bounadja-data/)
---

## Skills

| Data Science                                                                                                        | Robotics & IoT                                                                                     | DevOps & Miscellaneous                                                                                           |
|---------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" width="40" title="Python" /> Python          | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/cplusplus/cplusplus-original.svg" width="40" title="C++" /> C++                | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/git/git-original.svg" width="40" title="Git" /> Git                           |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/tensorflow/tensorflow-original.svg" width="40" title="TensorFlow" /> TensorFlow   | <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg" width="40" title="OpenCV" /> OpenCV                           | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/gitlab/gitlab-original.svg" width="40" title="GitLab" /> GitLab               |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/pytorch/pytorch-original.svg" width="40" title="PyTorch" /> PyTorch               | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/ros/ros-original.svg" width="40" title="ROS" /> ROS                            | <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg" width="40" title="Google Cloud" /> Google Cloud       |
| <img src="https://upload.wikimedia.org/wikipedia/commons/0/05/Scikit_learn_logo_small.svg" width="40" title="Scikit-learn" /> scikit-learn         | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" width="40" title="C" /> C                                    | <img src="https://logos-world.net/wp-content/uploads/2022/02/Microsoft-Power-BI-Symbol.png" width="40" title="PowerBI" /> Power BI                     |
| <img src="https://miro.medium.com/v2/resize:fit:419/0*Ws17TOkgJI7ie8yi.png" width="40" title="Seaborn" /> Seaborn                                       | <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/gazebo/gazebo-original.svg" width="40" title="Gazebo" /> Gazebo                | <img src="https://upload.wikimedia.org/wikipedia/commons/3/34/Microsoft_Office_Excel_%282019%E2%80%93present%29.svg" width="40" title="Excel" /> Excel |
| <img src="https://www.svgrepo.com/show/303229/microsoft-sql-server-logo.svg" width="40" title="SQLServer" /> SQLServer                                  | <img src="https://upload.wikimedia.org/wikipedia/en/d/d2/SolidWorks_Logo.svg" width="40" title="SolidWorks" /> SolidWorks                                |<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/92/LaTeX_logo.svg/2560px-LaTeX_logo.svg.png" width="40" title="LaTeX" /> LateX  |

---

## Projects

- 💻  Data Science personnal projects
- 🤖  Robotics and IoT projects
- 🔒  Brief explanation without public code

## Projects

- 💻[**Spam Detection Methods History (2025)**](https://github.com/Corrosifu/Spam_Detection/) 
### Spam Detection Project Summary

#### Context & Goal
Developed a comprehensive spam detection system to classify emails/messages as spam or ham. The project explored both historical methods and modern machine learning techniques to improve detection accuracy and robustness.

#### Methodology
- Used datasets such as CEAS-08 and Kaggle samples.  
- Applied advanced text preprocessing: tokenization, lemmatization, and stop-word removal with Python libraries.  
- Compared multiple classifiers—from heuristic filters and Naive Bayes to Random Forest and XGBoost.  
- Fine-tuned a transformer-based DistilBERT model for state-of-the-art classification.

#### Results
  | Model                | Accuracy (Text Only) | F1-Score (Text Only) | Accuracy (Multiple Features) | F1-Score (Multiple Features) |
  |----------------------|---------------------|---------------------|------------------------------|------------------------------|
  | KNN                  | 80.4%               | 0.80                | 75.9%                        | 0.76                         |
  | Logistic Regression   | 98.1%               | 0.98                | 97.4%                        | 0.97                         |
  | Random Forest        | 98.5%               | 0.98                | 99.1%                        | 0.99                         |
  | XGBoost              | 98.1%               | 0.98                | 98.1%                        | 0.98                         |

DistilBERT fine-tuning achieved near-perfect F1 scores (**~99.5%**), outperforming traditional methods but requiring greater computational resources.

---

For full technical details and code, please refer to the project repository.

  
  ![Confusion Matrix](img/33f64031-1651-4904-9425-e7e4b1f67a8d.png)

- 💻[**Covid-19 Case Prediction and Survival Analysis (2024)**](https://github.com/Corrosifu/covid19_diagnosis/)
# COVID-19 Diagnosis and Clinical Spectrum

## Context / Job Goal

The project addresses the urgent challenge of detecting COVID-19 positive cases from clinical laboratory data collected during the pandemic at Hospital Israelita Albert Einstein, São Paulo, Brazil. The aim is to develop accurate and reliable machine learning models that help identify COVID-19 infections based on routine lab tests, under constraints of limited testing capacity and incomplete data.

## Methodology

- **Dataset:** Anonymized patient data including SARS-CoV-2 RT-PCR results and various laboratory tests, standardized and cleaned.  
- **Handling Missing Data:** Columns with more than 90% missing values were removed. Missing values were imputed by feature-wise means, and new indicators such as "has_disease" were created to improve completeness.  
- **Data Balancing:** SMOTE technique was applied to mitigate class imbalance since negative cases dominate the dataset.  
- **Feature Analysis:** Correlation heatmaps were generated to explore relationships among lab features.  
- **Models Evaluated:** Classical machine learning algorithms including Random Forest, SVM, XGBoost, KNN, Logistic Regression, and ensembles.  
- **Evaluation Metrics:** Focused on Accuracy and Recall to balance overall correctness and sensitivity to true COVID positives.

## Results

| Metric         | Score  |
|----------------|--------|
| Accuracy       | 0.909  |
| Recall         | 0.706  |
| AUC            | 0.824  |
| KS Statistic   | 0.648  |

- Random Forest and XGBoost delivered the best classification results.  
- High recall indicates strong ability to detect true positive COVID-19 cases, critical for health screening.  
- Limitations include a relatively small test set, missing data impacting model reliability, and the need for validation on new cohorts.

---

For complete details, preprocessing methods, model code, and visualizations, please visit the project repository.

[Project Dataset on Kaggle](https://www.kaggle.com/datasets/einsteindata4u/covid19/data)

  <img width="851" height="548" alt="image" src="img/ababb14d-e8dd-425d-a170-81f3f12b3e43.png" />
  <img width="1327" height="528" alt="image" src="img/427738ef-56e7-4109-bf63-480c22890a7a.png" />



- 📚🤖**TurtleBot Autonomous Racing Project (2022)**  
  Designed and developed control algorithms for an autonomous TurtleBot capable of navigating race tracks with obstacle avoidance and trajectory tracking. Integrated multiple sensor inputs including LIDAR, RGB camera, and IMU within the Robot Operating System (ROS) framework. Employed Gazebo for realistic simulation testing. Applied computer vision techniques, including OpenCV for target color detection and image processing. Tuned PID controllers to optimize robot motion stability and speed while avoiding collisions on complex racecourse layouts.

- 🔒**Sales Forecasting for Jaeger-LeCoultre (2023)**  
  Led data-driven forecasting initiatives by building predictive models for sales planning and supply chain optimization at Jaeger-LeCoultre. Processed and analyzed large-scale datasets stored on SQL Server and Google BigQuery. Implemented machine learning pipelines using Python to predict monthly sales volumes, achieving a weighted Mean Absolute Percentage Error (wMAPE) outperforming prior benchmarks. Communicated results and insights through data visualization dashboards using PowerBI to support operational decisions and inventory management.

- 🔒**Reinforcement Learning for Autonomous Parking (2022)**  
  Conducted exploratory research on model-based reinforcement learning approaches applying Deep Deterministic Policy Gradient (DDPG) and Deep Q-Networks (DQN) to an autonomous parking task. Created simulation environments using OpenAI Gym and custom Gazebo models to train and evaluate policies. Focused on improving sample efficiency and balancing exploration-exploitation trade-offs with optimized neural network architectures and reward shaping techniques.


---


## Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/bilal-bounadja-data/)  
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:bilal.bndj@gmail.com)




![Profile views](https://komarev.com/ghpvc/?username=Corrosifu)























