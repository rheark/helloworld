# World Life Expectancy


## About
This is a mini project with the aim to gain more insight regarding world life expectancy. It is based on WHO national life expectancy dataset we obtained from kaggle (https://www.kaggle.com/datasets/mmattson/who-national-life-expectancy)

## Contributors
- Bong Jia Hui (@bjiah) - Machine Learning
- Celine Tan (@Cttan178) - Data Preparation and Cleaning
- Rhea Kenneth (@rheark) - Exploratory Data Analysis

## Github Folder
### SC1015_DSF3_World_Life_Expectancy.pdf
Our presentation slide which provides a brief summary of our project. It covers the details on how we derived our problem statement, the insights we obtained through EDA, how the machine learning model help us to answer our problem statment and the conclusion we obtained from our work.

### DSF3_LifeExpectancy.ipynb
Detailed walkthrough of analysing the national life expectancy dataset
- Contents of our notebook:
1. Data cleaning
2. Exploratory data analysis (global life expectancy)
3. Machine learning (global)
4. Exploratory data analysis (regional life expectancy)
5. Machine learning (regional)

### who_life_exp.csv
CSV file of WHO national life expectancy dataset.

### Regional Life Expectancy plotly graphs
PNG files of regional life expectancy trend graphs. Interactive feature of the plotly graphs can be explored in the jupyter notebook under Regional EDA.

### World Heat Map
https://docs.google.com/spreadsheets/d/1kfqoC_7yLZKGK2kwxgCjtqN_ah8raVBW9GACsrJ2KKU/edit?usp=sharing
Link to the world heat map that we have included in our presentation slide. The world heat map show the distribution of life expectancy for each country in year 2016. One can move through the world map to get details of the particular country and its respective life expectancy in 2016.

## Motivation & Problem Statement
The motivation behind our problem statement is the stereotype that people living in less developed countries tend to have worse health conditions that lead to low life expectancy compared to those in developed countries. Thus, we would like to find out if it is a fact or if it is just a myth that people are exposed to on social media. For example, a stereotype is that most African kids are suffering from diseases due to severe malnutrition. By investigating the factors affecting life expectancy, we hope to figure out what possible solutions can be implemented in order to narrow down the inequality gap if there is one. <br />
This leads to our problem statement: <br />
**Does life expectancy inequality really exist and if yes, what are the indicators of such scenarios and are there possible solutions to narrow the inequality?**

## Dataset Description
- This national life expectancy dataset is provided by World Health Organization (WHO) which referenced information from Global Health Observatory (GHO) and United Nations Educational Scientific and Culture Organization (UNESCO).
- The dataset consists of life expectancy of 183 countries covering the years 2000-2016.
- Some of the variables from UNESCO datasets overlapped with the variables from GHO datasets and there are also significant number of missing values, which is around 70% in those variables. Thus, we decided to remove the variables which are hospitals, une_poverty, une_edu_spend, une_literacy, une_school from UNESCO datasets.
- Following are the data description for the variables we have included:

| Data            | Data Description                                                                                        |
| -------------   | --------------------------------------------------------------------------------------------------------|             
| country         | Country name                                                                                            |
| region          | Global region of country                                                                                |
| year            | year                                                                                                    |
| life_expect     | Life expectancy at birth (years)                                                                        | 
| life_exp60      | Life expectancy at age 60 (years)                                                                       |
| adult_mort_rate | Adult Mortality Rates of both sexes (probability of dying between 15 and 60 years)                      |
| infant_mort_rate| Death rate up to age 1                                                                                  | 
| age1-4_mort_rate| Death rate between ages 1 and 4                                                                         |
| alcohol         | Alcohol, recorded per capita (15+) consumption (in litres of pure alcohol)                              |
| bmi             | Mean BMI (kg/m^2) (18+) (age-standardized estimate)                                                     |
| age5-19thinness | Prevalence of thinness among children and adolescents, BMI < (median - 2 s.d.) (crude estimate) (%)     |
| age5-19obesity  | Prevalence of obesity among children and adolescents, BMI > (median + 2 s.d.) (crude estimate) (%)      |
| hepatitis       | Hepatitis B (HepB) immunization coverage among 1-year-olds (%)                                          |
| measles         | Measles-containing-vaccine first-dose (MCV1) immunization coverage among 1-year-olds (%)                |
| polio           | Polio (Pol3) immunization coverage among 1-year-olds (%)                                                |
| diphtheria      | Diphtheria tetanus toxoid and pertussis (DTP3) immunization coverage among 1-year-olds (%)              |
| basic_water     | Population using at least basic drinking-water services                                                 |
| doctors         | Medical doctors (per 10,000)                                                                            |
| gni_capita      | Gross national income per capita (PPP int. $)                                                           |
| gghe-d          | Domestic general government health expenditure (GGHE-D) as percentage of gross domestic product (GDP)(%)|
| che_gdp         | Current health expenditure (CHE) as percentage of gross domestic product (GDP) (%)                      |
| une_pop         | Population (thousands)                                                                                  |
| une_hiv         | Prevalence of HIV, total (% of population ages 15-49)                                                   | 

## Something New Learnt in This Project
- Filling in null values for time series datas using linear interpolation method instead of using median or mean of the data
- Machine learning model using Random Forest Regressor and Gradient Boosting Regressor 
- Finding the best parameter for the estimators used and reducing the possibility of overfitting by using Grid Search Cross Validation
- Using plotly for data visualisation
- Collaborating on GitHub

## Conclusion
Life expectancy inequality does indeed exist as there is great difference among the dispersion of life expectancy across different region. However, a good thing to note is that every region's life expectancy generally increase over the years. 

Based on the features importance we obtained from GBR model and also high, negative correlation between life expectancy and mortality rates, we believe there is a strong inverse relationship between le and mortality rates. However, correlation does not indicate a causal relationship and from our research, their high correlation could be attributed to their dependency on common variables like basic water and vaccination.

Hence, we can build our solutions around these 2 factors that could improve life expectancy and narrow the inequality. Two solutions would be improving water infrastructure so more people have access to safe water services and to also raise the public awareness on the importance of vaccination in children and infants across all regions.

With the machine learning model that we trained, countries will be able to better predict the life expectancy of their people should there be a change in any of the predictors(such as accessibility to water etc.) Thus, they can be more precise in their policies should they wish to improve life expectancy.

## Reflection
However, there are some limitations to our proposed solution. The top predictors we got from our machine learning models are based off the linear model used by WHO which is rigid and does not take into account unforeseeable circumstances. For instance, mortality rates which is one of the important predictors of WHO’s model would be abnormally higher due to death caused by natural disasters resulting in inaccuracy.

Furthermore, our machine learning model based on regional data also showed different top predictors with varying importance which highlights the fact that it is not sufficient to use a single model to predict life expectancy globally. Hence, WHO should have timely understanding of each country’s situation and also use different models for different countries, taking into account their geographic factors. 


## References
https://www.kaggle.com/code/mmattson/exploring-cleaning-and-modeling <br />
https://towardsdatascience.com/how-to-interpolate-time-series-data-in-apache-spark-and-python-pandas-part-1-pandas-cff54d76a2ea <br />
https://time.com/5166514/moderate-drinking-live-longer-study/ <br />
https://www.webmd.com/diet/news/20140328/underweight-even-deadlier-than-overweight-studsays#:~:text=People%20who%20are%20clinically%20underweight,more%20than%2050%20prior%20studies

