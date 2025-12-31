# Climate Change in Africa: Temperature Analysis (1980-2023)

A comprehensive analysis of temperature trends across four African countries, exploring climate warming patterns through statistical analysis and data visualization.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-green.svg)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-orange.svg)
![Status](https://img.shields.io/badge/Status-Complete-success.svg)

---

##  Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Key Findings](#key-findings)
- [Technical Approach](#technical-approach)
- [Data Quality & Cleaning](#data-quality--cleaning)
- [Visualizations](#visualizations)
- [Technologies Used](#technologies-used)
- [What I Learned](#what-i-learned)
- [How to Run](#how-to-run)


---

##  Project Overview

This project analyzes temperature data from five African countries spanning 43 years (1980-2023) to identify climate change trends and patterns. The analysis focuses on:

- **Temperature trends over time** across different countries
- **Seasonal patterns** and geographic variations
- **Distribution changes** between historical (1980-2000) and recent (2000-2023) periods
- **Evidence of climate warming** through statistical analysis

**Countries Analyzed:** Tunisia, Cameroon, Egypt, Senegal

---

##  Dataset

**Source:** Climate Data (1980-2023)
- **Original Countries:** 5 (Tunisia, Cameroon, Egypt, Senegal, Angola)
- **Final Dataset:** 4 countries (Angola excluded due to data quality issues)
- **Total Records:** 453,308 daily temperature measurements
- **Variables:** 
  - `DATE`: Daily timestamp
  - `TAVG`: Average temperature (°F)
  - `TMAX`: Maximum temperature (°F)
  - `TMIN`: Minimum temperature (°F)
  - `COUNTRY`: Country name

---

##  Key Findings

### 1. **Geographic Climate Differences**
- **Cameroon** (Tropical/Equatorial): Consistently high temperatures (85-100°F) with minimal seasonal variation (~10-15°F range)
- **Tunisia** (Mediterranean): Dramatic seasonal cycles with 50-55°F swings between winter (~40-45°F) and summer (~90-95°F)
- Temperature overlap is minimal: Tunisia's hottest days barely reach Cameroon's coolest temperatures

### 2. **Climate Warming Evidence in Senegal**
- **Mean temperature increase:** 82.7°F (1980-2000) → 83.2°F (2000-2023)
- **Change:** +0.5°F warming over ~23 years
- **Distribution shift:** Entire temperature distribution shifted toward warmer values
- **Extreme events:** Increased frequency of hot days (90-100°F) in recent period; decreased frequency of cooler days (67-75°F)

### 3. **Seasonal Stability vs Variability**
- **Cameroon:** Predictable, stable climate (±5-7°F daily variation)
- **Tunisia:** High variability driven by continental influences (±25-30°F seasonal variation)
- Both countries maintain their characteristic patterns, but at slightly warmer baselines

---

##  Technical Approach

### Data Quality Assessment
Before analysis, I evaluated data quality across all variables:

| Country  | TAVG Missing | TMAX Missing | TMIN Missing | Decision |
|----------|--------------|--------------|--------------|----------|
| Tunisia  | 0.0%         | 21.6%        | 30.3%        | ✅ Keep   |
| Cameroon | 0.0%         | 43.3%        | 40.9%        | ✅ Keep   |
| Senegal  | 0.8%         | 17.4%        | 28.6%        | ✅ Keep   |
| Egypt    | 1.7%         | 16.0%        | 19.3%        | ✅ Keep   |
| Angola   | 19.3%        | 87.7%        | 84.2%        | ❌ Drop   |

**Decision rationale:** Angola's data quality was insufficient, particularly for the critical 1980-1990 period where ~100% of data was missing.

---


##  Visualizations

### 1. Temperature Trends: Tunisia vs Cameroon (1980-2023)
**Tool:** Matplotlib, Seaborn, Plotly

**Insight:** Clear visualization of geographic climate differences - Tunisia's pronounced seasonal waves vs Cameroon's stable tropical pattern.

### 2. Temperature Trends: Tunisia vs Cameroon (1980-2005, Zoomed)
**Tool:** Plotly (interactive)

**Customization:** Custom axis labels, color coding, interactive hover details for detailed exploration.

### 3. Temperature Distribution: Senegal (1980-2000 vs 2000-2023)
**Tool:** Matplotlib

**Insight:** Histogram comparison revealing:
- 0.5°F mean temperature increase
- Rightward shift in entire distribution
- Increased frequency of extreme heat events
- Decreased frequency of cooler days

---

##  Technologies Used

- **Python 3.8+**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Static visualizations
- **Seaborn** - Statistical data visualization
- **Plotly** - Interactive visualizations
- **Google Colab** - Development environment

---

##  What I Learned

### Data Science Concepts
1. **When to use different imputation methods:**
   - Time series data requires interpolation, not median/mean
   - Data structure determines cleaning approach
   - Groupby operations for handling multi-category datasets

2. **Data quality decision-making:**
   - How to assess missing data percentages
   - When to drop variables/observations vs impute
   - Trade-offs between data quantity and quality

3. **Visualization selection:**
   - Line charts for time series trends
   - Histograms for distribution comparisons
   - Bar charts for categorical comparisons
   - When each chart type is most appropriate

### Technical Skills
- Advanced pandas operations (groupby, transform, filtering)
- Time series data handling and date parsing
- Multiple visualization libraries (Matplotlib, Seaborn, Plotly)
- Data cleaning pipeline development
- Statistical interpretation of results


##  How to Run

### Option 1: Google Colab (Recommended)
1. Open the notebook in [Google Colab](https://colab.research.google.com/)
2. Upload your dataset or connect to Google Drive
3. Run all cells sequentially

### Option 2: Local Jupyter Notebook
```bash
# Clone repository
git clone https://github.com/yourusername/climate-change-africa-analysis.git
cd climate-change-africa-analysis

# Install dependencies
pip install pandas numpy matplotlib seaborn plotly

# Launch Jupyter
jupyter notebook climate_analysis_africa.ipynb
```

---


---


##  Acknowledgments

- Climate data source: [Dataset link](https://drive.google.com/file/d/1I8eV4-8p61CNNlVJzzho2xeoZ5-P7Q0F/view)
- Dataset was provided by the U.S global change research program.
- Created as part of data science learning journey through GOMYCODE Checkpoint

---

*This project demonstrates practical data science skills including data cleaning, exploratory data analysis, statistical interpretation, and data visualization. It showcases the ability to handle real-world messy data and extract meaningful insights.*
