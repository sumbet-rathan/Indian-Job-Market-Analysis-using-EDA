# Indian Job Market Analysis — Naukri.com EDA

> **A complete end-to-end data science project** — web scraping live job data from Naukri.com, cleaning and engineering features, performing exploratory data analysis across 9 domains, and uncovering actionable insights about the Indian job market.

---

##  Repository Name

```
indian-job-market-analysis-naukri
```

---

##  Project Overview

India's job market is one of the fastest-growing and most competitive in the world. Yet job seekers and career counsellors rarely have access to structured, real-time data about what the market actually looks like.

This project answers that gap by **scraping 1,780+ live job postings** from Naukri.com across **9 domains** and **29 roles**, then performing full EDA, feature engineering, salary imputation, and statistical hypothesis testing to surface market-level insights.

---

##  Key Business Questions Answered

| # | Question |
|---|----------|
| Q1 | Which domain has the highest number of job postings in India right now? |
| Q2 | Which cities are the biggest job hubs across all domains? |
| Q3 | What skills are companies demanding the most? |
| Q4 | What experience range is typically required per role and domain? |
| Q5 | How transparent are companies about salary — and what does disclosed salary look like? |
| Q6 | Which companies are hiring the most across the job market? |
| Q7 | What is the relationship between experience and salary? |

---

##  Project Structure

```
indian-job-market-analysis-naukri/
│
├── Indian_job_market_analysis_naukri.ipynb   # Main notebook (scraping → EDA)
├── Indian_job_market_data.csv                # Raw scraped dataset (1,780 rows)
├── Standardized_Roles_Naukri.csv             # Cleaned dataset with standardized roles
├── Indian_Job_Market_Analysis_Naukri.pptx    # Presentation deck
└── README.md
```

---

##  Project Pipeline

```
Web Scraping (Selenium)
        ↓
Raw Data Storage (Dictionary → DataFrame)
        ↓
Data Cleaning & Role Standardization
        ↓
Feature Engineering (Min/Max Exp, Salary, Work Mode, Employment Type)
        ↓
Salary Imputation (GroupBy Domain + Experience Band)
        ↓
EDA — Univariate & Bivariate Analysis
        ↓
Hypothesis Testing (t-test, ANOVA, Chi-Square, Pearson)
        ↓
Key Findings & Insights
```

---

##  Dataset Details

| Column | Description |
|--------|-------------|
| `domain` | One of 9 job domains (Data & AI, Finance, Healthcare…) |
| `roles` | Raw job title as scraped |
| `roles_standardized` | Cleaned role mapped to 29 standard categories |
| `companies` | Hiring company name |
| `locations` | City of the job posting |
| `experience` | Required experience range (e.g., `0-8 Yrs`) |
| `salaries` | Salary string as listed (e.g., `8-15 Lacs PA`) |
| `skills` | Comma-separated skill tags |
| `Min_Exp / Max_Exp` | Numeric experience bounds extracted via regex |
| `Min_Salary / Max_Salary` | Numeric salary bounds (Lacs PA), NaN-filled by domain + exp |
| `work_mode` | Onsite / Hybrid / Remote (simulated distribution) |
| `employment_type` | Full-time / Contract / Internship (simulated distribution) |
| `job_status` | Active / Filled (simulated distribution) |

**Dataset size:** 1,780 rows × 8 raw columns → 14 columns after feature engineering

---

##  Domains & Roles Covered

| Domain | Roles Scraped |
|--------|--------------|
| **Data & AI** | Data Scientist, ML Engineer, Data Analyst, Data Engineer, AI Engineer |
| **Software Development** | Software Developer, Full Stack, Backend, Frontend, Mobile Dev |
| **Cloud & DevOps** | DevOps Engineer, Cloud Architect, SRE, MLOps |
| **Cybersecurity** | Security Analyst, Ethical Hacker, SOC Analyst |
| **Finance** | Financial Analyst, Investment Banker, Risk Analyst |
| **Business & Management** | Business Analyst, Product Manager, Operations Manager |
| **Marketing** | Digital Marketer, SEO Specialist, Content Strategist |
| **Human Resources** | HR Manager, Talent Acquisition, L&D Specialist |
| **Healthcare** | Clinical Data Analyst, Healthcare IT, Medical Coder |

---

##  Visualizations Included

### Univariate
- Jobs by Domain — Bar Chart
- Jobs by Role — Horizontal Bar Chart
- Work Mode Distribution — Pie Chart
- Employment Type Distribution — Pie Chart
- Salary Distribution — Histogram
- Top Paying Domains — Horizontal Bar Chart
- Experience Distribution — Histogram

### Bivariate
- Experience vs Salary — Scatter Plot
- Domain vs Salary — Box Plot
- Work Mode vs Salary — Box Plot

---

##  Hypothesis Tests

| Hypothesis | Test Used | Result |
|------------|-----------|--------|
| Remote jobs have higher salaries than Onsite | Independent t-test | — |
| Salary depends on domain | One-Way ANOVA | — |
| Employment Type and Work Mode are related | Chi-Square Test | — |
| Experience affects salary | Pearson Correlation | — |

---

##  Key Findings

- **📍 Location:** Bengaluru, Hyderabad, and Mumbai are the top 3 job hubs. Hyderabad dominates in Data & AI and Healthcare.
- **🏢 Domain:** Data & AI and Software Development together represent ~40% of all postings — reflecting India's ongoing tech boom.
- **💰 Salary:** 75%+ of postings did NOT disclose salary. Among disclosed roles, the most common range is **8–15 Lacs PA**. Finance and Data & AI lead in average pay.
- **🛠️ Skills:** Python, Machine Learning, SQL, Communication, and Data Analysis are the top 5 demanded skills across all domains.
- **📅 Experience:** The sweet spot of demand is **3–8 years**. Very few postings target freshers or senior leadership.
- **🏭 Companies:** TCS, Accenture, Infosys, Wipro, and HCLTech are the dominant hirers across multiple domains.
- **🖥️ Work Mode:** Onsite roles dominate (60%). Remote roles (10%) tend to offer slightly higher compensation.

---

##  Tech Stack

| Category | Tools |
|----------|-------|
| **Scraping** | Selenium, ChromeDriverManager, BeautifulSoup |
| **Data** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn, WordCloud |
| **Statistics** | SciPy (t-test, ANOVA, Chi-Square, Pearson) |
| **Environment** | Python 3.x, Jupyter Notebook |

---

##  Setup & Run

```bash
# 1. Clone the repository
git clone https://github.com/YOUR_USERNAME/indian-job-market-analysis-naukri.git
cd indian-job-market-analysis-naukri

# 2. Install dependencies
pip install selenium webdriver-manager beautifulsoup4 pandas numpy matplotlib seaborn scipy wordcloud

# 3. Launch the notebook
jupyter notebook Indian_job_market_analysis_naukri.ipynb
```

>  **Note:** Web scraping requires Google Chrome installed. The notebook uses `ChromeDriverManager` to auto-install the matching driver. If you prefer to skip scraping, the pre-scraped CSV (`Indian_job_market_data.csv`) is included.

---

##  How to Use

1. **Skip scraping** → Load `Indian_job_market_data.csv` directly (Cell 32 onward)
2. **Run full pipeline** → Execute all cells from top (requires Chrome + internet)
3. **EDA only** → Jump to the `Data Visualization` section (Cell 54+)

---

##  Acknowledgements

- Data sourced from **[Naukri.com](https://www.naukri.com)** — India's largest job portal
- Scraped for academic and research purposes only



*Built with Python · Selenium · Pandas · Seaborn · SciPy*

