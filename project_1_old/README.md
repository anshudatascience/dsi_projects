# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

### Problem Statement

This project aims to investigate the SAT participation rate and find out the recommendation for the College board to boost the SAT participation rate in one state in the US. 


## Executive Summary
Study the SAT participation rate and provide recommendation to improve the participation rate year on year. We have taken 2 years data(2017 & 2018 ACT and SAT data) to show the relationship and factors affecting SAT participation rate.

### Contents:
- [Data sets](#SAT and ACT test data sets are given for 2017 & 2018)
- [Data Dictionary](#Type and description of datasets)
- [Findings from Data](#To find the states with highest and lowerst test results)
- .[Findings from Visualization](#Inferences from the graphs)
- [Conclusions and Recommendations](#Conclusions-and-Recommendations)

### Datasets
For this project, you'll have two provided datasets:

- [2017 SAT Scores](./data/sat_2017.csv)
- [2017 ACT Scores](./data/act_2017.csv)
- [2018 SAT Scores](./data/act_2018_update.csv )
- [2018 SAT Scores](./data/sat_2018.csv )

#### Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|column name|int/float/object|ACT/SAT|This is an example|
|**state**|*object*| SAT / ACT | 51 states in USA |
|**sat_part_17**|*float*| SAT | Percentage of students who all have taken SAT Test |
|**sat_erw_17**|*int*| SAT | Score for "Evidence-Based Reading and Writing"  |
|**sat_math_17**|*int*| SAT |  Score for Math |
|**sat_total_17**|*int*| SAT | Total score for SAT Test |
|**act_part_17**|*float*| ACT | Percentage of high students who all have taken ACT Test |
|**act_english_17**|*float*| ACT | Score for English |
|**act_math_17**|*float*| ACT | Score for Math |
|**act_reading_17**|*float*| ACT | Composite score for Reading |
|**act_science_17**|*float*| ACT | Composite score for Science |
|**act_composite_17**|*float*| ACT | Composite score for ACT Test |



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
- Heatmap shows participation rate in ACT and SAT data are highly negative correlated which means SAT is not taken in those states where ACT has been popular.
- Histpgram of SAT participation and ACT participations shows that the SAT participation rate is very low in those states where the ACT has been taken. 

### Conclusions:
|**Takeaways**|:
- There is drastic increase in SAT participation rate in two states Colorado and Illinois.
- Colorado and Illinois switched from ACT Testing to mandatory SAT Testing in Spring 2017.
- This was due to statewide high school accountability 
   and every student in those states is now required to participate in SAT Testing.

|**Recommendations**|:
 - Improve access for US States to SAT School Day Programs
 - Improve access to free preparation material for students
 - Cost-saving incentives for state boards, public schools, and public students..
