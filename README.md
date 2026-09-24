# Anime Data Analysis — Exploratory Data Analysis

## Project Overview

This project presents a focused **Exploratory Data Analysis (EDA)** of the `anime-dataset-2023.csv` dataset.

The analysis examines anime ratings, popularity, audience engagement, genres, anime types, studios, source material, and historical release trends. The objective is to identify meaningful descriptive patterns in the dataset and communicate them through clear statistics and visualizations.

> **Analysis-only project:** No Machine Learning, predictive modeling, classification, regression, clustering, or recommendation system is used.

---

## Objective

The main objectives of this project are to:

- Understand the distribution of anime scores.
- Identify highly rated and highly engaged anime.
- Analyze popularity using `Popularity`, `Members`, and `Favorites`.
- Examine genre frequency, average scores, and audience engagement.
- Compare anime types such as TV, Movie, OVA, ONA, Special, and Music.
- Analyze studio production volume and score patterns.
- Compare anime by source material.
- Identify historical release and production trends.
- Examine relationships among important numerical variables using correlation analysis.

---

## Dataset Description

**Dataset:** `anime-dataset-2023.csv`

The completed notebook contains **24,905 anime titles**.

Important fields used in the analysis include:

| Category | Variables |
|---|---|
| Rating | `Score` |
| Popularity | `Popularity`, `Rank` |
| Engagement | `Members`, `Favorites`, `Scored By` |
| Classification | `Genres`, `Type` |
| Production | `Studios` |
| Source | `Source` |
| Time | `Premiered`, `Aired`, `Release_Year` |

### Dataset Scope

The release-year analysis covers anime from **1960 to 2023** after filtering to valid release years.

---

## Data Cleaning & Preparation

The notebook performs the following preparation steps:

### Missing Values

The dataset uses the sentinel value `UNKNOWN` in some fields rather than representing all missing information as standard `NaN`.

Relevant fields are cleaned and converted before analysis.

The calculated notebook summary reports:

- **9,213 titles without a score**
- Approximately **37.0%** of the dataset has a missing score

### Numerical Conversion

Relevant numerical fields were converted to appropriate numeric types, including:

- `Score`
- `Rank`
- `Popularity`
- `Scored By`
- `Members`
- `Favorites`
- `Episodes`
- `Duration_min`

### Genre Processing

Multiple genres are stored together in the `Genres` field. These values were split and exploded into individual genre records so that genre-level counts, scores, and engagement could be analyzed correctly.

### Studio Processing

Multiple studios were similarly split into individual studio records for studio-level analysis.

### Release Year

Release year was extracted into `Release_Year` for historical trend analysis.

---

## Main Analysis Performed

### 1. Score Analysis

The analysis examines:

- Average score
- Median score
- Score distribution
- Highest-rated anime
- Score differences by anime type
- Score differences by genre

The calculated results show:

- **Average score:** 6.38
- **Median score:** 6.39
- **Score range:** 1.85–9.10
- **Highest-rated anime under the notebook's ≥1,000-voter rule:** *Fullmetal Alchemist: Brotherhood* — 9.10

---

### 2. Popularity & Audience Engagement

The project examines:

- Popularity
- Members
- Favorites
- Scored By
- Relationships between score and engagement

The most-member anime in the dataset is:

**Shingeki no Kyojin — 3,744,541 Members**

The notebook also shows that engagement measures are highly right-skewed, meaning a relatively small number of titles account for very large audience counts.

---

### 3. Genre Analysis

The `Genres` column was split into individual genres before analysis.

The most common genre in the dataset is:

**Comedy — 7,142 titles**

Other frequently occurring genres include:

- Fantasy
- Action
- Adventure
- Sci-Fi
- Drama
- Romance
- Slice of Life
- Supernatural

For average-score comparisons, the notebook applies a minimum of **50 scored titles per genre**.

Under that threshold, **Award Winning** has the highest average score at approximately **7.30**.

---

### 4. Anime Type Analysis

The notebook compares:

- TV
- Movie
- OVA
- ONA
- Special
- Music

The number of titles by type is:

| Type | Anime Count |
|---|---:|
| TV | 7,597 |
| Movie | 4,381 |
| OVA | 4,076 |
| ONA | 3,533 |
| Music | 2,686 |
| Special | 2,558 |

For score comparisons, the notebook calculates average and median scores by type.

TV has the highest average score among the listed types at approximately **6.85**.

---

### 5. Studio Analysis

Studio-level analysis examines:

- Production volume
- Average score
- Audience engagement

For average-score comparisons, the notebook uses a minimum threshold of **10 scored titles per studio**.

For production volume, the most prolific studio is:

**Toei Animation — 864 titles**

Other high-volume studios include Sunrise, J.C.Staff, Madhouse, Production I.G, and TMS Entertainment.

---

### 6. Source Analysis

The `Source` field is analyzed by:

- Frequency
- Average score
- Audience engagement

The most common source category is:

**Original — 9,622 titles**

For average-score comparisons, the notebook uses a minimum threshold of **20 scored titles per source**.

Among sources meeting this threshold, **Web novel** has the highest average score at approximately **7.00**, followed by **Light novel** at approximately **6.96**.

