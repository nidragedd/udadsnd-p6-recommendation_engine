# Udacity DataScience nanodegree project - Recommender system
## Table of contents
* [1. Context - Objectives](#1-context---objectives)
* [2. Technical section](#2-technical-part)

---

## 1. CONTEXT - OBJECTIVES
### Context
This project is only for educational purposes. I did it while I was following the Udacity `DataScience nanodegree`.  
In this project we analyze the interactions that users have with articles on the IBM Watson Studio platform, and make 
recommendations to them about new articles we think they will like.  
Here is an example of what the dashboard could look like displaying articles on the IBM Watson Platform:
![IBM Watson platform picture](assets/ibm_platform.png)

Though the above dashboard is just showing the newest articles, we could imagine having a recommendation board available
here that shows the articles that are most pertinent to a specific user.


### Objectives
This project is divided into several phases and this [notebook](notebooks/Recommendations_with_IBM.ipynb) is a walkthrough guide to follow:  
1. **Exploratory Data Analysis** that processes message and category data from csv files and load them into a SQLite database  
2. **Rank Based Recommendations**: find the most popular articles simply based on the most interactions. Since there are no ratings for any 
of the articles, it is easy to assume the articles with the most interactions are the most popular. These are then the articles we might recommend
to new users (or anyone depending on what we know about them).  
3. **User-User Based Collaborative Filtering**: look at users that are similar in terms of the items they have interacted with.
These items could then be recommended to the similar users. This would be a step in the right direction towards more personal
recommendations for the users.
4. **Content Based Recommendations**: use NLP to develop a content based recommendation system.
5. **Matrix Factorization (SVD)**: machine learning approach to building recommendations. Using the user-item interactions, we build out a matrix decomposition.
And using this decomposition, we can get an idea of how well we can predict new articles an individual might interact with

---
## 2. TECHNICAL PART
### Dependencies & Installation - Create your CONDA virtual environment
Easiest way is to create a virtual environment through **[conda](https://docs.conda.io/en/latest/)**
and the given `environment.yml` file by running this command in a terminal (if you have conda, obviously):
```
conda env create -f environment.yml
```

If you do not have/want to use conda for any reason, you can still setup your environment by running some `pip install`
commands. Please refer to the `environment.yml` file to see what are the dependencies you will need to install.  
Basically, this project requires **Python 3.7** in addition to common datascience packages (such as 
[numpy](https://www.numpy.org/), [pandas](https://pandas.pydata.org/), [matplotlib](https://matplotlib.org/)).

For machine learning, this project is using **Singular Value Decomposition** from [numpy](https://www.numpy.org/) package.

There are those additional packages in order to expose our work within a webapp:
* [spacy](https://spacy.io/): used for NLP tasks

### Directory & code structure
Here is the structure of the project:
```
    project
      |__ assets     (contains images displayed in notebooks or README)
      |__ data       (raw data)
      |__ notebooks  (contains all notebooks)
      |__ srctests   (python modules and scripts)
```
