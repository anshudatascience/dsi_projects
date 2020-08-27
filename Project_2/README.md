# Project 2 - Ames Housing Data and Kaggle Challenge


## 1. Executive Summary:
Using the Ames Housing Dataset that is available on Kaggle, we want to identify which features are the best predictors of housing price and create a regression model that will help us make predictions with the best root mean square value. The Kaggle challenge offers a train.csv for us to to train our model with, and a test.csv which we will clean and fit the model onto, in order to make our predictions. A csv of the predictions is ultimately uploaded to the Kaggle challenge for scoring. The model will be tuned closely to the Ames Housing dataset, and we might be able to use our findings from the process to understand what are some key predictors we can use in predicting prices for houses in the United States. However, given that this data set has some features that are very specific to Ames, Iowa (e.g. neighborhood), it will not be perfect fit for other housing data in the U.S. Steps to follow for this projects:

- Understanding the Data
- Exploratory Data analysis
- Clean the Null values
- EDA analysis and Feature creation
- Convert Categorical to numerical data
- Fit the Regularization models
- Test Data Cleaning and Submission to Kaggle
- Personal kaggle score of:

Private Score: 44555

SalePrice key predictors are:

The neighborhood the house is located in
Overall quality of the house
Total Square feet area



## Data Dictionary 


Data consist of 2051 rows of observations that is broken down into 80 separate information of a housing with sale price included.
The columns can be classified into numerical (int or float types) and categorical (object type). Categorical features can be further subdivided into descriptive (eg. Neighbourhood and MS Zoning) and ordinal (eg. ExterQual and ExterCond).

Feature	Variable type	Datatype	Description
id	Discrete	int	Observation number
pid	Nominal	int	Parcel identification number
ms_subclass	Nominal	int	Identifies the type of dwelling involved in the sale
ms_zoning	Nominal	object	Identifies the general zoning classification of the sale
lot_frontage	Continuous	float	Linear feet of street connected to property
lot_area	Continuous	int	Lot size in square feet
street	Nominal	object	Type of road access to property
alley	Nominal	object	Type of alley access to property
lot_shape	Ordinal	object	General shape of property
land_contour	Nominal	object	Flatness of the property
utilities	Ordinal	object	Type of utilities available
lot_config	Nominal	object	Lot configuration
land_slope	Ordinal	object	Slope of property
neighborhood	Nominal	object	Physical locations within Ames city limits
condition_1	Nominal	object	Proximity to various conditions
condition_2	Nominal	object	Proximity to various conditions (if more than one is present)
bldg_type	Nominal	object	Type of dwelling
house_style	Nominal	object	Style of dwelling
overall_qual	Ordinal	int	Rates the overall material and finish of the house
overall_cond	Ordinal	int	Rates the overall condition of the house
year_built	Discrete	int	Original construction date
year_remod/add	Discrete	int	Remodel date (same as construction date if no remodeling or additions)
roof_style	Nominal	object	Type of roof
roof_matl	Nominal	object	Roof material
exterior_1st	Nominal	object	Exterior covering on house
exterior_2nd	Nominal	object	Exterior covering on house (if more than one material)
mas_vnr_type	Nominal	object	Masonry veneer type
mas_vnr_area	Continuous	float	Masonry veneer area in square feet
exter_qual	Ordinal	object	Evaluates the quality of the material on the exterior
exter_cond	Ordinal	object	Evaluates the present condition of the material on the exterior
foundation	Nominal	object	Type of foundation
bsmt_qual	Ordinal	object	Evaluates the height of the basement
bsmt_cond	Ordinal	object	Evaluates the general condition of the basement
bsmt_exposure	Ordinal	object	Refers to walkout or garden level walls
bsmtfin_type_1	Ordinal	object	Rating of basement finished area
bsmtfin_sf_1	Continuous	float	Type 1 finished square feet
bsmtfin_type_2	Ordinal	object	Rating of basement finished area (if multiple types)
bsmtfin_sf_2	Continuous	float	Type 1 finished square feet
bsmt_unf_sf	Continuous	float	Unfinished square feet of basement area
total_bsmt_sf	Continuous	float	Total square feet of basement area
heating	Nominal	object	Type of heating
heating_qc	Ordinal	object	Heating quality and condition
central_air	Nominal	object	Central air conditioning
electrical	Ordinal	object	Electrical system
1st_flr_sf	Continuous	int	First Floor square feet
2nd_flr_sf	Continuous	int	Second floor square feet
low_qual_fin_sf	Continuous	int	Low quality finished square feet (all floors)
gr_liv_area	Continuous	int	Above grade (ground) living area square feet
bsmt_full_bath	Discrete	float	Basement full bathrooms
bsmt_half_bath	Discrete	float	Basement half bathrooms
full_bath	Discrete	int	Full bathrooms above grade
half_bath	Discrete	int	Half baths above grade
bedroom_abvgr	Discrete	int	Bedrooms above grade (does NOT include basement bedrooms)
kitchen_abvgr	Discrete	int	Kitchens above grade
kitchen_qual	Ordinal	object	Kitchen quality
totrms_abvgrd	Discrete	int	Total rooms above grade (does not include bathrooms)
functional	Ordinal	object	Home functionality (Assume typical unless deductions are warranted)
fireplaces	Discrete	int	Number of fireplaces
fireplace_qu	Ordinal	object	Fireplace quality
garage_type	Nominal	object	Garage location
garage_yr_blt	Discrete	float	Year garage was built
garage_finish	Ordinal	object	Interior finish of the garage
garage_cars	Discrete	float	Size of garage in car capacity
garage_area	Continuous	float	Size of garage in square feet
garage_qual	Ordinal	object	Garage quality
garage_cond	Ordinal	object	Garage condition
paved_drive	Ordinal	object	Paved driveway
wood_deck_sf	Continuous	int	Wood deck area in square feet
open_porch_sf	Continuous	int	Open porch area in square feet
enclosed_porch	Continuous	int	Enclosed porch area in square feet
3ssn_porch	Continuous	int	Three season porch area in square feet
screen_porch	Continuous	int	Screen porch area in square feet
pool_area	Continuous	int	Pool area in square feet
pool_qc	Ordinal	object	Pool quality
fence	Ordinal	object	Fence quality
misc_feature	Nominal	object	Miscellaneous feature not covered in other categories
misc_val	Continuous	int	$Value of miscellaneous feature
mo_sold	Discrete	int	Month Sold (MM)
yr_sold	Discrete	int	Year Sold (YYYY)
sale_type	Nominal	object	Type of sale
saleprice	Continuous	int	Sale price $$



