# 🔥 Correlation Heatmap & Pairwise Relationships
> Uncovering hidden relationships between variables — using Pearson correlation, masked heatmaps, pairplots and regression scatter plots on a student academic performance dataset.

![Python](https://img.shields.io/badge/Python-3.14-blue?style=flat&logo=python)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange?style=flat&logo=python)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-teal?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-darkblue?style=flat&logo=pandas)
![SciPy](https://img.shields.io/badge/SciPy-1.x-darkgreen?style=flat&logo=scipy)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat&logo=jupyter)
![Internship](https://img.shields.io/badge/Syntecxhub-Data%20Science%20Internship-purple?style=flat)

---

## 📌 Project Overview

Knowing which variables are related — and how strongly — is one of the most valuable things you can learn from a dataset before building any model. A strong correlation between study hours and final grade tells you that study hours is likely a useful feature. A near-zero correlation tells you a variable probably won't help.

This project computes Pearson correlations across all variable pairs in a student academic performance dataset, visualizes them as a masked heatmap, surveys all relationships through a pairplot, and zooms in on the strongest pairs with annotated scatter plots and regression lines.

Built as part of the Syntecxhub Data Science Internship (Week 2, Project 3).

---

## ✨ Features

- **Pearson correlation matrix** — computes r values for all variable pairs using `.corr(method="pearson")`
- **Masked heatmap** — lower triangle only, upper triangle masked to remove redundant symmetric values, annotated with exact r values
- **Absolute correlation heatmap** — strips direction to show pure relationship strength, useful for feature selection
- **Pairplot with KDE diagonal** — visual survey of all key variable combinations simultaneously in one grid
- **Top 4 scatter plots with regression lines** — automatically identifies strongest correlations and plots them with trend lines and r values annotated
- **Color coded by direction** — blue dots for positive correlations, pink dots for negative correlations
- **Full ranked correlation table** — all unique pairs sorted by absolute strength with direction and strength label
- **Written summary export** — generates `correlation_summary.txt` with strongest positive and negative relationships identified and interpreted

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.14 | Core programming language |
| Matplotlib | Chart creation and styling |
| Seaborn | Heatmap and pairplot generation |
| Pandas | Data manipulation and correlation computation |
| NumPy | Numerical operations and data generation |
| SciPy | Linear regression for scatter plot trend lines |
| Jupyter Notebook | Development and documentation environment |

---

## 📸 Charts

### Correlation Heatmap — Lower Triangle Masked
<img width="1327" height="1176" alt="01_correlation_heatmap" src="https://github.com/user-attachments/assets/43c005db-e644-4b2d-96df-3a749641db2d" />

### Absolute Correlation Heatmap — Strength Only
<img width="1301" height="1176" alt="02_absolute_correlation_heatmap" src="https://github.com/user-attachments/assets/1cbbc226-9deb-4c7b-b087-3e0b0c3af469" />

### Pairplot — Key Variable Relationships
<img width="1841" height="1890" alt="03_pairplot_key_variables" src="https://github.com/user-attachments/assets/47079967-efe3-4ec9-8b58-fcaafd7e9843" />

### Top 4 Strongest Pairs — Scatter Plots with Regression
<img width="2075" height="1516" alt="04_top_correlation_scatter_plots" src="https://github.com/user-attachments/assets/fc390f89-e131-4c00-8db7-77fdb940b5d8" />

---

## 🚀 Installation

1. Clone the repository
```bash
git clone https://github.com/fsafva13-coder/Syntecxhub_Correlation_Heatmap_Pairwise.git
cd Syntecxhub_Correlation_Heatmap_Pairwise
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scipy jupyter
```

3. Launch the notebook
```bash
jupyter notebook project3_correlation_heatmap_pairwise.ipynb
```

4. Run all cells with **Kernel → Restart & Run All**

---

## 📋 Usage

The notebook is fully self-contained — it generates a 500-row student performance dataset automatically with realistic correlations built in.

**Pipeline flow:**
1. Dataset generated with 8 numeric features — study hours, sleep, stress, attendance, 3 subject scores, final grade
2. Pearson correlation matrix computed for all variable pairs
3. Heatmap rendered with upper triangle masked and values annotated
4. Pairplot generated for 5 key variables
5. Top 4 strongest pairs identified automatically and plotted with regression lines
6. Full ranked summary exported to `correlation_summary.txt`

To use your own dataset:
```python
df = pd.read_csv("your_data.csv")
corr_matrix = df.corr(method="pearson")
```
Make sure all columns are numeric — categorical columns need to be encoded first.

---

## 📁 Project Structure

```
Syntecxhub_Correlation_Heatmap_Pairwise/
├── README.md
├── project3_correlation_heatmap_pairwise.ipynb   ← main notebook
├── correlation_summary.txt                       ← ranked correlation report
└── plots/
    ├── 01_correlation_heatmap.png
    ├── 02_absolute_correlation_heatmap.png
    ├── 03_pairplot_key_variables.png
    └── 04_top_correlation_scatter_plots.png
```

---

## 📊 Results

| Relationship | Pearson r | Strength | Direction |
|---|---|---|---|
| math_score vs final_grade | ~0.93 | Strong | Positive |
| science_score vs final_grade | ~0.88 | Strong | Positive |
| study_hours vs math_score | ~0.72 | Strong | Positive |
| sleep_hours vs stress_level | ~-0.65 | Moderate | Negative |
| stress_level vs math_score | ~-0.48 | Moderate | Negative |

**Key findings:**
- Math score is the strongest single predictor of final grade — a student who performs well in math almost always performs well overall
- Study hours positively correlates with all three subject scores — more study time means better results across the board
- Sleep and stress are inversely related — as sleep hours decrease, stress levels rise predictably
- Stress negatively impacts math and science scores — high-stress students consistently score lower in technical subjects

---

## 🧠 Challenges & Learnings

**Challenge:** The full pairplot with all 8 variables produced a 8x8 grid that was too dense and unreadable. The solution was to select the 5 most informative variables for the pairplot and use the heatmap to display all 8 — each chart type serves a different purpose.

**Learning:** Pearson r only captures **linear** relationships. A correlation near 0 doesn't mean two variables are unrelated — it means they don't have a *linear* relationship. A variable could still follow a curve or threshold pattern that Pearson completely misses.

**Key insight:** Masking the upper triangle is not just cosmetic — it actively reduces cognitive load. A full symmetric heatmap forces the reader to mentally filter duplicates. The masked version directs attention exactly where it needs to go.

---

## 🔮 Future Improvements

- Add Spearman correlation for non-linear and ranked relationships
- Include p-values on the heatmap to indicate statistical significance of each correlation
- Build an interactive heatmap using Plotly so users can hover over cells for details
- Add a feature importance section connecting correlation findings to a simple regression model
- Extend to partial correlations — controlling for a third variable to see if a relationship holds independently

---

## 👩‍💻 Author

**Fathima Safva** - Data Science Intern @ Syntecxhub  
🔗 [LinkedIn](https://linkedin.com/in/fathima-safva-578294315) · [GitHub](https://github.com/fsafva13-coder)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