---

### 7. Release Trend Analysis

Release trends are analyzed using the extracted `Release_Year`.

The valid historical range used in the notebook is:

**1960–2023**

The highest-production year is:

**2017 — 1,221 anime titles**

The notebook also examines:

- Average score by year
- Seasonal production
- Anime type distribution over time

---

### 8. Correlation Analysis

Correlation analysis examines relationships among numerical variables including:

- Score
- Popularity
- Members
- Favorites
- Scored By
- Episodes
- Duration
- Rank

Some notable calculated correlations include:

| Relationship | Correlation |
|---|---:|
| Score ↔ Popularity | -0.698 |
| Score ↔ Members | 0.391 |
| Score ↔ Favorites | 0.235 |
| Members ↔ Favorites | 0.773 |
| Members ↔ Scored By | 0.989 |
| Favorites ↔ Scored By | 0.785 |

These values describe statistical association only.

> **Important:** Correlation does not imply causation.

---

## Key Findings

1. The dataset contains **24,905 anime titles**, with scores ranging from **1.85 to 9.10**.

2. The average anime score is **6.38**, while the median score is **6.39**.

3. Under the notebook's minimum 1,000-voter condition, **Fullmetal Alchemist: Brotherhood** has the highest score at **9.10**.

4. **Shingeki no Kyojin** has the highest number of Members, with **3,744,541**.

5. **Comedy** is the most common genre, appearing in **7,142 titles** after genre-level processing.

6. **TV** is the most common anime type, with **7,597 titles**, and has the highest average score among the analyzed types at approximately **6.85**.

7. **Toei Animation** is the most prolific studio, with **864 titles**.

8. **Original** is the most common source category, with **9,622 titles**.

9. **2017** has the highest production count in the analyzed release-year range, with **1,221 titles**.

10. `Members` and `Scored By` show a very strong positive correlation (**0.989**), while `Score` and `Popularity` show a strong negative correlation (**-0.698**).

---

## Visualizations

The notebook includes focused visualizations covering:

- Score distribution
- Top-rated anime
- Top anime by Members
- Genre frequency
- Average score by genre
- Anime type comparisons
- Studio comparisons
- Source comparisons
- Anime production by year
- Correlation heatmap
- Score vs Members
- Other engagement relationships

The final report selects only the most important visuals rather than reproducing every notebook chart.

---

## Technologies Used

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Jupyter Notebook**

---

## Project Structure

```text
AnimeDataAnalysis/
│
├── AditiVerma_AnimeDataAnalysis.ipynb
├── requirements.txt
├── AditiVerma_AnimeDataAnalysisReport.docx
├── README.md
└── anime-dataset-2023.csv
```

The CSV is the input dataset; the four files above are the project deliverables.

---

## Installation

### 1. Install Python

Use a supported Python installation and ensure Python and pip are available from the terminal.

### 2. Install project libraries

Open a terminal in the project directory and run:

```bash
pip install -r requirements.txt
```

### 3. Start Jupyter Notebook

Run:

```bash
jupyter notebook
```

Open:

```text
AditiVerma_AnimeDataAnalysis.ipynb
```

Then run the notebook cells from beginning to end.

---

## How to Run the Project

1. Place `anime-dataset-2023.csv` in the project directory.
2. Install the libraries listed in `requirements.txt`.
3. Start Jupyter Notebook.
4. Open `AditiVerma_AnimeDataAnalysis.ipynb`.
5. Run the cells sequentially.
6. Review the calculated tables, charts, and findings.
7. Refer to `AditiVerma_AnimeDataAnalysisReport.docx` for the professional project report.

---

## Analysis Approach

The project follows this workflow:

```text
Raw Dataset
     ↓
Dataset Inspection
     ↓
Data Cleaning & Type Conversion
     ↓
Genre / Studio Expansion
     ↓
Release Year Extraction
     ↓
Descriptive Statistics
     ↓
EDA & Visualization
     ↓
Correlation Analysis
     ↓
Key Findings
     ↓
Conclusion
```

The analysis is intentionally focused on descriptive analytics rather than predictive modeling.

---

## Limitations

The findings should be interpreted within the scope of the dataset.

Key limitations include:

- Some fields contain missing or `UNKNOWN` values.
- A substantial portion of titles does not have a score.
- Engagement metrics such as Members and Favorites can be highly skewed toward popular titles.
- Studio and source comparisons depend on the number of available titles in each category.
- Genre and studio fields can contain multiple values for a single anime.
- Release-year trends depend on the available historical coverage and recorded release information.
- Popularity and engagement measures reflect the dataset's underlying platform context.
- Correlation identifies association and does not establish causation.
- The findings describe patterns in this dataset and should not automatically be generalized to the entire anime industry.

---

## Project Scope

This project is strictly an **Exploratory Data Analysis / descriptive analytics project**.

It does **not** include:

- Machine Learning
- Predictive Modeling
- Classification
- Regression
- Clustering
- Recommendation Systems

The purpose is to understand the data, identify patterns, compare categories, and communicate insights clearly.

---

## Author

**Aditi Verma**

**Project:** Anime Data Analysis — Exploratory Data Analysis

