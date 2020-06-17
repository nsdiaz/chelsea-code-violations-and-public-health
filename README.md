#  Leveraging data to expand city capacity to identify and resolve housing-related public health problems

This project uses machine learning to predict which properties in the city of Chelsea, MA, will be exposed to public health hazards. The model works by training on a subsection of the city that was subject to a proactive code inspections program and then making predictions for the rest of the city.

Initial evaluation of the models suggests that the city government may use these results to be more effective at finding public health risks than by inspecting properties at random or by reactively responding to citizen requests.

## Motivation

 City housing code enforcement has enormous transformative potential for public health. Achieving cities’ health and social missions, such as reducing overcrowding or asthma attacks, has remained difficult with traditional code enforcement approaches. 
 
 Cities increasingly have access to digital datasets that can be used to identify and characterize housing-related health risks and prioritize these properties for inspection. However, code enforcement has limited effectiveness in addressing health and housing problems. This is because cities are not aware of problems soon enough and inspections are often reactive or rely only on inspectors’ tacit knowledge.
 
 ## Scope

In 2014, Chelsea implemented a proactive program to inspect all rental properties in a target area of the city. In mid-2018, the city expanded the proactive program beyond the target area. . The sanitary code violations resulting from these inspections, as well as data on police and fire calls, the assessor’s database, the census, and other sources were aggregated and linked by property.

## Data

The data used for this project has been collected by different departments in Chelsea and uploaded to the [BuildingBlocks](https://www.tolemi.com/buildingblocks/)  platform, a map-based application which collects and joins property-based data. In 2019, the City of Chelsea had property-level records for 5,989 residential properties, 1,611 of which has been inspected between 2014 and 2019.

## Analysis

We built three models for each of our target variables:
*	Properties with any code violation
*	Properties with code violations that present an elevated public health risk (a composite of 4 code violations selected to consultation with city housing inspectors) 
*	Properties with code violations associated with overcrowding (illegal locks found inside building units)

For each of these, we ran different machine learning algorithms (XGBoost, Random Forest, LASSO) on a training dataset of properties inspected proactively between 2014 and 2018 in a target area of the city. We optimized the hyperparameters for each using crossvalidation and the ["area under the precision-recall curve"](https://scikit-learn.org/stable/auto_examples/model_selection/plot_precision_recall.html) metric. Then, we tested each algorithm using data from inspections outside of the target area that was held at the beginning.


## Python

This project is written in Python. To work in Python, we recommend downloading the 
[Anaconda environment](https://docs.anaconda.com/anaconda/install/).

Within Python, we use the `pandas` library for dataframe manipulation and analysis and the `sklearn` library for running supervised learning models. Additionally, we leverage the following libraries: `matplotlib.pyplot`, `seaborn`, `numpy`, `missingno`, `xgboost`, `warnings`.


## Notes

This work was conducted as part of the Harvard Kennedy School’s Ash Center for Democratic Governance and Innovation’s [Innovation Field Lab](https://ash.harvard.edu/innovation-field-lab). 
