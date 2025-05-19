# Project Title: Digitalization Extent of Top Performing Manufacturing Companies in the Lithuanian Manufacturing Industry
This data analytics project is a part of my Master Thesis in the topic "Digitalization Extent of Top Performing Manufacturing Companies in the Lithuanian Manufacturing Industry". The analysis aiming to find digital technologies adopted in the industry and find out if the adoption levels vary between top performers and others, and if this variance is the real cause of the competitive advantage why top performers are forefront of their rivals.

## Project Overview

This project aims to investigate the relationship between the level of digitalization and business performance within companies in the manufacturing industry. Utilizing a dataset containing information on various digital technology adoption levels and financial metrics, the analysis identifies top-performing companies and examines how their digitalization strategies differ from others.

## Data

The analysis uses data from a survey focusing on digital technology adoption in the manufacturing sector. The dataset includes information on:

*   Financial metrics (e.g., annual turnover, profit before tax, net profit)
*   Company size (number of employees)
*   Industry sector
*   Adoption of various digital technologies across different functional domains (Production Planning, Automation, Design, HMI, Data Management, Supply Chain Integration).

## Methodology

The data analysis follows these key steps:

1.  **Data Loading and Initial Cleaning:**
    *   The data is loaded from an SPSS `.SAV` file.
    *   Irrelevant columns, particularly those related to technology adoption year with significant missing values, are dropped.
    *   Columns containing key financial metrics and digital technology adoption data are selected for further analysis.
    *   Columns are renamed for clarity and ease of use.

2.  **Missing Value Handling:**
    *   Missing values in digital technology adoption columns are identified and handled by replacing them with a specific value (-1) to indicate 'Not Applicable' or unanswered questions, allowing for later exclusion in relevant calculations.
    *   Rows with missing 'annual\_turnover' are dropped due to their limited number and inability to be reliably imputed.
    *   The percentage of missing values and 'Not Applicable' responses are examined.

3.  **Data Transformation and Structuring:**
    *   Detailed industry sectors are mapped to broader, more general sectors for consolidated analysis.
    *   Company sizes are categorized into groups based on the number of employees.

4.  **Identifying Top Performing Companies:**
    *   A weighted performance score is calculated based on 'annual\_turnover' and 'num\_employees', giving higher weight to annual turnover.
    *   Companies are classified into "Top Performing" and "Other" categories based on a quantile threshold of the calculated performance score.

5.  **Analyzing Digitalization by Functional Domain:**
    *   Digital technologies are grouped into functional domains (e.g., Production Planning, Automation, Data Management).
    *   An adjusted average score is calculated for each functional domain for each company, considering only answered questions and normalizing by the number of questions in the domain.

6.  **Comparing Digitalization Levels:**
    *   The distribution of the calculated functional domain scores is visualized for the overall dataset and by performance class.
    *   Average digitalization scores per functional domain are compared between "Top Performing" and "Other" companies.

7.  **Correlation Analysis:**
    *   Spearman correlation is used to examine the relationship between functional domain digitalization scores and the performance score.
    *   Correlations between overall digitalization score, performance score, and annual turnover are explored.
    *   Sector-specific correlations between digital functions and performance are calculated and visualized.

8.  **Statistical Testing:**
    *   Cronbach's alpha is calculated to assess the internal consistency of the functional domain groupings.
    *   Independent samples t-tests are conducted to statistically compare the mean functional domain scores between "Top Performing" and "Other" companies.

9.  **Visualization:**
    *   Various plots (histograms, bar charts, box plots, heatmaps, scatter plots) are used throughout the analysis to visualize data distributions, comparisons, and relationships.

## Key Findings (Based on the Analysis in the Notebook)
1. The descriptive analysis revealed that the Lithuanian manufacturing sector, represented by the sample, is largely composed of small and medium-sized enterprises (SMEs).
2. The overall distribution of digitalization scores indicated that the majority of companies exhibited low to moderate levels of digitalization
3. Foundational technologies like Production Planning and Control and Design and Prototyping showed relatively broader adoption than more advanced or integrative technologies such as Automation and Robotics and Supply Chain Integration, which were less embedded.
4. A clear association between company size and digital technology adoption was observed, with mid-sized and larger firms exhibiting higher median digitalization scores than micro and small enterprises.
5. The core empirical finding was that top-performing firms consistently exhibited significantly higher mean digitalization scores across all six functional domains than their lower-performing counterparts.

## Dependencies
The following Python libraries are required to run the notebook:

*   `pyreadstat`
*   `pandas`
*   `numpy`
*   `seaborn`
*   `matplotlib`
*   `sklearn` (for `MinMaxScaler`, `train_test_split`, `mean_squared_error`, `r2_score`)
*   `scipy` (for `ttest_ind`, `kstest`, `norm`, `zscore`)
*   `pingouin` (for `cronbach_alpha`)
