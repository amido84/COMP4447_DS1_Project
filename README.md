# COMP 4447 Final Project
This repository houses the notebook, files, and code pertaining to the final project, encompassing various stages such as data scraping, data cleaning, visualizations, and data analysis, all conducted using R.

# Versions
Python Version:
- Python 3.9.12

R Version:
- 4.2.2

Packages used (with version):

- See requirements.txt for Python
- See R-library_requirements.txt for R

# Should We Trust that Hiking Trail Rating?
# Contributors:
- Ahmed Al Ayoubi
- Chris Kirchberg
- Harlan Kefalas

# Motivation and Dataset:
When looking for hikes, sometimes the rating and difficulty specified at websites do not always seem to meet expectations of those who hike the trail of interest.

Taking a look a various websites, we settled on using https://www.hikingproject.com to scrape information from hikes in the state of Colorado. Currently the site lists 5,855 trails in that state which are curated by staff or contributors. Other sites like www.alltrails.com look like they would be good sites but have web scraping prevention tools in place which makes it difficult to extract information.

# Task Definition/Research Question:
As a prospective hiker of a trail, questions come to mind before choosing that trail to hike:
- Does the ratings/difficulty stated by the reviewers match that of the currated trail?
- Is there other information about the trail that might give us a better idea as what the trail should be rated?
- Is there information that might corroborate the trails difficulty/rating either by the currator or the reviewers?

Answers to these questions could possibly be gleaned by scraping data from website like https://www.hikingproject.com, cleaned and then explored by visualizations and simple summary statistics. This project seeks out to explore some possible answers and directions to these questions.

# Literature Review:
Upon searching the web for similar types of tasks, APIs, or others who have attempted something similar, we ran accross this GitHub page: https://github.com/oschow/take-a-hike

It used packages like Selenium, MongoDB, Pandas, sklearn and other resources to scrape infromation from www.alltrails.com, model, visualize and create a Hike Recommendation web app to find hikes that are similar to the hikers interests or whims.

This seemed like a good start to try our hand at exploring ratings...until we ran into blocks in web scrapping AllTrails.com...and so our journey began.

# Data Scraping
Web scraping https://www.hikingproject.com from hiking trails in the state of Colorado. as stated above, 5,855 trails are listed and curated by staff or contributors. Using Selenium automation test tool, we scraped 4,903 hiking trails in Colorado filtered by the following Data attributes:

- Trail Name
- Trail Length
- Trail Difficulty
- Trail Rating
- User Rate Number
- Trail Type
- Elev_Up
- Elev_Down
- Highest Elevation
- Lowest Elevation
- Average Grade
- Max Grade
- Dogs and Features
- Stats Info.


![onesheet copy](https://user-images.githubusercontent.com/71293836/219767598-f12965f7-505a-4722-a2f7-f4b420032888.jpg)


# Data Cleaning:
Data cleaning is identifying and correcting errors or inconsistencies in hike_project.pkl dataset to ensure that the data is accurate, complete, and consistent.

Data cleaning typically involves several tasks, including:

- Removing duplicates
- Handling missing data
- Standardizing data
- Removing outliers
- Correcting data type
- Merging data
- Normalizing data
- Reformatting data

# Visualizations:
After extraction and cleaning, it is time for exploratory data analysis. Some basic output and visuals and explored below.

![output](https://user-images.githubusercontent.com/95116282/223188500-50f8b0d4-b9d5-4863-a9dd-5634d7f59c07.png)

![output](https://user-images.githubusercontent.com/95116282/223188616-0d2a74e9-5311-47e5-81ac-445c37932338.png)

![output](https://user-images.githubusercontent.com/95116282/223188750-65498eae-11c8-44d5-911e-7797c5cb433e.png)

There are more visualization to be shown as well as some summary statistics and can be found in the Jupyter Notebook at this site.  The take home message is that it is not clear what the main contributing relationshipts between Overall Rating and Trail Characteristics are, but a multivariate approach will be more appropriate and explored in the next section.

# Data Analysis in R

Best subset linear regression completed. Plots of the summary for the model with no features offered the best predictability. 
<img width="815" alt="Screenshot 2023-03-05 at 7 52 56 PM" src="https://user-images.githubusercontent.com/123426828/223002278-7040262d-b78b-4217-aeb9-fb0d2f14c987.png">

The coeffecients for the model.
<img width="787" alt="Screenshot 2023-03-05 at 7 53 42 PM" src="https://user-images.githubusercontent.com/123426828/223002302-e6eb4b36-ef18-4fb6-8bba-c18f32609199.png">

For comparison, the best subset with all factors. 
<img width="807" alt="Screenshot 2023-03-05 at 7 53 59 PM" src="https://user-images.githubusercontent.com/123426828/223002350-ce89b35f-a84e-45fa-82f1-b6014560a787.png">

Basic linear regression shows not all factors are statiscally significant.

<img width="620" alt="Screenshot 2023-03-05 at 7 56 38 PM" src="https://user-images.githubusercontent.com/123426828/223002470-82502bb4-be5d-4ba1-acb3-bb76192b89ba.png">


