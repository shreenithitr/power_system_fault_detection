# Power System Fault Detection & Classification

> Capstone Project — KPR Institute of Engineering and Technology, CSE  
> Automated multi-class fault detection using IBM Watsonx.ai AutoAI and classical machine learning.

![IBM Watsonx](https://img.shields.io/badge/IBM%20Watsonx.ai-AutoAI-0062ff?style=flat&logo=ibm&logoColor=white)
![Python](https://img.shields.io/badge/ML-Classification-3B6D11?style=flat)
![Status](https://img.shields.io/badge/Status-Completed-1D9E75?style=flat)

---

## Problem Statement

Power distribution systems are vulnerable to electrical faults — including line-to-ground (LG), line-to-line (LL), and three-phase short circuits (LLLG) — that can disrupt operations, damage infrastructure, and compromise grid safety. Traditional fault detection methods are slow and manually intensive, creating a critical need for intelligent, real-time systems capable of automatically detecting and classifying fault conditions from voltage and current phasor measurements.

**Fault Classes:** `No Fault` · `LG` · `LL` · `LLG` · `LLLG`

---

## System Pipeline
```
Data Collection → Preprocessing → AutoAI Training → Evaluation → Deployment (REST API)
(IEDs, PMUs, SCADA)   (Clean, Feature Eng.)  (HPO + Model Select.)  (Accuracy, F1)   (Watson OpenScale)
```

---

## Technology Stack

| Component | Technology |
|-----------|-----------|
| AutoML Platform | IBM Watsonx.ai (AutoAI) |
| ML Algorithms | Random Forest, Gradient Boosting, SVM |
| Monitoring | Watson OpenScale |
| Data Sources | IEDs, Phasor Measurement Units (PMUs), SCADA |
| Input Features | Voltage, Current, Frequency, Phase Angles |

---

## System Approach

1. Upload labeled electrical measurement data (voltage, current phasors, fault type) to IBM Watsonx.ai
2. Clean data — handle missing values, outliers; perform feature engineering for fault-relevant indicators
3. Run AutoAI to automate model training with classification as the target task
4. Evaluate pipelines using accuracy, precision, recall, F1-score, and confusion matrix
5. Deploy the best-performing model as a REST API for real-time fault classification
6. Monitor with Watson OpenScale; retrain periodically with new operational data

---

## AutoAI Pipeline Leaderboard

| Rank | Pipeline | Algorithm | Accuracy (CV) |
|------|----------|-----------|--------------|
| ⭐ 1 | Pipeline 9 | Batched Tree Ensemble (Random Forest) | 0.409 |
| 2 | Pipeline 8 | Random Forest Classifier | 0.409 |
| 3 | Pipeline 4 | Snap Logistic Regression | 0.393 |
| 4 | Pipeline 3 | Snap Logistic Regression | 0.393 |

> 9 pipelines generated and ranked in under 2 minutes. The top model was deployed for real-time multiclass prediction (Line Breakage, Transformer Failure, etc.).

---

## Conclusion

Watsonx.ai AutoAI successfully automated the full ML workflow — from data preprocessing and feature selection through model training and hyperparameter optimization. The deployed Random Forest Classifier provides real-time fault classification via REST API, enabling timely fault isolation and significantly improving grid stability and operational efficiency over traditional manual approaches.

---

## Future Scope

- **Edge Computing** — On-site processing for faster fault response during grid events
- **Fault Location Estimation** — Pinpoint fault location, not just fault type
- **IoT + SCADA Integration** — Seamless automation with smart sensor networks
- **Digital Twins + Reinforcement Learning** — Self-learning, adaptive grid optimization platform

---

## IBM Certifications

| Certification | Issued By | Date |
|--------------|-----------|------|
| Getting Started with Artificial Intelligence | IBM SkillsBuild | Jul 20, 2025 |
| Journey to Cloud: Envisioning Your Solution | IBM SkillsBuild | Jul 20, 2025 |
| Retrieval Augmented Generation with LangChain | IBM SkillsBuild | Jul 27, 2025 |

---

## References

1. IBM Watsonx.ai Documentation — https://www.ibm.com/docs/en/watsonx
2. IBM Research: Granite Models — http://research.ibm.com/blog/ibm-granite-models
3. Brown, T. et al. (2020). *Language Models are Few-Shot Learners*. NeurIPS.
4. Liu, P. et al. (2023). *Prompt Engineering for Large Language Models*. arXiv.
5. OpenAI (2023). *Prompt Engineering Best Practices*. https://platform.openai.com/docs/guides/prompt-engineering

---

## Author

**Shreenithi T R**  
CSE · KPR Institute of Engineering and Technology  
Aspiring Data Analyst | AI & Cloud Enthusiast
