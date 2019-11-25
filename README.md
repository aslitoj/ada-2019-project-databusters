# How to Survive Eating Out in Chicago

**All progress up to milestone 2 is in the DataCleaningAndExploratoryAnalysis.ipynb notebook.**

## Abstract
Chicago is home to 16,000 food establishments like restaurants, grocery stores, bakeries, hospitals, day care facilities, shelters, schools and more, all of which are subject to recurring inspections by The Food Protection Division of the Chicago Department of Public Health.

We will try to link high/low risk areas of contracting food-borne illnesses and the socioeconomic indicators of the different community areas of the city of Chicago with the inspection results to see if there are any patterns. Furthermore, we will investigate what the Chicago Food Desert is, seeing if our dataset could support its existence.

Our ultimate aim for this project is to promote public health in areas of food safety and sanitation and prevent food-borne illness by providing a reliable recommendation system for eating out in Chicago, based on a "safety score" that we will compute using the information from inspections of food establishments in Chicago. All of this is compatible with our end goal of showcasing an example of the use of "data science for social good”.

## Research questions

### I. Do facility attributes influence food inspection outcomes for establishments in Chicago?

Our main dataset as well as our secondary datasets give us many attributes for each establishment such as facility type, risk, location and whether it is a chain or not [1](https://www.chicagotribune.com/business/ct-biz-mcdonalds-cyclospora-outbreak-20180719-story.html). Which of these attributes contributes the most to food inspection outcomes in Chicago?

### II. Chicago Food Deserts: an indicator of social segreggation?

Many articles seem to point to the fact that different areas in Chicago do not have equal access to healthy food [2](https://chicago.eater.com/2018/12/13/18138387/chicago-magazine-john-kessler-food-scene-racism-immigration-food) [3](https://www.chicagoreporter.com/food-deserts-persist-in-chicago-despite-more-supermarkets/). These articles claim that this is due to the persistence of racial segreggation. Our aim is to inspect this further and see whether our dataset could help in seeing if this is true.

### III. The survival guide: a personalized guide for eating out safely

This represent the conclusion to our findings. The aim is to display an interactive map with widgets where the user can choose parameters as: "Allergies friendly restaurants", "No food chains" and get restaurants displayed along with their safety scores.

## Datasets

#### Chicago Food Inspections Dataset
We chose the _Chicago Food Inspections_ dataset from the given datasets. It contains information about food inspections of different establishments in Chicago from January 1, 2010 to the present. We will use it as our main dataset for the project and it can be downloaded either as a JSON file _socrata\_metadata.json (9.14 KB)_  or a CSV file _food-inspections.csv (219.71 MB)_ from [4](https://www.kaggle.com/chicago/chicago-food-inspections) (In addition to that source, you can check for the main source dataset on Chicago Data Portal [5](https://data.cityofchicago.org/Health-Human-Services/Food-Inspections-Dashboard/2bnm-jnvb)). More information about the attributes in the Chicago Food Inspections' dataset can be found on [6](https://data.cityofchicago.org/api/assets/BAD5301B-681A-4202-9D25-51B2CAE672FF).

#### Socioeconomic & Health related datasets
In order to answer our second research question, we need a socioeconomic as well as health related indicator datasets.To that end, we will be using selected public health indicators for the different community areas. The dataset is available under this [link](https://data.cityofchicago.org/Health-Human-Services/Public-Health-Statistics-Selected-public-health-in/iqnk-2tcu) and contains measures related to infectious disease, lead poisoning, and economic status.

We will also need the total population by community area which we will merge with the latter. [source](https://www.chicagohealthatlas.org/indicators/total-population)

#### Community Areas boundaries
We need the community areas boundaries dataset for visualization purposes as well as to fill in missing values in our main dataset. The dataset is provided by the City of Chicago under this [link](https://www.chicago.gov/city/en/depts/doit/dataset/boundaries_-_communityareas.html) and is provided under different extensions. We will be using the .geojson file.

#### Fast Food Restaurants Across America
In order to work on chains specifically, we use [this dataset](https://www.kaggle.com/datafiniti/fast-food-restaurants) to get a list of chains that we join with our inspections dataset.

## APIs

#### Yelp Fusion
Yelp is a business directory service and crowd-sourced review forum. 
Alongside our main dataset, we will be using the Yelp Fusion API, [8](https://www.yelp.com/developers/documentation/v3). This is a collection of endpoints developers can reach to get information on establishment. It has been made available to use for personal, educational, and academic purposes. To support our research questions, we will be using:

- **Business Match Endpoint**: Lets us match business data from other sources against businesses on Yelp, based on provided business information. 
- **Business Details**: Given the id of any establishment obtained from the Business Match Endpoint, this returns details like price range, rating, and cuisine. 

## A list of internal milestones up until project milestone 2

#### Clean primary dataset (November 10th)

* Explore features
* Drop features which are irrelevant to our research questions
* Clean each column in the dataset
    * Try to reduce the number of unique values for each column through clustering
    * Find ways to fill missing values

#### Come up with a data story (November 20th)

* Plot different features and examine their distribution and correlations
* Cluster thematically close questions together and modify README to reflect evolution of ideas
* Finalize list of secondary datasets to use to answer research questions
* Divide secondary dataset management among group members
* Conduct cleaning process on secondary datasets

## A list of internal milestones up until project milestone 3

#### Answer research questions on primary dataset (December 3rd)

* Divide questions among group members
* Answer the research questions using all resulting datasets and analysis from milestone 2
* Come up with insightful responses to questions
* Peer review after all the group members have finished writing their responses

#### Putting it all together (December 13th)

* Finalize structure of data story after gathering all responses found
* Divide tasks for data story construction among group members
* Put together data story
* Final peer review regarding the different parts each group member was responsible for
* Test data story to detect bugs and errors
* Fix errors and bugs
* Test and finalize data story
    
## Resources
[1] https://www.chicagotribune.com/business/ct-biz-mcdonalds-cyclospora-outbreak-20180719-story.html <br/>
[2] https://chicago.eater.com/2018/12/13/18138387/chicago-magazine-john-kessler-food-scene-racism-immigration-food <br/>
[3] https://www.chicagoreporter.com/food-deserts-persist-in-chicago-despite-more-supermarkets/ <br/>
[4] https://www.kaggle.com/chicago/chicago-food-inspections <br/>
[5] https://data.cityofchicago.org/Health-Human-Services/Food-Inspections-Dashboard/2bnm-jnvb <br/>
[6] https://data.cityofchicago.org/api/assets/BAD5301B-681A-4202-9D25-51B2CAE672FF <br/>
[7] https://data.cityofchicago.org/Health-Human-Services/Census-Data-Selected-socioeconomic-indicators-in-C/kn9c-c2s2 <br/>
[8] https://www.yelp.com/developers/documentation/v3 <br/>
[9] https://www.kaggle.com/datafiniti/fast-food-restaurants <br/>
