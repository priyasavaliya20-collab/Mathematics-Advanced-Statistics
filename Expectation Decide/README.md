# 📊 Expectation Decider — Probability Analysis of Student Performance

> A complete **Theory + Practical** Probability Project analyzing a real-world student dataset of **200 records**.  
> Covers fundamental probability concepts end-to-end — from basic events to Bayes' Theorem — implemented in Python.

---
## 🛠️ Tools & Technologies

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=python&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)
![Microsoft Word](https://img.shields.io/badge/Microsoft_Word-2B579A?style=for-the-badge&logo=microsoft-word&logoColor=white)

---

## 🧾 Project Overview

| Field | Details |
|---|---|
| **Title** | Expectation Decider: Probability Analysis of Student Performance |
| **Duration** | 4 Hours |
| **Type** | Theory + Practical |
| **Tools Used** | Python · Excel |
| **Libraries** | Pandas · NumPy · Matplotlib · SciPy · matplotlib-venn |
| **Dataset** | AI-Generated · 200 Student Records |

---

## 🎯 Objective

Working for an **educational research organization**, the task is to analyze student performance data and apply probability concepts to understand factors affecting exam success.

Through this project:
- Calculate **event probabilities** for real student outcomes
- Analyze relationships between **study habits and exam results**
- Explore **conditional probability** and **independence**
- Apply **Bayes' Theorem** to identify the strongest predictor of passing

---

## 🗂️ Project Files

| File | Description |
|---|---|
| 📓 `Expectation_Decider.ipynb` | Jupyter Notebook with all probability calculations |
| 📊 `Student_Competitive_Exam_Dataset.xlsx` | Dataset — 200 student records |
| 📄 `Expectation_Decider_Insights.docx` | Detailed insights report and interpretations |
| 📘 `README.md` | Project documentation |

---

## 🧩 Dataset Structure

**AI-Generated Dataset · 200 Records**

| Column Name | Data Type | Description |
|---|---|---|
| `study_hours` | Numerical | Weekly study hours |
| `attendance` | Numerical | Student attendance percentage |
| `group_discussion` | Categorical | Yes / No |
| `previous_test_score` | Numerical | Previous test performance |
| `final_exam_pass` | Categorical | Pass / Fail |

---

## 🎬 Project Demo Video

[![Watch the Project Walkthrough](https://img.shields.io/badge/▶️%20Watch%20Demo-Google%20Drive-blue?style=for-the-badge&logo=google-drive)](https://drive.google.com/file/d/1dNdl9H0zVWI2gwrM6scI97YvPVi6oLcr/view?usp=sharing)

> 📺 Click the badge above to watch the full project walkthrough video on Google Drive.

---

## 🎦 Project GIF

<img width="900" height="525" alt="PR 1GIF" src="https://github.com/user-attachments/assets/7a3e7b94-9223-41e4-a517-d187ad99b56c" />

---

##  🎦 Insights GIF 

<img width="900" height="525" alt="Expectation_Decider_GIF" src="https://github.com/user-attachments/assets/43e7350a-e6c8-4811-9a82-781cc8b07996" />

---

## 📗 Probability Topics Covered

---

### 🔢 Q1 — Basic Probability Events

Calculate probabilities of three key student events from the dataset:

| Event | Favorable | Total | Probability |
|---|---|---|---|
| Pass Exam | 142 | 200 | **0.7100** |
| Group Discussion | 99 | 200 | **0.4950** |
| Attendance > 75% | 101 | 200 | **0.5050** |

```python
total_students = len(df)

p_pass       = len(df[df["final_exam_pass"] == "Pass"]) / total_students   # 0.7100
p_group      = len(df[df["group_discussion"] == "Yes"]) / total_students   # 0.4950
p_attendance = len(df[df["attendance"] > 75]) / total_students             # 0.5050
```

> 📌 **Insight:** 71% of students pass — significantly above the theoretical 50% baseline. Group participation and attendance are closely balanced at ~50% each.

---

### 📋 Q2 — Empirical vs Theoretical Probability

| Type | Formula | Probability |
|---|---|---|
| Empirical (actual data) | 142 / 200 | **0.7100** |
| Theoretical (assumed 50/50) | 1 / 2 | **0.5000** |

$$P(\text{Pass})_{\text{empirical}} = \frac{142}{200} = 0.7100$$

$$P(\text{Pass})_{\text{theoretical}} = \frac{1}{2} = 0.5000$$

```python
empirical_probability  = pass_students / total_students   # 0.7100
theoretical_probability = 1 / 2                           # 0.5000
```

> 📌 **Insight:** Real pass rate (71%) exceeds the theoretical assumption (50%) by 21 percentage points — driven by attendance, study hours, and participation.

---

### 🎰 Q3 — Random Variable & Binomial Distribution

**X = Number of students passing among 3 randomly selected students**

Parameters: `n = 3`, `p = 0.71`, `q = 0.29`

| X | P(X) | Interpretation |
|---|---|---|
| 0 | 0.0244 | None of 3 pass |
| 1 | 0.1791 | Exactly 1 passes |
| **2** | **0.4386** | **← Most likely outcome** |
| 3 | 0.3579 | All 3 pass |

$$E(X) = np = 3 \times 0.71 = 2.13$$

$$Var(X) = npq = 3 \times 0.71 \times 0.29 = 0.6177$$

```python
from scipy.stats import binom

p = len(df[df["final_exam_pass"] == "Pass"]) / len(df)  # 0.71
n = 3

distribution = pd.DataFrame({
    "X (Number of Passes)": [0, 1, 2, 3],
    "P(X)": [binom.pmf(x, n, p) for x in range(4)]
})

mean     = n * p              # 2.13
variance = n * p * (1 - p)    # 0.6177
```

> 📌 **Insight:** When selecting 3 students at random, the most likely outcome (44%) is exactly **2 passing**. The probability that all 3 fail is only **2.44%**.

---

### 🔵 Q4 — Venn Diagram Analysis

**A** = Students with Study Hours > 10 &nbsp;|&nbsp; **B** = Students with Attendance > 80%

| Region | Count | Description |
|---|---|---|
| Only A | 92 | Study hard but low attendance |
| **A ∩ B** | **60** | Both study hard AND attend regularly |
| Only B | 18 | Good attendance but fewer study hours |
| Neither | 30 | Low on both |

| Probability | Formula | Value |
|---|---|---|
| P(A) | 152 / 200 | **0.7600** |
| P(B) | 78 / 200 | **0.3900** |
| P(A ∩ B) | 60 / 200 | **0.3000** |
| P(A ∪ B) | 170 / 200 | **0.8500** |

```python
A = set(df[df["study_hours"] > 10].index)
B = set(df[df["attendance"] > 80].index)

venn2([A, B], set_labels=("Study Hours > 10", "Attendance > 80%"))
```

> 📌 **Insight:** 85% of students satisfy at least one condition. The overlap group (30%) — strong in both study hours and attendance — forms the highest-performing cohort.

---

### 📊 Q5 — Contingency Table & Conditional Probability

**Group Discussion vs Final Exam Outcome**

| Group Discussion | Fail | Pass | Total |
|---|---|---|---|
| No | 35 | 66 | 101 |
| Yes | 23 | **76** | 99 |
| **Total** | **58** | **142** | **200** |

| Probability | Formula | Value |
|---|---|---|
| P(Discussion ∩ Pass) — Joint | 76 / 200 | **0.3800** |
| P(Pass) — Marginal | 142 / 200 | **0.7100** |
| **P(Pass \| Discussion)** — Conditional | 76 / 99 | **0.7677** |

```python
contingency_table = pd.crosstab(df["group_discussion"], df["final_exam_pass"])

joint_probability       = joint_count / len(df)          # 0.3800
marginal_probability    = pass_count / len(df)           # 0.7100
conditional_probability = joint_count / discussion_count # 0.7677
```

> 📌 **Insight:** Students who participate in group discussions have a **76.77% pass rate** vs 65.35% for non-participants — a **+11.42 percentage point** advantage.

---

### ⚙️ Q6 — Independence & Mutual Exclusivity

**Independence Test**

$$P(\text{Pass} \mid \text{Discussion}) = 0.7677 \neq P(\text{Pass}) = 0.7100$$

Since the two values differ:

✅ **Events are Dependent** — participation in group discussion positively influences exam success.

**Mutual Exclusivity Test**

76 students **both** participated in group discussion **and** passed the exam.

$$P(\text{Pass} \cap \text{Discussion}) = 0.38 \neq 0$$

✅ **Events are Not Mutually Exclusive** — a student can do both simultaneously.

---

### 🧮 Q7 — Bayes' Theorem Application

**Given historical data:** H = High Attendance (>80%)

| Parameter | Meaning | Value |
|---|---|---|
| P(H \| Pass) | High attendance among passers | 0.70 |
| P(H \| Fail) | High attendance among failers | 0.40 |
| P(H) | Overall high attendance rate | 0.60 |

**From dataset:**

$$\text{Pass} = 142, \quad \text{Fail} = 58, \quad \text{Total} = 200$$

$$P(\text{Pass}) = \frac{142}{200} = 0.71$$

**Bayes' Theorem:**

$$P(\text{Pass} \mid H) = \frac{P(H \mid \text{Pass}) \times P(\text{Pass})}{P(H)}$$

**Calculation:**

$$P(\text{Pass} \mid H) = \frac{0.70 \times 0.71}{0.60} = \frac{0.497}{0.60} = 0.8283$$

| Probability | Value |
|---|---|
| Overall pass rate | 71.00% |
| **Pass rate with high attendance** | **82.83%** |
| Improvement | **+11.83 percentage points** |

```python
P_H_given_P = 0.70
P_H        = 0.60
P_P        = pass_count / total_students          # 0.71

P_P_given_H = (P_H_given_P * P_P) / P_H          # 0.8283
```

> 📌 **Insight:** A student with high attendance (>80%) has an **82.83% probability of passing** — making attendance the single strongest predictor in this dataset.

---

## 📊 Key Findings

| # | Finding |
|---|---|
| ✔️ | **71.00%** of students passed the final examination (142 out of 200) |
| ✔️ | Group discussion participants achieved a **76.77%** pass rate vs 65.35% for non-participants |
| ✔️ | Students with attendance above 80% have an **82.83%** probability of passing (Bayes' Theorem) |
| ✔️ | Probability that all 3 randomly selected students fail is only **2.44%** |
| ✔️ | Study hours and attendance together cover **85%** of all students (A ∪ B) |
| ✔️ | Group discussion and exam success are **statistically dependent** events |
| ✔️ | **High attendance (>80%)** is the strongest single predictor of exam success |

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|---|---|
| **Python** | Core programming language |
| **Pandas** | Data manipulation and probability calculations |
| **NumPy** | Numerical computations |
| **Matplotlib** | Charts and Venn diagram visualizations |
| **SciPy** | Binomial probability calculations |
| **matplotlib-venn** | Venn diagram rendering |
| **Jupyter Notebook** | Interactive development environment |
| **Microsoft Excel** | Dataset storage and verification |

---

## 🚀 How to Run

1. Clone or download this repository
2. Install required libraries:
   ```bash
   pip install pandas numpy matplotlib scipy openpyxl matplotlib-venn
   ```
3. Place `Student_Competitive_Exam_Dataset.xlsx` in the project folder
4. Open `Expectation_Decider.ipynb`
5. Run all cells sequentially

---

## 🌟 Future Enhancements

- [ ] Probability Tree Diagrams
- [ ] Markov Chain Student Progression Analysis
- [ ] Interactive Streamlit Dashboard
- [ ] Hypothesis Testing on Attendance Impact
- [ ] Monte Carlo Simulation for Exam Predictions
- [ ] Expand dataset to 1000+ students

---

## ✅ Submission Checklist

- [x] Probability calculations completed in Python
- [x] Binomial Distribution Analysis (n=3, p=0.71)
- [x] Venn Diagram Probability Analysis
- [x] Contingency Table Analysis
- [x] Conditional Probability Calculations
- [x] Independence & Mutual Exclusivity Testing
- [x] Bayes' Theorem Application
- [x] Insights Report Included
- [x] Dataset Included
- [x] Complete README Documentation

---

## 👩‍💻 Author

**Priya Savaliya**  
📍 Ahmedabad, Gujarat

---

> ⭐ If you found this project helpful, give it a star and feel free to fork!

*📊 Data-Driven Decisions · Probability-Powered Insights · Smarter Predictions*
