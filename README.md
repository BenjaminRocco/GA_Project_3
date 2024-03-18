# USA Political Party Subreddit Classification: Extensive Applications with Natural Language Processing Models

# Goals

1. With [PRAW](https://praw.readthedocs.io/en/stable/), collect posts from two subreddits, `democrats` and `Republican.`
2. Utilize NLP modeling to train a classifier to predict from which subreddit a given post originated. In this binary classification problem the objective will be to create the most accurate and optimized model possible and quantify success by relying upon classification metrics such as sensitivity, specificity, precision, accuracy, and the misclassification rate. 
3. Stakeholders in this research will be individuals and organizations interested in learning how NLP models may differentiate between supporters of two different political parties based on language used in their posts and how accurately these predictions may be made. 
4. Therefore, this study will enable these stakeholders to understand the process and considerations that must be made in order to create a fully functional NLP model and distinguish between these groups in a highly technical and sophisticated manner so that they may design their own models for future research.

# Primary Objective

The goal of the model is to prioritize sensitivity. In other words, the positive class is whether a given post belonged to the `democrats` subreddit class, denoted by a $1$, therefore, the goal is the achieve a result that yields a high probability of correctly predicting an "actual" positive example. 

Precision, the probability that the model is correct when it predicts an example to be in the positive class, will also be prioritized. 

Accuracy, the percentage of observations correctly predicted within the test class, is another goal.

Finally, the two models chosen, to be detailed in a few sections, will be compared to the standards of the aforementioned classification metrics.


#### $\textit{Nota bene Regarding PRAW}$

PRAW is a Python wrapper for the Reddit API.  The Reddit API has more functionality than PushShift; and therefore, is a little less straightforward. 

One drawback of PRAW is that it only allows collection of up to around 1000 posts from any given subreddit stream. 

In this project, we use a placeholder file as `praw.ini` had path conflicts locally which could not be resolved even with more technical assistance. Please see the notebook for details, as one can define a separate `.py` file with their Reddit API credentials and import it within the security of their local notebook. When this issue is resolved the repo will be updated accordingly.  

# Model Workflow

Data Choices
- In this project, posts and comments were webscraped from two distinct subreddits, `democrats` and `Republican`. 

Data collection
- The API only allowed a retrieval of $1000$ of the most recent new and popular posts at time, so running the script at regular intervals in time was necessary in order to collect enough data.

# Steps

- Gather and prepare data using the `requests` library and PRAW.
- **Create and compare models**. These are included within the `ProjectModeling.ipynb` file. 
- Present these findings to peers. 
- Document everything carefully and legibly for future reference and third-party viewership. 

## General Folder Contents

- Readme/executive summary in markdown.
- PowerPoint presentation as a `PDF` file.
V- code folder
- data folder
- images folder
- image function documentation folder

## Code Folder Contents

### `Data_Collection.ipynb`: Contains the webscraping portion of the project and exportation of the datafiles. 
#### Sections: 
    1. Imports
    2. Instantiate PRAW
    3. Subreddit Titles
    4. Scraping Subreddit Titles
    5. Saving, Viewing, Exporting DataFrames
### `Data_Imports_and_EDA.ipynb`: Imports of datafiles and subsequent concatenation into one DataFrame. Exploratory data analysis (EDA), dummifying of target column, and modifications to DataFrame are detailed. Resulting file is exported for future usage.
#### Sections: 
    1. Imports
    2. Loading Data
    3. Drop Duplicates
    4. Drop Superfluous Columns
    5. Visual Inspection
    6. Further Cleaning and Concatenating of DataFrames
    7. Exportation of Final DataFrame
### `ProjectModeling.ipynb`: Necessary cleaning using regular expressions and functions and $\textit{NLP}$ modeling and analysis.  
#### Sections: 
    1. Imports
    2. Data Inspection
    3. Preliminary Cleaning
    4. Stopwords Glance
    5. Modeling Section (CountVectorizer with Logistic Regression and TFIDF Vectorizer with Support Vector Machine)
    6. BONUS: Aforementioned Models with SMOTE
### `FunctionDocumentation`: Markdown cells explaining the way each processing method works from a theory-standpoint, adapted directly from course notes, and links to function documentation sourced from online documentation. 
### Source material attributed to General Assembly course notes and functions to online documentation centers, respectively. 
#### Sections: 
    1. CountVectorizer Theory
    2. TFIDF Vectorizer Theory
    3. Logistic Regression Documentation
    4. Support Vector Machine (SVM) Documentation
    5. SMOTE Documentation
## Data Folder Contents

Datafiles from webscraping. Format follows this convention: $\text{df\_\,d\#}$ or $\text{df\_\,r\#}$ based on whether data was gathered from `democrats` or `Republican` subreddit, respectively. Data was then merged into one DataFrame and exported to final file $\text{df\_\,final\#}.$

## Image Folder Contents

Images formatted for the PowerPoint presentation. 
#### Files: 
    1. Confusion Matrix for Logistic Regression with SMOTE
    2. Confusion Matrix for Logistic Regression Model
    3. Confusion Matrix for Support Vector Machine Model
    4. "GOPDEM" - Image for PowerPoint Presentation
    5. "NLP_Sample" - Image for PowerPoint Presentation (Attributed to Course Lesson)
    6. "reddit-alien" - Image for PowerPoint Presentation 
    7. Barchart of important words in final posts list
    8. "Troll" - Image for PowerPoint Presentation

## Images Function Documentation Folder Contents
Images for the purpose of the `FunctionDocumentation.ipynb` file adapted from course lessons.
#### Files: 
    1. Count Vectorizer Schematic
    2. Count Vectorizer Transformation Flow Chart
    3. TF-IDF Vectorizer Process Schematic

# Conclusion: Since the goal of the modeling process was to prioritize sensitivity, SVM achieved this result (see `ProjectModeling.ipynb` for more details). 

In summary: the positive class was whether the post belonged to the `democrats` subreddit class, denoted by a $1$, therefore, the goal was to achieve a result that yielded a high probability of correctly predicting an "actual" positive example. 

Precision in SVM was high, defined as 'the probability that the model was correct when it predicts an example to be in the positive class.' 

Accuracy, defined as 'the percentage of observations correctly predicted within the test class,' was highly fine-tuned. 

It will be revealed that $\textit{SVM}$ outperformed $\textit{logistic\,regression}$ in the aforementioned classification metrics; thus $\textit{SVM}$ was the optimal model at differentiating between the two subreddit classes. 

Thus, stakeholders interested in creating a fully functional NLP model and distinguishing between political parties in a highly technical and sophisticated manner may utilize SVM to achieve success in their research. Other models like logistic regression and different Naive Bayes statistical models (Bernoulli, Multinomial, and Guassian) are also adequate, but Support Vector Machines (SVM) will perform optimally compared with these models. The author recommends SVM for this binary classification problem and the research done in this study will substantiate this position. 


