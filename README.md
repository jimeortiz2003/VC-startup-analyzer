# VC Startup Analyzer

A data-driven tool to evaluate early-stage startups for investment readiness, tailored for aspiring venture capitalists, analysts, and anyone passionate about startup ecosystems.

---

## Problem Statement

Early-stage investors face *information overload* and *inconsistent data* when screening startups. The lack of standardized metrics makes it difficult to compare companies objectively.  
This project develops a **VC Fit Score**—a composite metric integrating funding traction, investor engagement, and startup maturity—to help identify promising companies in large datasets.

---

## Project Goals

- Clean and merge real-world Crunchbase-like datasets  
- Engineer meaningful features such as total funding, number of rounds, company age, and investor count  
- Develop a **VC Fit Score** to rank startups  
- Visualize score distributions and relationships  
- Share insights to illustrate patterns in early-stage venture funding  

---

## Project Structure

| Folder/File         | Description                                   |
|----------------------|-----------------------------------------------|
| `/data/raw/`         | Original CSV datasets                        |
| `/data/processed/`   | Cleaned and scored datasets                  |
| `/notebooks/`        | Jupyter or Colab notebooks                   |
| `/src/`              | Python modules (e.g., cleaning, scoring)     |
| `/outputs/`          | Plots and exports                            |
| `README.md`          | This file                                    |


---

## Analysis Workflow

### 1️. Data Loading

I combined **five datasets**:
- `companies`: metadata about companies
- `rounds`: funding rounds
- `investments`: investor participation
- `acquisitions`: M&A data
- `addition`: additional fields (if available)

Each file contained partial information—**the challenge was to merge them into a coherent view without duplicating or losing records.**

---

### 2️. Data Cleaning

Key steps:
- Removed funding rounds missing `raised_amount_usd`
- Converted amounts to numeric types
- Parsed founding dates
- Merged datasets on `company_permalink` keys
- Filled missing numeric fields with appropriate values (e.g., median age, 0 investors)

> **Insight:**  
> In many real datasets, more than half of the funding rounds are missing dollar amounts. This illustrates why venture analysts often spend significant time cleaning data before any modeling.

---

### 3️. Feature Engineering

I computed:
- **Total Funding (USD)**: cumulative capital raised
- **Number of Funding Rounds**
- **Number of Investors**
- **Company Age (Years)**

These variables were normalized to **0–100 scales** to allow balanced combination.

> **Insight:**  
> Even when funding is disclosed, the number of investors often varies widely. This dimension is important to understand syndicate depth, not just headline funding.

---

### 4️. VC Fit Score

The **VC Fit Score** formula:

0.4 × Funding Score

0.3 × Rounds Score

0.2 × Investor Score

0.1 × Age Score


This reflects an assumption:
- Funding traction is the strongest indicator.
- Engagement of multiple investors signals validation.
- Company age provides context but carries less predictive weight.

> **Critical thinking:**  
> This weighting can be adjusted for different strategies—seed funds might weigh age and rounds more heavily, while growth-stage funds would emphasize cumulative capital.

---

## Visual Insights & Interpretation

### 1. Distribution of VC Fit Scores

![Distribution](outputs/distribution_vc_fit_scores.png)

**Interpretation:**
- The distribution is highly **right-skewed**.
- Most startups have very low VC Fit Scores.
- Only a small subset shows significant traction.

> **What this means:**  
> This pattern reflects the “power law” dynamic in venture capital: a tiny fraction of startups capture most of the investment and attention. The scoring system effectively surfaces these outliers.

---

### 2. Funding vs. Number of Investors

![Scatter](outputs/funding_vs_investors.png)

**Interpretation:**
- While there is some positive correlation between funding and investor count, the relationship is **far from linear**.
- A few companies raised large amounts from only a small syndicate.

> **What this means:**  
> High funding is not always coupled with a diverse investor base. This can highlight startups with strong backing from a single major investor versus those with broader syndication.

---

### 3. VC Fit Score by Industry

![Boxplot](outputs/score_by_industry.png)

**Interpretation:**
- Software and E-Commerce companies tend to have higher median scores.
- Biotech shows a wider spread, reflecting its “moonshot” dynamic.

> **What this means:**  
> Industry segmentation reveals risk-return patterns—some sectors produce consistent traction, while others are more volatile.

---

## Future Enhancements

- Integrate web scraping for live Crunchbase or AngelList data
- Expand the model with additional criteria (e.g., employee count, web traffic, team composition)
- Build an interactive **Streamlit dashboard** to filter and rank startups in real time
- Experiment with different weighting schemes to fit varied investment theses  

---

## Key Takeaways & Reflections

- **Data gaps are the norm** in early-stage investing datasets.
- **Careful normalization and weighting** are critical to avoid biasing scores.
- Visual analysis can surface hidden patterns, such as the concentration of funding among a few companies.
- A scoring framework is a starting point, not a substitute for human judgment—**context matters.**

---

## About Me

*Created by Jimena Ortiz*  
Business Analytics + Finance Student  
Exploring venture capital, fintech, and startup ecosystems.  

If you have feedback or ideas for collaboration, feel free to connect!