## Conclusions and Recommendations

In order to have a model that predict the price of house accurate first we will need to clean up our data with the help of Exploratory Data Analysis, where we will be looking at data for completeness through imputation of the null values, convertion of discrete, continous, ordinal and nominal values in variables, identifying which are the outlier.

#### Feature Exploration

seaborn Heatmap, we will be able to identify which features are of the highest correlation with saleprice.
pairplot allow us to take a close look at the correlation and the distribution
boxplot help to identify which are the outlier.
Which features appear to add the most value to a home? Feature Correlation with Sale price with a significant positive correlation of more than 0.5 1.total square feet (0.84) 2.Overall quality (0.81) 3.External quality (0.72) 4.Ground Living Area (0.72) 5.kitchen quality(0.69) 6.Total basement square feet (0.67) 7.garage area (0.65)

Which features hurt the value of a home the most?
Feature Correlation with Sale price with a significant negative correlation of less than than -0.6 1.Housing age (-0.58)

What modeling approaches yield the most accurate prediction

Dummy variables: Replace catergorical variables
Ordinal Values: Assigning values to those scaled variables with the use of mapping.
Train test split
Comparison between linear regression, lasso and ridge
Which model has the best prediction? 

Lasso has the highest accurate prediction whcih are R^2 score of 85% on the test Prediction.

What are things that homeowners could improve in their homes to increase the value?

as age of the house can hurt the value of a home hence, remodelling might come in handy if homeowners are planning to increase the value.
Other Recommendation Rather than only looking at the features of a property, there are other factors that might affect the sale price. This to consider to further investigate that may help to predict the price of property even more accurately.
For instance, a recession or a pandemic might cause a drop in the sale price due to supply and demand.