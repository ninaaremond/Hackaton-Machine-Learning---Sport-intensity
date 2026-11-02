# Workout Intensity Prediction Challenge

---

## 📌 Problem Overview

Each row in the dataset describes a single workout with the following features:
- **User:** Pseudonymous ID
- **Activity:** Sport, gender, start date, and time
- **Metrics:** Duration, distance, average speed, maximum speed, speed variability, and climbing

### Target Variable
- **`intensity`:** Indicates how hard the workout was for that specific user (measured by app sensors).
- **Classes:** `easy`, `moderate`, `hard` (balanced distribution across classes).
- **Challenge:** Capturing the relative, individualized meaning of "hard" across different users and sport types.

---

## 👥 Team Setup Protocols (Must-Read Before Any Submission)

1. **Form Team Before First Submission:**  
   The team leader opens the **Team** tab on Kaggle and invites all team members. All members must accept the merge **before anyone uploads any file** (including `sample_submission.csv`).  
   > ⚠️ *Submitting individually first will trigger Kaggle's quota restrictions and block team merging later.*

2. **Official Team Naming:**  
   Name your Kaggle team using your official assigned team number (e.g., `Team_13`, `Team_14`, ..., `Team_28`).  
   > ⚠️ *At 18:10, any solo account or unrecognized team name on the private leaderboard will be ignored for grading.*

3. **Account Rules:**  
   One account per student. Every student must belong to their official team on Kaggle. Holding accounts "in reserve" to test models on the side is strictly prohibited. Teams are verified at **14:20** from the Team tab.

---

## 📜 Rules & Constraints

- **Team Size:** 6 or 7 members (formed by the teacher).
- **Submission Limit:** Maximum 15 submissions per team per day.
- **Allowed Libraries & Models:**  
  - Libraries: `pandas`, `NumPy`, `matplotlib`, `scikit-learn`
  - Models: Any standard `scikit-learn` non-neural network algorithm (e.g., k-Nearest Neighbors, SVM, Naïve Bayes, Extra Trees, `HistGradientBoosting`, Voting Classifier, Stacking Classifier).
- **Forbidden:**  
  - Deep Learning (including `MLPClassifier`).
  - External datasets.
  - Sharing code between teams.
- **Documentation (`LOG.md`):**  
  Every submission **must** be documented on a new line in `LOG.md` containing:
  - Timestamp
  - Change description
  - Rationale ("why")
  - Validation score
  - Public score
- **Defense:**  
  *You submit it, you explain it.* Every team member will individually explain the final model on paper.

---

## ⏱️ Checkpoints & Gates

| Checkpoint | Threshold / Metric | Timing & Requirements |
| :--- | :--- | :--- |
| **Gate 1 (G1)** | Public Macro-$F_1$ | **15:50** |
| **Gate 2 (G2)** | Public Macro-$F_1$ | **17:35** (Requires confusion matrix + 1 sentence error analysis in `LOG.md`) |
| **Gate 3 (G3)** | Beat Teacher's Reference | Final Evaluation |

---

## 📊 Evaluation Metric

Submissions are evaluated using the **Macro-Averaged $F_1$-score** across the three target classes:

$$F_1_{\text{macro}} = \frac{F_1_{\text{easy}} + F_1_{\text{moderate}} + F_1_{\text{hard}}}{3}$$

- **Public Leaderboard:** Evaluated on ~50% of the test set.
- **Private Leaderboard:** Final ranking uses the remaining ~50% (hidden until the competition ends).
- **Final Selection Deadline:** Select your final submission candidate before **18:10**.

---

## 📄 Submission File Format

For each `workout_id` in `test.csv`, predict the class label (`easy`, `moderate`, or `hard` in lowercase).

The CSV file must include a header and adhere to this exact structure:

```csv
workout_id,intensity
100008,easy
100010,hard
100011,moderate
```