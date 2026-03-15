
# Research Diagrams

These diagrams describe the conceptual architecture of the project.
GitHub can render these automatically using Mermaid.

---

# 1. Overall Research Pipeline

```mermaid
flowchart LR
A[Raw Medicare Claims] --> B[Data Cleaning]
B --> C[Feature Engineering]
C --> D[Dataset Split]

D --> E1[Isolation Forest]
D --> E2[Local Outlier Factor]
D --> E3[One‑Class SVM]

E1 --> F[Anomaly Scores]
E2 --> F
E3 --> F

F --> G[Evaluation Metrics]
G --> H[Results & Analysis]
```

---

# 2. Dual Evaluation Framework

```mermaid
flowchart TB
A[Feature Dataset]

A --> B[Phase 1: Controlled Evaluation]
B --> C[Anomaly Injection]
C --> D[PR‑AUC / Precision@K]

A --> E[Phase 2: Unsupervised Tuning]
E --> F[Hyperparameter Search]
F --> G[Stability Metrics]
G --> H[Jaccard Similarity]

H --> I[Model Comparison]
```

---

# 3. Consensus Anomaly Detection

```mermaid
flowchart LR
A[Isolation Forest Anomalies]
B[LOF Anomalies]
C[OCSVM Anomalies]

A --> D[Overlap Analysis]
B --> D
C --> D

D --> E[Consensus Anomalies]
E --> F[Expert Review Candidates]
```

---

# Project Description

This study develops a reproducible anomaly detection framework for Medicare outpatient claims using publicly available synthetic claims data. Three classical unsupervised algorithms—Isolation Forest, Local Outlier Factor, and One‑Class Support Vector Machine—are evaluated using a dual‑phase experimental design.

First, semi‑synthetic anomaly injection enables controlled performance evaluation using precision‑recall metrics. Second, models are tuned on unlabeled claims to simulate real‑world deployment conditions, where stability‑based evaluation metrics such as Jaccard similarity and anomaly rate consistency are used to assess reliability.

The framework further introduces consensus anomaly detection across multiple algorithms to prioritize high‑confidence anomalies for expert review. By combining reproducible pipelines, controlled benchmarking, and stability‑based unsupervised evaluation, the study contributes a practical and transparent methodology for anomaly detection in healthcare insurance claims.
