STEP 1 :- Let’s start with the basic data exploration: Dataset consists of 20,000 ROWS with 15 attributes which are :-
            uniq_id 
            crawl_timestamp
            product_url
            product_name
            product_category_tree
            pid
            retail_price
            discounted_price
            image
            is_FK_Advantage_product
            description
            product_rating
            overall_rating
            brand
            product_specifications
From the product_cateogry_tree I selected a primary cateogry which is at the starting of tree  which will act as dependent variable .
Apart from this I deleted All the other coloumns apart from description .
Description will act as a independent variable .
I deleted all the rows with the missing values in 'Description' and 'product cateogry' coloumn 

STEP 2:-Text cleaning and Preprocessing
There can be multiple ways of cleaning and preprocessing the textual data and here I have applied the ones which are frequently used in NLP pipelines.
Lower case: Since we would expect to treat “Food” and “food” as the same word, without creating various predicting powers, I’ve down-cased each word.
Contractions: I’ve replaced contractions with their longer forms such as “isn’t”: “is not”, “can’t”: “cannot“. To do so, I’ve imported contractions list from here.
Remove special characters: I’ve cleaned the data from any special character such as double quotes, punctuation, and possessive pronouns.

STEP 3:-TRAIN-TEST SPLIT 
With the random State of 225 I applied train-test-split to saperate train and test data


STEP 4:- APPLYING A MODEL
MODEL 1:-
Tf-Idf
Tf-Idf stands for term frequency-inverse document frequency, and instead of calculating the counts of each word in each document of the dataset (Bow),
it calculates the normalized count where each word count is divided by the number of documents this word appears.
Logistic Regression
After I created a train-test split of the dataset,
I’ve applied logistic regression which is a classification algorithm used to solve classification problems.
The logistic regression classifier uses the weighted combination of the input features and passes them through a sigmoid function.
Sigmoid function transforms any real number input, to a number between 0 and 1.

MODEL 2:-
Count Vectorizer 
Scikit-learn's CountVectorizer is used to convert a collection of text documents to a vector of term/token counts.
It also enables the pre-processing of text data prior to generating the vector representation.
Logistic Regression
After I created a train-test split of the dataset,
I’ve applied logistic regression which is a classification algorithm used to solve classification problems.
The logistic regression classifier uses the weighted combination of the input features and passes them through a sigmoid function.
Sigmoid function transforms any real number input, to a number between 0 and 1.

STEP 5:- TESTING 
AFTER TESTING THE ACCURACY OF BOTH THE MODELS ON THE TEST SET 'COUNT VECTORIZER GAVE MORE ACCURACY THAN TFIDF '
The only difference is that the TfidfVectorizer() returns floats while the CountVectorizer() returns ints. 
TfidfVectorizer() assigns a score while CountVectorizer() counts.

STEP 6:- ADDITIONAL STEP 
Since the Accuracy was already high I decided not to go with HYPERPARAMETER  TUNING 
If th accuracy had been low I would have used GRIDSEARCH 
By using GridSearch we are able to try different combinations of values to find the model with the lowest error metric, which is in this case log loss.
In logistic regressions ‘C’ determines the amount of regularization, and the lower values increase regularization.
The low accuracy scores are due to bad regularization parameters. 
Once we traine the model using the best hyperparameter we get the BEST accuracy scores.
