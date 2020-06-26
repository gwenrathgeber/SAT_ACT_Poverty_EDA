# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

## Gwen Rathgeber, DSI-12-The Matt

## Instructor: Mahdi Shadkam-Farrokhi

## Problem Statement

We want to understand how poverty rates relate to state SAT and ACT scores by integrating [census data](https://www2.census.gov/programs-surveys/demo/tables/p60/266/state.xls) with scores.

As it's well established that [family income is a strong predictor of test scores](https://www.washingtonpost.com/news/wonk/wp/2014/03/05/these-four-charts-show-how-the-sat-favors-the-rich-educated-families/), it is reasonable to suspect that in states with high participation on a given test, average poverty level will be correlated with state average test scores.

We wish to determine if a relationship between state test scores and poverty levels exists through exploratory data analysis.

## Executive Summary

To investigate the question of poverty as it relates to standardized test scores, we gathered summary statistics on the data, investigated trends, then created visualizations which helped to understand the data and communicate findings.

Cleaning the sets followed these steps:
- Isolating input errors and replacing with correct values, then sourcing accurate replacements
- Adjusting data types where necessary due to formatting or input errors
- Dropping a handful of rows with extraneous or missing values
- Merging all 5 source tables into our final, combined table

We then proceeded with exploratory data analysis. This proceeded as follows:
- Explored minimum and maximum values in our columns
- Identified states with large changes in year-over-year participation rates
- Explored the highest and lowest states based on the sum of both participation rates for each year

Finally, we created visualizations. These were split into two parts:
- First, several types of plots helped us better understand our data
    - A heatmap of correlations allowed us to explore the relationships between different columns
    - Histograms of our columns allowed us to explore the internal distributions of each variable
    - Boxplots of all columns further visualized the spread of each variable
    - Scatterplots began relating specific variables to each other in tangible patterns
    - Finally, combinations of masks and scatterplots allowed us to isolate features which previous analysis had shown were confounding the relationship between poverty and test scores.
    - We then examine Ohio, the only state which had above-average test scores in the presence of high poverty and high participation rates for the test. By going deeper into the 
   
We conclude that there is a meaningful relationship between state poverty levels and average SAT and ACT scores, and make several recommendations to address this effect.

## Conclusions and Recommendations

After extensively exploring this data, our key takeaways are as follows:
- When investigating SAT and ACT scores at the state level, it is critical to compare 'apples to apples,' i.e. high-participation states to other high-participation states.
- State-level SAT and ACT scores both have demonstrable connection to state-level poverty. This connection is still evident if we take a deeper dive into a state's demographic score breakdown and poverty distributions.

SAT and ACT scores shouldn’t be considered objective without factoring in family wealth on an individual level, or poverty and race on an aggregate level.

We recommend cheaper access to test prep and equitable school funding to help equalize the US college admissions process, and that efforts should continue to eliminate unintentional biases in SAT and ACT questions and formats.

We further recommend statistical modeling to put numbers to the patterns and effects we have been able to observe through visualizations.

## Sources

- [Poverty Census Data](https://www.census.gov/data/tables/2019/demo/income-poverty/p60-266.html)
- [SAT Suite of Annual Assessments Report](https://reports.collegeboard.org/pdf/2019-total-group-sat-suite-assessments-annual-report.pdf)
- [Average ACT Scores by State Graduating Class 2018](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdf)
- [Colorado juniors face new, revamped college exam in SAT after state dumps rival ACT](https://www.denverpost.com/2017/03/06/colorado-juniors-sat-college-exam/)
- [Illinois Changed to the SAT in 2017: What You Need to Know](https://www.testive.com/illinois/)
- [Historically low ACT scores ‘a red flag for our country’](https://www.daytondailynews.com/news/historically-low-act-scores-red-flag-for-our-country/djfx9Urp719WyEaMfykyxL/)
- [Ohio Poverty Report 2019](https://www.development.ohio.gov/files/research/p7005.pdf)
- [ACT Profile Report - Ohio, 2017](https://www.act.org/content/dam/act/unsecured/documents/cccr2017/P_36_369999_S_S_N00_ACT-GCPR_Ohio.pdf)
- [These four charts show how the SAT favors rich, educated families](https://www.washingtonpost.com/news/wonk/wp/2014/03/05/these-four-charts-show-how-the-sat-favors-the-rich-educated-families/)

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|State|string|All|One of 50 States + Washington, D.C.| 
|sat_partic_17|float|SAT '17|% of students participating in the SAT in 2017|
|sat_read_write_17|float|SAT '17|SAT Reading and Writing Score, 2017|
|sat_math_17|float|SAT '17|SAT Math Score, 2017|
|sat_total_17|float|SAT '17|SAT Total Score, 2017|
|act_partic_17|float|ACT '17|% of students participating in the ACT in 2017|
|act_eng_17|float|ACT '17|ACT English Score, 2017|
|act_math_17|float|ACT '17|ACT Math Score, 2017|
|act_read_17|float|ACT '17|ACT Reading Score, 2017|
|act_sci_17|float|ACT '17|ACT Science Score, 2017|
|act_composite_17|float|ACT '17|ACT Composite Score, 2017|
|sat_partic_18|float|SAT '18|% of students participating in the SAT in 2018|
|sat_read_write_18|float|SAT '18|SAT Reading and Writing Score, 2018|
|sat_math_18|float|SAT '18|SAT Math Score, 2018|
|sat_total_18|float|SAT '18|SAT Total Score, 2018|
|act_partic_18|float|ACT '18|% of students participating in the ACT in 2018|
|act_composite_18|float|ACT '18|ACT Composite Score, 2018|
|poverty|float|Census Poverty|% of people living in poverty, 2017-2018 average|
|total_partic_17|float|Generated Feature|Sum of sat_partic_17 and act_partic_17|
|total_partic_18|float|Generated Feature|Sum of sat_partic_18 and act_partic_18|
|poverty_above_median|bool|Generated Feature|True if poverty index is below national median|