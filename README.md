
<br><br>

![2129d7ad-6afd-4166-9bf1-a4f9c3b9e5cc](https://github.com/user-attachments/assets/faf3e0a3-3610-4c0b-99bb-afb7a765f28d)

<br><br>

## <p align="center">  Practical Stats - PUCSP  2nd Semester 2024 

<br>

#### <p align="center"> [![Sponsor FabianaCampanari ](https://img.shields.io/badge/Sponsor-FabianaCampanari-brightgreen?logo=GitHub)](https://github.com/sponsors/FabianaCampanari)

<br>


## **Statistics and Probability**
 
This repository, created by [Fabiana 🚀 Campanari](https://linktr.ee/fabianacampanari) in the 2nd semester of 2024, consolidates the materials and code developed for the Statistics and Probability course within the Data Science and Artificial Intelligence program at PUC-SP, under the guidance of [Professor Eric Bacconi Gonçalves](https://www.linkedin.com/in/eric-bacconi-423137/)
). It is designed to support hands-on learning through exercises, scripts, and datasets.

## Repository Contents:

<br>

- **Python Scripts**: This section includes scripts for a wide range of statistical analyses, covering key topics such as distributions, population and sample concepts, and hypothesis testing. Calculations include:
  - **Central Tendency**: Mean, median, and mode
  - **Dispersion**: Standard deviation, variance, and range
  - **Positional Measures**: Percentiles and quartiles (Q1, Q2, Q3)
  - **Distribution Shape**: Skewness and kurtosis
  - **Confidence Intervals** for estimating population parameters
  - **Correlation and Covariance** for bivariate analysis
 
 <br>   

- **Practical Exercises**: Available in Python and Excel, these exercises provide hands-on practice in calculating statistical measures and applying concepts, including:
  - **Analysis of Variance (ANOVA)**: Comparing means across multiple groups
  - **Hypothesis Testing**: Null hypothesis (\( H_0 \)) tests, such as T-tests (one-sample, independent, and paired), ANOVA, and Chi-square tests
  - **Regression Analysis**: Linear regression models for predictive analysis
  - **Probability**: Exercises covering probability distributions, expected value, and variance
 
 <br>   

- **Statistical Tests**: This section includes implementations of statistical tests tailored to analyze variables like age and salary, categorized by region and educational level. Each test includes the process of setting up and testing the null hypothesis (\( H_0 \)) for statistical significance.

<br>  

- **Support Materials**: Supplementary documentation on probability, relevant datasets, and homework assignments to reinforce key concepts.

<br>

## Study Topics:

This repository provides a comprehensive foundation in core topics, including Descriptive Statistics, Probability Distributions, Population and Sample, Hypothesis Testing I and II (featuring null hypothesis (\( H_0 \)) testing), and Regression Analysis. It serves as a practical tool for building statistical and analytical skills.


## Statistical Measures Analysis in Python

This repository contains Python scripts for descriptive statistical analysis of employee salary and age data, including analyses for the entire dataset as well as subgrouped by education level and region.

## Features:

Descriptive statistics: Mean, Median, Mode, Variance, Standard Deviation, Coefficient of Variation (CV), and Amplitude (Range).
Grouped analysis: The same statistics calculated by grouping data based on region and education level.
Designed for students: Easy-to-follow code with comments and explanations for each step.

<br>

## Dataset:

The dataset used in this analysis contains employee details, including their age, salary, region of origin (reg_proc), and education level (grau_instrucao).
[Click here to get the Dataset](https://github.com/FabianaCampanari/statisticalMeasures-python-/tree/a9e92b1cbce36fa5f26edeadef937981012f0a98/Dataset)

<br>

## Getting Started:

### To run this script, ensure you have the following:

- Python 3 installed.

- Necessary libraries (pandas) installed.

- An Excel file containing the dataset in the appropriate format.


## Codes

### 1. Statics Measures

```python

Copy code

# Importing the necessary library
import pandas as pd

# Define the file path to the dataset
file_path = 'add_your_dataset_path_here'

# Load the dataset into a DataFrame
df = pd.read_excel(file_path)

# Display the first few rows of the dataset
df.head()

# --- Descriptive Statistics for 'SALARIO' (salary) ---

# Generate descriptive statistics for the 'SALARIO' column
print("Descriptive statistics for 'SALARIO':")
print(df.salario.describe())

# Calculate the range (amplitude) of the 'SALARIO' column
ampl_salario = df['salario'].max() - df['salario'].min()
print("\nAmplitude of 'SALARIO':", ampl_salario)

# Calculate the mode of the 'SALARIO' column
moda_salario = df.salario.mode()[0]
print("\nMode of 'SALARIO':", moda_salario)

# Calculate the variance of the 'SALARIO' column
var_salario = df.salario.var()
print("\nVariance of 'SALARIO':", var_salario)

# Calculate the coefficient of variation (CV) for 'SALARIO'
cv_salario = df.salario.std() / df.salario.mean()
print("\nCoefficient of variation (CV) of 'SALARIO':", cv_salario)

# --- Descriptive Statistics for 'SALARIO' by 'grau_instrucao' (educational level) ---

# Generate descriptive statistics for 'SALARIO' grouped by 'grau_instrucao' (education level)
print("\nDescriptive statistics for 'SALARIO' grouped by 'grau_instrucao':")
print(df.groupby('grau_instrucao')['salario'].describe())

# Calculate the range (amplitude) of 'SALARIO' by 'grau_instrucao'
ampl_salario_grau = df.groupby('grau_instrucao')['salario'].max() - df.groupby('grau_instrucao')['salario'].min()
print("\nAmplitude of 'SALARIO' by 'grau_instrucao':")
print(ampl_salario_grau)

# Calculate the mode of 'SALARIO' by 'grau_instrucao'
moda_salario_grau = df.groupby('grau_instrucao')['salario'].agg(lambda x: pd.Series.mode(x)[0])
print("\nMode of 'SALARIO' by 'grau_instrucao':")
print(moda_salario_grau)

# Calculate the variance of 'SALARIO' by 'grau_instrucao'
var_salario_grau = df.groupby('grau_instrucao')['salario'].var()
print("\nVariance of 'SALARIO' by 'grau_instrucao':")
print(var_salario_grau)

# Calculate the coefficient of variation (CV) for 'SALARIO' by 'grau_instrucao'
cv_salario_grau = df.groupby('grau_instrucao')['salario'].std() / df.groupby('grau_instrucao')['salario'].mean()
print("\nCoefficient of variation (CV) of 'SALARIO' by 'grau_instrucao':")
print(cv_salario_grau)

# Summary of key descriptive statistics
print("\nSummary for 'SALARIO' as a Whole:")
print(f"\nAmplitude: {ampl_salario}")
print(f"\nMode: {moda_salario}")
print(f"\nVariance: {var_salario}")
print(f"\nCoefficient of variation (CV): {cv_salario}")

print("\nSummary by 'grau_instrucao':")
print(f"\nAmplitude by 'grau_instrucao': \n{ampl_salario_grau}")
print(f"\nMode by 'grau_instrucao': \n{moda_salario_grau}")
print(f"\nVariance by 'grau_instrucao': \n{var_salario_grau}")
print(f"\nCoefficient of variation (CV) by 'grau_instrucao': \n{cv_salario_grau}")
```

<br>

### 2. Sample Selection

```python

Copy code

# Import pandas and numpy libraries
import pandas as pd
import numpy as np

# Define the file path
file_path = 'add_your_dataset_path_here'

# Read the Excel file into a DataFrame
df = pd.read_excel(file_path)

# Sample Selection

# Simple random sample without replacement with 20 elements
sample = df.sample(20, replace=False)
print(sample)

# Simple random sample without replacement with 20 elements (fixing the random seed)
sample = df.sample(n=20, replace=False, random_state=2903)
print(sample)

# Check the classes of the variable and their proportions
perc_est_civ = df["estado_civil"].value_counts(normalize=True)
print(perc_est_civ)

# Execute equal stratified sample by marital status
sample_strat_equal = df.groupby(['estado_civil'], group_keys=False).apply(lambda x: x.sample(n=10, replace=False, random_state=2903))
print(sample_strat_equal)

# Define desired total
N = 20

# Execute proportional stratified sample by marital status
sample_strat_prop = df.groupby(['estado_civil'], group_keys=False).apply(
    lambda x: x.sample(int(np.rint(N * len(x) / len(df))), random_state=2903)  # Proportional sample calculation
).sample(frac=1, random_state=2903).reset_index(drop=True)  # Shuffle the sample
print(sample_strat_prop)

# Check the proportion of each marital status
perc_est_civ = sample_strat_prop["estado_civil"].value_counts(normalize=True)
print(perc_est_civ)

# Execute equal stratified sample by region of origin
sample_strat_equal = df.groupby(['reg_proc'], group_keys=False).apply(lambda x: x.sample(n=10, replace=False, random_state=2903))
print(sample_strat_equal)

# Execute equal stratified sample by education level
sample_strat_equal = df.groupby(['grau_instrucao'], group_keys=False).apply(lambda x: x.sample(n=10, replace=False, random_state=2903))
print(sample_strat_equal)

# Execute equal stratified sample by region of origin and education level
sample_strat_equal = df.groupby(['reg_proc', 'grau_instrucao'], group_keys=False).apply(lambda x: x.sample(n=10, replace=False, random_state=2903))
print(sample_strat_equal)

# Create an equal stratified sample by education level and region of origin
sample_strat_equal = df.groupby(['grau_instrucao', 'reg_proc'], group_keys=False).apply(lambda x: x.sample(n=min(len(x), 10), replace=False, random_state=2903)).reset_index(drop=True)
print(sample_strat_equal)

# Save the stratified sample to a new Excel file
output_path = 'path_to_save_sample/stratified_sample.xlsx'
sample_strat_equal.to_excel(output_path, index=False)

print(f"The stratified sample has been saved to {output_path}")
```   

<br>

### 3. One-Sample t-Test

```python
Copy code

# Exercise 3 – Test the hypothesis that the salary is equal to 12. What is your conclusion?
# Import pandas library
import pandas as pd

# Import scipy library
import scipy.stats as stats

# File path
file_path = 'add_your_dataset_path_here'

# Load the file into Python
df = pd.read_excel(file_path)
print(df.head())

# Bring only the age variable to perform the test
base_age = df['idade']

# Execute the t-test testing H0: age = 32 and H1: age ≠ 32
result_t_test = stats.ttest_1samp(base_age, 32)
p_value = result_t_test.pvalue
alpha = 0.05

if p_value < alpha:
    print("We reject the null hypothesis (H0).")
else:
    print("We do not reject the null hypothesis (H0).")

# Remember the mean
print(f"Mean age: {df.idade.mean()}")

# Execute the t-test testing H0: age = 34 and H1: age ≠ 34
result_t_test = stats.ttest_1samp(base_age, 34)
p_value = result_t_test.pvalue
alpha = 0.05

# Decision based on p-value
if p_value < alpha:
    print("We reject the null hypothesis (H0).")
else:
    print("We do not reject the null hypothesis (H0).")

# With a p-value of 0.045, which is less than the significance level of 0.05, we reject the null hypothesis. This indicates that there is statistically significant evidence to suggest that the average age of employees is different from 34.

# Execute the t-test testing H0: age = 35 and H1: age ≠ 35
result_t_test = stats.ttest_1samp(base_age, 35)
p_value = result_t_test.pvalue
alpha = 0.05

# Decision based on p-value
if p_value < alpha:
    print("We reject the null hypothesis (H0).")
else:
    print("We do not reject the null hypothesis (H0).")

# With a p-value of 0.2234, which is greater than the significance level of 0.05, we do not reject the null hypothesis. This means that there is not enough evidence to conclude that the average age of employees is different from the hypothesized value (32, 35, or any other value being tested).

# Answering question 3

# Test the hypothesis that the salary is equal to 12. What is your conclusion?
import pandas as pd
import scipy.stats as stats

# File path
file_path = 'add_your_dataset_path_here'

# Load the data
df = pd.read_excel(file_path)
print(df.head())

# Select the variable of interest (salary)
salaries = df['salario']

# Execute the t-test testing H0: salary = 12 and H1: salary ≠ 12
result_t_test = stats.ttest_1samp(salaries, 12)
print(result_t_test)

# Get the p-value from the test result
p_value = result_t_test.pvalue

# Define the significance level
alpha = 0.05

# Interpret the result
p_value = 8.755117588192511e-06

if p_value < alpha:
    print("We reject the null hypothesis (H0).")
else:
    print("We do not reject the null hypothesis (H0).")

# Define the conclusion based on the p-value and the significance level
if p_value < alpha:
    conclusion = "We reject the null hypothesis (H0)."
else:
    conclusion = "We do not reject the null hypothesis (H0)."

# Display the test result and conclusion
print(f"t-test statistic: {result_t_test.statistic}")
print(f"p-value: {result_t_test.pvalue}")
print(conclusion)

# Analysis and Conclusion with p-value and significance level

# In the hypothesis test performed, we tested the null hypothesis (H0) that the average salary of employees is equal to 12 against the alternative hypothesis (H1) that the average salary of employees is different from 12.

# The results of the t-test were as follows:
# - t-test statistic: -4.500727991746298
# - p-value: 8.755117588192511e-06

# With a p-value of approximately 8.76e-06, which is significantly less than the significance level of 0.05, we reject the null hypothesis (H0). This indicates that there is statistically significant evidence to suggest that the average salary of employees is different from 12.

# Therefore, the conclusion of the test is that we reject the null hypothesis (H0) and accept the alternative hypothesis (H1), indicating that the average salary of employees is not equal to 12.
```
<br>

### 4. Two-Sample t-Test

```python

copy code

### Question 4

#### To test the hypothesis that income is equal for the two marital statuses (single and married), we can use the t-test for independent samples. We will follow these steps:
### Visualization

#### 1. Extract income data for singles and married individuals.
#### 2. Perform the t-test for independent samples.
#### 3. Interpret the p-value to accept or reject the null hypothesis.

### Steps in pseudocode:

1. **Import necessary libraries** (pandas and scipy.stats).
2. **Load data from the Excel file**.
3. **Extract income columns for singles and married individuals**.
4. **Perform the t-test for independent samples**.
5. **Interpret the result based on the p-value**.

# Install scipy if necessary
# %pip install scipy pandas
import pandas as pd
from scipy import stats

# Load the data from the Excel file
file_path = '/Users/fabicampanari/Desktop/_8-Prova Matematematica/1-statiscalMeasures_ Hypothesis Testing II./1🇧🇷-statiscalMeasures_ Hypothesis Testing II./answeredCodes_statiscalMeasures/cadastro_funcionarios.xlsx'
df = pd.read_excel(file_path)

# Visualize the first rows of the DataFrame
print(df.head())

# Check the mean salary by marital status group
print(df.groupby(['estado_civil'])['salario'].describe())

# Extract income columns for singles and married individuals
single_income = df[df['estado_civil'] == 's']['salario']
married_income = df[df['estado_civil'] == 'c']['salario']

# Perform the t-test for independent samples
t_stat, p_value = stats.ttest_ind(married_income, single_income, equal_var=False)

# Display the results of the t-test
print("Results of the t-Test:")
print(f"t-statistic: {t_stat}")
print(f"p-value: {p_value}")

# Interpret the result
alpha = 0.05
if p_value < alpha:
    print("Conclusion: We reject the null hypothesis. The incomes are different for the two marital statuses.")
else:
    print("Conclusion: We do not reject the null hypothesis. The incomes are equal for the two marital statuses.")

### Conclusion Results of the t-Test:

#### Interpretation:
 - t-statistic: 4.567472731259726 <br>
 - p-value: 6.527014259249644e-06

The p-value is extremely small (6.527014259249644e-06), much smaller than the common significance level (0.05). This indicates that there is a significant difference in income between the two marital statuses.

**Conclusion:**

We reject the null hypothesis. The incomes are different for the two marital statuses (single and married).
```














































 

<br><br>

<p align="center"> <a href="#top">Back to Top</a>


#
###### <p align="center"> Copyright 2024 Fabiana Campanari. Code released under the [MIT license.](https://github.com/FabianaCampanari/FabianaCampanari/blob/66325d147794b5fc4688d56e6b78e8cdf42946e4/LICENSE)


