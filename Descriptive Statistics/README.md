# Typical Employee Survey Analysis

**Author:** Shreya Sinha  
**Date:** September 19, 2026  
**Language:** R

## Project Overview

This project analyzes the Typical Industries Employee Survey dataset using R. The goal is to explore employee demographics, job satisfaction, workplace experiences, career expectations, and organizational loyalty through descriptive statistics and data visualization.

The analysis includes five-point summaries, boxplots, factor conversion, histograms, bar plots, scatter plots, and an additional heatmap to explore relationships between survey responses.

## Dataset

The dataset, `Typical_Employee_Survey_Data_Updated.csv`, contains employee survey responses covering the following variables:

- Age
- Gender
- Job satisfaction
- Most important job characteristic
- Years worked for the current employer
- Promotion likelihood
- Workplace decision-making participation
- Budgetary decision participation
- Organizational pride
- Likelihood of turning down another job for more pay
- Coworker and workplace relations

## 1. Five-Point Summary and Boxplots (20 Points)

I used R's `fivenum()` function to calculate the five-point summary for each column, including the minimum, lower hinge, median, upper hinge, and maximum.

The five-point summaries were generated for all 11 variables. However, age and years worked are the two numerical variables for which boxplots were created.

The results for the numerical variables were:

| Statistic | Age | Years Worked |
|---|---:|---:|
| Minimum | 20 | 0.08 |
| Lower hinge | 33 | 2 |
| Median | 38 | 5 |
| Upper hinge | 44 | 11 |
| Maximum | 64 | 52.25 |

Boxplots were used to visualize the distributions and identify potential outliers in age and years worked.

## 2. Converting Columns to Factors (20 Points)

I converted the nine categorical survey variables into factors using R's `as.factor()` function.

These variables include:

- Gender
- Satisfaction
- Job Characteristic
- Promotion Likeliness
- Decision Making
- Budget Decision
- Proud
- Turn Down
- Relations

This step ensures that the coded survey responses are treated as categorical variables rather than continuous numerical measurements.

## 3. Visual Representation of Each Column (20 Points)

I selected visualizations based on the type of data being analyzed.

- **Histogram for Age:** Used to explore the distribution of employee ages.
- **Histogram for Years Worked:** Used to examine employee tenure.
- **Bar plots for categorical variables:** Used to display response frequencies for gender, satisfaction, job characteristics, promotion likelihood, decision-making participation, budget participation, organizational pride, willingness to remain with the organization, and workplace relations.

These visualizations provide a clear way to examine the distribution of employee characteristics and survey responses.

## 4. Scatter Plots and Relationships (20 Points)

I created two scatter plots to explore relationships between employee characteristics and career expectations.

**Age vs. Years Worked**

This plot examines the relationship between employee age and the number of years they have worked for their current employer.

**Years Worked vs. Promotion Likeliness**

This plot explores how employee tenure relates to their coded responses about promotion likelihood.

These plots provide a visual starting point for investigating relationships between employee tenure, age, and career expectations.

## 5. Extra Analysis: Heatmap

As an additional visualization, I created a heatmap comparing promotion likelihood with the likelihood of turning down another job for more pay.

The heatmap uses a frequency table of the two categorical survey variables:

- Promotion Likeliness
- Turn Down

The color scale represents the frequency of employees in each combination of responses. This visualization helps compare patterns between career expectations and organizational loyalty.

## Tools and Technologies

- **R:** Data analysis and statistical computing
- **RStudio:** Development environment
- **Base R:** Summary statistics, factor conversion, histograms, boxplots, bar plots, scatter plots, and heatmap visualization

## Key Learning Outcomes

Through this project, I practiced:

- Calculating five-point summaries using `fivenum()`.
- Creating boxplots to examine numerical distributions.
- Converting categorical survey variables into factors.
- Selecting appropriate plots for numerical and categorical data.
- Using scatter plots to explore relationships between variables.
- Creating a heatmap to compare combinations of survey responses.
- Applying exploratory data analysis techniques to employee survey data.

## Conclusion

This project demonstrates how R can be used to explore employee survey data through descriptive statistics and visualizations. The analysis covers employee demographics, tenure, satisfaction, promotion expectations, and organizational loyalty.

The additional heatmap extends the analysis by examining the relationship between promotion likelihood and willingness to remain with the organization. Together, these techniques provide a foundation for understanding employee characteristics and workplace attitudes.



