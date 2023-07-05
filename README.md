# CodeClause_FakeNewsAnalysis
Python Code for Fake News Analysis

The data set used for the project is available on: kaggle datasets download -d clmentbisaillon/fake-and-real-news-dataset

1. Importing Libraries
   First, we import a few libraries into the Jupyter Notebook for using it in our program code. The libraries imported are as follows:
     - Pandas: This library is mainly used for data manipulation and analysis on structured datasets such as CSV files.
     - sklearn.feature_extraction.text.TfidfVectorizer: Converts the raw text to a matrix format for preprocessing.
     - sklearn.model_selection.train_test_split: This is helpful for splitting the dataset into training and testing subsets.
     - sklearn.linear_model.PassiveAgressiveClassifier: Used for the classification of tasks.
     - sklearn.metrics: Evaluating machine learning models, accuracy, confusion matrix.
     - string: Used for manipulation of strings.
       
2. Loading Datasets
   Fake.csv and True.csv are loaded into thedata frames named fake_data and true_data respectively with the help of 'read.csv'.
   
3. Preprocessing Data
   This is mainly achieved in 4 steps.
   - We first create labels to differentiate fake and true news.
   - Then we combine the datasets into 'news_data'.
   - Then we shuffle the data.
       > sample(): selects random rows
       > frac=1: selects all rows
       > reset_index: resets old index and assigns a new index
   - We then split the shuffled data into training and testing subsets.
       > 0.2 size means 20% will be assigned for training and 80% for testing.
       > The random state ensures that the same split is achieved each time the code is run.
       
4. Creating Vectorizer
   This converts the text into a matrix format for numerical features. The common English words and words with many occurrences are removed.
   
5. Fit and Transform Training Data
   This recognises unique words from the training subset and transforms them by representing the unique words in a matrix format.
   
6. Initialize a Passive Aggressive Classifier
    This is used for the linear classification algorithm and then passed to the training set.
   
7. Train Classifier
     Takes the unique words from the training data and matches them with their corresponding labels in order to make predictions on unseen data.
    
8. Transform Test Data
   Takes test data as input and transforms the data to ensure that the testing data is represented in a consistent manner and compatible with the trained classifier
   
9. Predict Labels
    Makes predictions on the testing data with the help of the trained classifier which takes the train data as input.
   
10. Evaluate Performance
    - The accuracy score compares the predicted labels along with the true labels.
    - It gives the percentage of correctly classified instances.
    - The confusion matrix creates a matrix based on predicted and true labels representing the true positives, true negatives, false positives and false negatives.
    - This also provides a detailed breakdown of performance by revealing types of errors made.
      
11. Print Result
    The accuracy score and confusion matrix is then printed.
    
12. Create Function
    We create a function named test_news which takes a news string as user input and then prints whether the given news is fake or not.
  
13. Manual Testing
    - We first take a variable which takes a news string as user input.
    - The variable is then passed through the function name to analyse and print whether the user input news is fake or real.
