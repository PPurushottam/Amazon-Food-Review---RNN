# Amazon_fine_food_review
## Introduction
The Amazon Fine Food Reviews dataset consists of 568,454 food reviews. This dataset consists of a single CSV file, Reviews.csv

<b>Data Set</b><br />
<a href="https://www.kaggle.com/snap/amazon-fine-food-reviews">Click here</a> to get the dataset.<br />
<pre>Review.csv - 251MB</pre>

<b>Dataset statistics</b>
<pre>
    Number of reviews     568,454
    Number of users     256,059
    Number of products     74,258
    Users with > 50 reviews     260
    Median no. of words per review     56
    Timespan     Oct 1999 - Oct 2012
</pre>

<b>Data Fields Explanation</b>
<pre>
    Id - Unique row number
    ProductId - unique identifier for the product
    UserId - unqiue identifier for the user
    ProfileName
    HelpfulnessNumerator - number of users who found the review helpful
    HelpfulnessDenominator - number of users who indicated whether they found the review helpful
    Score - rating between 1 and 5
    Time - timestamp for the review
    Summary - brief summary of the review
    Text - text of the review
</pre>

## Model Building
<pre>
    STEP-1: Copy the data in Pandas DataFrame and drop unwanted columns.
    STEP-2: Text Preprocessing.
            a. Removing Unwanted Columns
            b. Checking for null values and Removing them
            c. Tokenizing the text using Tokenizer from tensorflow.keras
            d. Sequencing and padding train test X data
    STEP-3: Train Test Split
    STEP-4: Building and evaluating the model
            a. Building model for 5 classes of score from 0 to 4
            b. Evaluating the Model
            c. Building model for positive and negative comments
            d. Evaluating the Model 
</pre>

## Hyperparameter Constraint
<pre>
  - max_num_words = 10000 #unique words to be considered in set of documents
  - seq_len=50 # how many of the unique words are preset in each document
  - embedding_size = 100 # vector length of each word
  - Neurons in RNN - 32
  - activation='softmax'
  - learning_rate=0.001
  - optimizer=adam 
  - loss='categorical_crossentropy'
  - metrics=['accuracy']
</pre>

## Model Performance
<pre>
  - RNN for 5 Classes of score
    Accuracy Score - 0.7452568804918596
    Accuracy - 74.52 %
  - RNN for Positive and Negative Classes 
    Accuracy Score - 0.9016896676078142
    Accuracy - 90.16 %
</pre>
