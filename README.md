# Suicide Rates in Singapore: A Data Analysis

An exploratory data analysis (EDA) and natural language processing (NLP) study investigating 
the major social determinants contributing to rising suicide rates in Singapore, and how 
those determinants interact with interventions by the Samaritans of Singapore (SOS).

This project was submitted for CM2015: Programming with Data.

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NLTK](https://img.shields.io/badge/NLTK-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Maintenance](http://unmaintained.tech/badge.svg)

---

## Research Question

What are the major social determinants contributing to the increasing suicide rates in 
Singapore, and how do these determinants interact with SOS interventions?

---

## Datasets

| # | Dataset | Format | Source |
|---|---|---|---|
| 1 | Suicide Rates Overview (1985-2021) | CSV | Kaggle (compiled from WHO, World Bank, UNDP) |
| 2 | Hospital Admission Rate by Age and Sex | CSV | Ministry of Health (MOH), data.gov.sg |
| 3 | Long-Term Unemployed Residents, Annual | CSV | Ministry of Manpower (MOM), data.gov.sg |
| 4 | SOS Annual Reports (2016-2021) | PDF | Samaritans of Singapore (SOS) |
| 5 | Public Opinion on SOS | Web (Reddit API via PRAW) | r/singapore |

---

## Methodology

**Data Preparation**
Datasets were filtered to Singapore-specific records, cleaned for missing values, and merged 
on a shared time axis (2016-2021). Feature engineering included age group remapping, comma 
removal for numeric parsing, and mean imputation for missing values.

**Exploratory Data Analysis (EDA)**
Correlation analysis was performed across variables including GDP, HDI, long-term 
unemployment, psychiatric hospital admissions, SOS community outreach activity, and calls 
with suicide risk. Seaborn heatmaps and distribution plots were used to surface patterns 
across demographic groups (age, sex).

**Natural Language Processing (NLP)**
Reddit posts from r/singapore were scraped using PRAW (Python Reddit API Wrapper). Text 
was tokenized, lemmatized, and filtered of stopwords using NLTK, then visualized as a 
word cloud to surface dominant themes in public sentiment toward SOS.

---

## Key Findings

**Unemployment** showed a high positive correlation with suicide risk calls, suggesting 
that economic stress is a significant driver of mental health deterioration in Singapore.

**Community outreach** by SOS correlated with rising suicide rates, interpreted as a 
reactive relationship: as rates climbed, SOS expanded its outreach efforts including 
crisis hotlines, counseling, and psychiatric referrals to institutions such as IMH.

**Psychiatric hospital admissions** showed a negative correlation with suicide rates, 
suggesting that access to structured mental health care may be associated with reduced 
suicide risk.

**Public sentiment analysis** of Reddit discussions revealed that mental health, community 
support, and personal crises (unemployment, relationships) were the dominant themes in 
conversations relating to SOS, consistent with the quantitative findings.

---

## Getting Started

**Prerequisites:** Python 3.x, Jupyter Notebook, Git

```bash
# Clone the repository
git clone https://github.com/mlemxy/suicide-analysis

# Create and activate a virtual environment
py -m venv .venv
.venv\scripts\activate

# Install dependencies
pip install -r requirements.txt

# Add your Reddit API credentials in .env

# Launch the notebook
jupyter notebook suicide_rate.ipynb
```

> Note: Reddit data collection via PRAW requires a Reddit API key stored in `.env`.
