
# 🎯 Expectation Decider : Probability Analysis of Student Performance


A complete **Theory + Practical** Statistics project analyzing a real-world **Student Competitive Exam Dataset** of 200 records. The project covers probability fundamentals, types of events, random variables, Binomial distribution, Venn diagrams, contingency tables, conditional probability, and Bayes' Theorem — implemented in **Python (Jupyter Notebook)** with a supporting **Word Report**.

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

## 🎬 Project Demo Video

[![Watch the Project Walkthrough](https://img.shields.io/badge/▶️%20Watch%20Demo-Google%20Drive-blue?style=for-the-badge&logo=google-drive)](https://drive.google.com/file/d/1dNdl9H0zVWI2gwrM6scI97YvPVi6oLcr/view?usp=sharing)

> 📺 Click the badge above to watch the full project walkthrough video on Google Drive.

---

## 📋 Project Details

| Field | Details |
|-------|---------|
| **Title** | Expectation Decider |
| **Type** | Theory + Practical |
| **Tools Used** | Python · Microsoft Word |
| **Libraries** | Pandas · NumPy · Matplotlib · SciPy · matplotlib-venn |

---

## 🎯 Objective

You are a data analyst working for an **educational research organization**. Your task is to analyze a dataset containing information about **student study habits, attendance, group discussion participation, and exam outcomes**. Through this project, you will explore probability concepts, apply statistical theory, calculate event probabilities, and draw insights using Bayes' Theorem and Binomial distribution.

---

## 🎬 Project GIF

<img width="800" height="425" alt="PR 1GIF" src="https://github.com/user-attachments/assets/dd47116a-6488-40a3-b55e-c42789bc2f60" />





## 🗂️ Project Files

| File | Description |
|------|-------------|
| 📓 `Expectation_Decider.ipynb` | Jupyter Notebook — all Python code, calculations & insights |
| 📊 `Student_Competitive_Exam_Dataset.xlsx` | Dataset — 200 student records across 5 features |
| 📝 `Expectation_Decider_Insights.docx` | Word Report — full step-by-step insights & analysis |

---

## 🧩 Dataset Structure

**AI-Generated Dataset · 200 Records · 5 Features · Binary Outcome: Pass / Fail**

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| `study_hours` | Numerical | Weekly study hours per student |
| `attendance` | Numerical | Class attendance percentage |
| `group_discussion` | Categorical | Participation: Yes / No |
| `previous_test_score` | Numerical | Score in previous test (0–100) |
| `final_exam_pass` | Categorical | Outcome: Pass / Fail |

> **Pass: 142 students (71%)** &nbsp;|&nbsp; **Fail: 58 students (29%)** &nbsp;|&nbsp; **Total: 200**

---

## ✅ Task Checklist

### 🔶 Part A — Theory & Definitions
- [x] Q1. Define Probability, Sample Space, Events, Conditional Probability
- [x] Q2. Types of Events — Empirical vs Theoretical Probability
- [x] Q3. Random Variable, Binomial Distribution, Mean & Variance
- [x] Q4. Venn Diagram — Study Hours > 10 vs Attendance > 80%
- [x] Q5. Contingency Table — Joint, Marginal & Conditional Probability
- [x] Q6. Event Relationships — Independent / Dependent / Mutually Exclusive
- [x] Q7. Bayes' Theorem — Probability of Passing given High Attendance

### 🔶 Part B — Python Practical (`Expectation_Decider.ipynb`)
- [x] Task 1 — Load dataset and verify structure
- [x] Task 2 — Three probability event examples from dataset
- [x] Task 3 — Empirical vs Theoretical Probability
- [x] Task 4 — Binomial Distribution Table + Mean & Variance
- [x] Task 5 — Venn Diagram using `matplotlib-venn`
- [x] Task 6 — Contingency Table + Joint / Marginal / Conditional Probability
- [x] Task 7 — Bayes' Theorem calculation using dataset priors

---

## 🧪 Python — Practical Breakdown

### 🔹 Three Probability Events

| Event | Calculation | Result |
|-------|-------------|--------|
| P(Pass) | 142 ÷ 200 | **0.71** |
| P(Group Discussion = Yes) | 99 ÷ 200 | **0.495** |
| P(Attendance > 75%) | 101 ÷ 200 | **0.505** |

---

### 🔹 Empirical vs Theoretical Probability

| Type | Value | Meaning |
|------|-------|---------|
| Empirical P(Pass) | 142 ÷ 200 = **0.71** | Calculated from actual dataset |
| Theoretical P(Pass) | 1 ÷ 2 = **0.50** | Assuming equally likely outcomes |

> 📌 **Insight:** The empirical probability (0.71) is significantly higher than theoretical (0.50) — preparation and attendance genuinely improve outcomes beyond random chance.

---

### 🔹 Random Variable & Binomial Distribution

**X = Number of students passing out of n = 3 randomly selected students**  
**X ~ Binomial(n=3, p=0.71)**

```python
from scipy.stats import binom
p = len(df[df["final_exam_pass"] == "Pass"]) / len(df)   # 0.71
n = 3
distribution = pd.DataFrame({
    "X": [0, 1, 2, 3],
    "P(X)": [binom.pmf(x, n, p) for x in range(4)]
})
```

| X (Number of Passes) | Formula | P(X) |
|----------------------|---------|------|
| X = 0 | C(3,0) × 0.71⁰ × 0.29³ | 0.0244 |
| X = 1 | C(3,1) × 0.71¹ × 0.29² | 0.1791 |
| X = 2 | C(3,2) × 0.71² × 0.29¹ | 0.4386 |
| X = 3 | C(3,3) × 0.71³ × 0.29⁰ | 0.3579 |

```
Mean     (μ)  = n × p           = 3 × 0.71        = 2.13
Variance (σ²) = n × p × (1-p)  = 3 × 0.71 × 0.29 = 0.6177
```

> 📌 **Insight:** On average, **2.13 out of 3** randomly selected students are expected to pass.

---

### 🔹 Venn Diagram — Study Hours & Attendance

<img width="484" height="453" alt="output" src="https://github.com/user-attachments/assets/40e87669-214e-4174-a67d-45197a422f21" />


**A = Study Hours > 10/week &nbsp;|&nbsp; B = Attendance > 80%**

```python
A = set(df[df["study_hours"] > 10].index)
B = set(df[df["attendance"] > 80].index)
venn2([A, B], set_labels=("Study Hours > 10", "Attendance > 80%"))
```

| Region | Count |
|--------|-------|
| Study > 10 only (A − B) | 92 |
| Both conditions (A ∩ B) | 60 |
| Attendance > 80% only (B − A) | 18 |
| Neither | 30 |

> 📌 **Insight:** 60 students satisfy both conditions — the most disciplined segment and strongest pass candidates.

---

### 🔹 Contingency Table & Probability

**Group Discussion vs Final Exam Result**

| Group Discussion | Fail | Pass | Total |
|-----------------|------|------|-------|
| No | 35 | 66 | 101 |
| Yes | 23 | 76 | 99 |
| **Total** | **58** | **142** | **200** |

```
Joint P(GD=Yes AND Pass)  = 76 ÷ 200           = 0.38
Marginal P(Pass)          = 142 ÷ 200           = 0.71
Conditional P(Pass|GD=Yes)= 76 ÷ 99            = 0.7677
```

> 📌 **Insight:** Students who joined group discussions pass at **76.77%** vs the overall base rate of 71%. Events are **dependent and not mutually exclusive**.

---

### 🔹 Bayes' Theorem — High Attendance & Passing

**Given:**
- P(H | Pass) = 0.70 → 70% of passers had high attendance
- P(H | Fail) = 0.40 → 40% of failers had high attendance
- P(H) = 0.60 → 60% of all students had high attendance
- P(Pass) = 142 ÷ 200 = 0.71

```
P(Pass | H) = [ P(H | Pass) × P(Pass) ] ÷ P(H)
            = [ 0.70 × 0.71 ] ÷ 0.60
            = 0.497 ÷ 0.60
            = 0.8283 → 82.83%
```

> 📌 **Insight:** A student with **high attendance (> 80%)** has an **82.83% probability of passing** — the highest probability found in this entire analysis.

---

## 📊 Visualizations

| # | Visual | Tool | Purpose |
|---|--------|------|---------|
| 1 | Venn Diagram — Study Hours & Attendance | Python | Show overlap between two student groups |
| 2 | Binomial Distribution Bar Chart | Python | Show probability distribution for X passes |
| 3 | Contingency Heatmap | Python | Visualize group discussion vs pass/fail counts |
| 4 | Insights Report (Word) | Microsoft Word | Step-by-step calculations with tables |

---

## 📌 Key Insights

✔️ **Attendance is the strongest predictor** — Students with > 80% attendance have an 82.83% chance of passing (Bayes' Theorem)

✔️ **Group Discussion boosts pass rate** — P(Pass | GD=Yes) = 76.77% vs base rate of 71%

✔️ **Empirical > Theoretical** — Real pass rate (71%) far exceeds the random 50% chance, confirming preparation matters

✔️ **2.13 expected passes** out of any 3 randomly selected students (Binomial mean)

✔️ **60 students meet both** high study hours AND high attendance — the most disciplined student profile

✔️ **Group Discussion and Passing are dependent events** — participation genuinely influences outcome

---

## 🚀 How to Run

**Python**
```bash
# 1. Clone or download this repository
# 2. Install required libraries
pip install pandas numpy matplotlib seaborn scipy matplotlib-venn openpyxl

# 3. Place Student_Competitive_Exam_Dataset.xlsx in the same folder as the notebook
# 4. Open Expectation_Decider.ipynb in Jupyter Notebook or JupyterLab
# 5. Run all cells from top to bottom — each section ends with a 📌 INSIGHT
```

---

## 🌟 Future Enhancements

- [ ] Add Logistic Regression to predict pass/fail from study hours & attendance
- [ ] Perform Chi-Square test for independence between Group Discussion & Pass
- [ ] Build an interactive Streamlit dashboard for probability exploration
- [ ] Extend dataset to 1000+ records for more robust conclusions
- [ ] Add ROC curve analysis comparing different probability thresholds

---

## 📩 Submission Checklist

- [x] Practical implementation in Jupyter Notebook (Python)
- [x] All calculations shown step-by-step with formula substitutions
- [x] Venn Diagram, Contingency Table, Binomial Distribution included
- [x] Bayes' Theorem applied with dataset-derived priors
- [x] Insights Word Report with tables and summary
- [x] Dataset file included (200 records, AI-generated)
- [x] Clear and descriptive README.md

---

## 👩‍💻 Priya Savaliya
📍 Ahmedabad, Gujarat

⭐ If you found this project helpful, give it a star and feel free to fork!

📊 *Clean Data · Sharp Stats · Confident Insights*
