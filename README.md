STEP 1 :- Let’s start with the basic data exploration: Dataset consists of 20,000 ROWS with 15 attributes which are :- </br>
            uniq_id </br>
            crawl_timestamp</br>
            product_url </br>
            product_name </br>
            product_category_tree </br>
            pid </br>
            retail_price </br>
            discounted_price </br>
            image </br>
            is_FK_Advantage_product </br>
            description </br>
            product_rating </br>
            overall_rating </br>
            brand </br>
            product_specifications </br>
From the product_cateogry_tree I selected a primary cateogry which is at the starting of tree  which will act as dependent variable </br>
[
![image](https://user-images.githubusercontent.com/79022961/113734850-8bdf2680-96b0-11eb-814d-50a758cccdc3.png)
](url)
</br>
 I deleted All the other coloumns apart from description and product cateogry .</br>
Description will act as a independent variable .</br>
I deleted all the rows with the missing values in 'Description' and 'product cateogry' coloumn </br></br></br>

STEP 2:-Text cleaning and Preprocessing</br>
There can be multiple ways of cleaning and preprocessing the textual data and here I have applied the ones which are frequently used in NLP pipelines.</br>
Lower case: Since we would expect to treat “Food” and “food” as the same word, without creating various predicting powers, I’ve down-cased each word.</br>
Contractions: I’ve replaced contractions with their longer forms such as “isn’t”: “is not”, “can’t”: “cannot“. To do so, I’ve imported contractions list from here.</br>
Remove special characters: I’ve cleaned the data from any special character such as double quotes, punctuation, and possessive pronouns.</br></br></br>

STEP 3:-TRAIN-TEST SPLIT </br>
With the random State of 225 I applied train-test-split to saperate train and test data.</br></br></br>


STEP 4:- APPLYING A MODEL</br>
MODEL 1:-</br>
Tf-Idf</br>
Tf-Idf stands for term frequency-inverse document frequency, and instead of calculating the counts of each word in each document of the dataset (Bow),</br>
it calculates the normalized count where each word count is divided by the number of documents this word appears.</br>
Logistic Regression</br>
After I created a train-test split of the dataset,</br>
I’ve applied logistic regression which is a classification algorithm used to solve classification problems.</br>
The logistic regression classifier uses the weighted combination of the input features and passes them through a sigmoid function.</br>
Sigmoid function transforms any real number input, to a number between 0 and 1.</br></br>

MODEL 2:-</br>
Count Vectorizer </br>
Scikit-learn's CountVectorizer is used to convert a collection of text documents to a vector of term/token counts.</br>
It also enables the pre-processing of text data prior to generating the vector representation.</br>
Logistic Regression</br>
After I created a train-test split of the dataset,</br>
I’ve applied logistic regression which is a classification algorithm used to solve classification problems.</br>
The logistic regression classifier uses the weighted combination of the input features and passes them through a sigmoid function.</br>
Sigmoid function transforms any real number input, to a number between 0 and 1.</br></br></br>

STEP 5:- TESTING </br>
AFTER TESTING THE ACCURACY OF BOTH THE MODELS ON THE TEST SET 'COUNT VECTORIZER GAVE MORE ACCURACY THAN TFIDF </br>
The only difference is that the TfidfVectorizer() returns floats while the CountVectorizer() returns ints.</br> 
TfidfVectorizer() assigns a score while CountVectorizer() counts.</br></br></br>

STEP 6:- ADDITIONAL STEP </br>
Since the Accuracy was already high I decided not to go with HYPERPARAMETER  TUNING </br>
If th accuracy had been low I would have used GRIDSEARCH </br>
By using GridSearch we are able to try different combinations of values to find the model with the lowest error metric, which is in this case log loss.</br>
In logistic regressions ‘C’ determines the amount of regularization, and the lower values increase regularization.</br>
The low accuracy scores are due to bad regularization parameters. </br>
Once we traine the model using the best hyperparameter we get the BEST accuracy scores.</br>
