# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

### Problem Statement

The project aim is to analyse the SAT and ACT scores and participation rates from each state in the United States and identifying the key factors which can influence to increase the SAT participation rate in some the states.


## Executive Summary
To investigate the SAT participation rate and what Strategies College board should implement to improved the SAT participation rate across US year on year. We have taken 2017 and 2018 ACT and SAT datasets to do data analysis and to come up with the factors which can help to improve the SAT participation rate in some of the States. This project aims to analyse the data with some outside research to identify the drivers behind participation rates and scores in various states.


### Contents:
- [2Data Import and Cleaning](#SAT and ACT test data sets are given for 2017 & 2018)
- [Data Dictionary](#Type and description of datasets)
- [Exploratory Data Analysis](#To find the states with highest and lowerst test results)
- [Visualize the data](#Inferences from the graphs)
- [Descriptive and Inferetial Statistics](#Inferential Analysis)
- [Outside Research](#Some findings from outside research)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations

### Datasets
For this project, you'll have two provided datasets:

- [2017 SAT Scores](./data/sat_2017.csv)
- [2017 ACT Scores](./data/act_2017.csv)
- [2018 SAT Scores](./data/act_2018_update.csv )
- [2018 SAT Scores](./data/sat_2018.csv )

#### Data Dictionary
|Feature|Type|Dataset|Description|Value Range|
|---|---|---|---|---|
|column name|int/float/object|ACT/SAT|This is an example| Min&Max range|
|**state**|*object*| SAT / ACT | 51 states in USA |NA|
|**sat_part_17**|*float*| SAT | Percentage of students who all have taken SAT Test |0-100%|
|**sat_erw_17**|*int*| SAT | Score for "Evidence-Based Reading and Writing" |200-800 |
|**sat_math_17**|*int*| SAT |  Score for Math |200-800 |
|**sat_total_17**|*int*| SAT | Total score for SAT Test |0-1600|
|**act_part_17**|*float*| ACT | Percentage of high students who all have taken ACT Test|0-100% |
|**act_english_17**|*float*| ACT | Score for English|1-36 |
|**act_math_17**|*float*| ACT | Score for Math|1-36 |
|**act_reading_17**|*float*| ACT | Composite score for Reading|1-36 |
|**act_science_17**|*float*| ACT | Composite score for Science|1-36|
|**act_composite_17**|*float*| ACT | Composite score for ACT Test|1-36 |
|**sat_part_18**|*float*| SAT | Percentage of students who all have taken SAT Test|0-100% |
|**sat_erw_18**|*int*| SAT | Score for "Evidence-Based Reading and Writing" |200-800 |
|**sat_math_18**|*int*| SAT |  Score for Math |200-800 |
|**sat_total_18**|*int*| SAT | Total score for SAT Test |0-1600 |
|**act_part_18**|*float*| ACT | Percentage of high students who all have taken ACT Test| 0-100%|
|**act_english_18**|*float*| ACT | Score for English |1-36|
|**act_math_18**|*float*| ACT | Score for Math |1-36|
|**act_reading_18**|*float*| ACT | Composite score for Reading |1-36|
|**act_science_18**|*float*| ACT | Composite score for Science |1-36|
|**act_composite_18**|*float*| ACT | Composite score for ACT Test |1-36|


#### Findings from the data:

|**Highest Participation Rate**|

- 2017 SAT: District of Columbia, Michigan, Connecticut, Delaware, New Hampshire
- 2018 SAT: Colorado,Connecticut,Delaware,Michigan,Idaho
- 2017 ACT: Alabama, Kentucky, Wisconsin, Utah, Tennessee,South Carolina,Oklahoma,North Carolina,Nevada,          Montana,Mississippi,Minnesota,Louisiana,Missouri,Wyoming,Colorado,Arkansas	
- 2018 ACT: Alabama, Kentucky, Wisconsin, Utah, Tennessee,South Carolina,Oklahoma,North Carolina,Nevada,     Montana,Mississippi,Minnesota,Louisiana,Missouri,Wyoming,Colorado,Arkansas

|**Lowest Participation Rate**]

- 2017 SAT: Arkansas,Wyoming,North Dakota,Mississippi,Iowa
- 2018 SAT: Mississippi,Iowa,Wisconsin,Wyoming,North Dakota
- 2017 ACT: Pennsylvania,Rhode Island,Delaware,New Hampshire,Maine
- 2018 ACT: Pennsylvania,Delaware,New Hampshire,Rhode Island,Maine

|**Highest Total/Composite Rate**|

- 2017 SAT: Minnesota, Wisconsin, Iowa, Missouri, Kansas
- 2018 SAT: Minnesota, Wisconsin, North Dakota, Iowa, Kansas
- 2017 ACT: New Hampshire, Massachusetts, Connecticut, Maine, District of Columbia,
- 2018 ACT: Connecticut, Massachusetts, New Hampshire, New York, Michigan

|**Lowest Total/Composite Rate**|

- 2017 SAT: District of Columbia,Delaware,Michigan,Idaho,Maine
- 2018 SAT: District of Columbia, Delaware, West Virginia, Idaho, Hawaii
- 2017 ACT: Nevada, Mississippi, South Carolina, Hawaii, North Carolina
- 2018 ACT: Nevada, South Carolina, Mississippi, Hawaii, Alabama

|**Do any states with 100% participation on a given test have a rate change year-to-year?**|

 - District of Columbia participation rate changed to less than 100% in 2018 whereas Colorado and Idaho increased to 100% in 2018 
 
|**Do any states show have >50% participation on *both* tests either year?**|
   
    - Georgia
    - Hawaii
    - Florida


### Visualization findings:

|**Observation**|

The participation rate is more apperant on the choropleth map, which visualizes relationships between variables over a geographic span. For this part of the analysis, we can see the mid west states participation rate of ACT is higher that SAT participation rate.
A quick glance confirms that for the 2017 year, states with low ACT Participation % had high SAT Participation % and vice versa. This is primarily the result of business contracts, in which the states designate the test of choice for the area.

|**Observations**|

We observe a strong, negative correlation between ACT and SAT participation rates, -0.84 in 2017 and -0.87 in 2018. We can say from this that in states where the ACT participation rate is high, its SAT participation rate would be low.

There is also a negative correlation between scores and participation rates. For instance, the correlation between the 2018 SAT participation and total score was -0.79. States that require mandatory testing will see high participation rates but lower mean scores as a result of a wider range of scorers.

States where standardised testing is not mandatory, students that are more academically-inclined or self-motivated will register for these tests voluntarily. As they are more likely to be well prepared for the test, we will see a large proportion of high scorers.


### Conclusions:
|**Takeaways**|:

There is drastic increase in SAT participation rate in two states Colorado and Illinois.
Colorado and Illinois switched from ACT Testing to mandatory SAT Testing in Spring 2017.
This was due to statewide high school accountability and every student in those states is now required to participate in SAT Testing.
There is an inverse relationship between the ACT and SAT participation rates. States that administer a particular test will result in a low participation rate in the other.
There are strong regional (and possibly political) affiliations associated with ACT versus SAT preference. Coastal progressive states tend to favor the SAT, while Midwestern and Mountain conservative states tend to favor the ACT.

|**Recommendations**|:

Improve access for US States to SAT School Day Programs
Improve access to free preparation material for students
In order to increase SAT participation rates, the College Board can pitch to states that will soon see their ACT statewide contract due for renewal.
Cost-saving incentives for state boards, public schools, and public students..
Standardised testing is a mandatory requirement for high school graduates in Ohio. Unlike most states that administer only the ACT or the SAT, high schools in Ohio are given the flexibility to choose between administering the ACT or the SAT. This presents the College Board with the opportunity to persuade individual school districts in Ohio to switch from ACT to SAT.
The strategy is to slowly garner support from the local school districts to administer the SAT. Furthermore, as Ohio is also the 7th most populous state in the US, getting some schools to switch to the SAT would help to increase the SAT participation in absolute terms.
