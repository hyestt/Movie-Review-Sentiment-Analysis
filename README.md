# Movie-Review-Sentiment-Analysis
https://www.kaggle.com/c/sentiment-analysis-on-movie-reviews

### Dataset
IMDB sentiment analysis data set, which has 100,000 multi-paragraph movie reviews, both positive and negative. 
The dataset has 50,000 rows (i.e., reviews) and 3 columns. Column 1 "new_id" is the ID for each review (same as the row number), Column 2 "sentiment" is the binary response, and Column 3 is the review. 

### Target
Evaluation metric is AUC on the test data.

### Ideal Scenario
Google's Word2Vec is a deep-learning inspired method that focuses on the meaning of words. 
Word2Vec attempts to understand meaning and semantic relationships among words. 
 
### Main File
Save my main file as mymain.ipynb

### Data Preprocessing 
Select s to determine which train and test split (S = 1 or 2 or 3). Then I left join split data and generate different training and test dataset. Last, I store all the preprocessing in train_list and test_list

### Vocabulary list and text processing
First, I create the function review_to_words to remove any non-letters and stopwords in review. 
Then I import Tokenizer from keras and set the max_feature to 5000. Before I split the data into different training and test dataset, 
I use whole dataset to fit Tokenizer. You can find the most 5000 frequent vocabularies in myVocab.txt file.

![alt text]()

### Model Prediction 
Fit LSTM model and do the text processing
LSTM model is units of a recurrent neural network (RNN). The parameter turning is refered to the reference from Kaggle’s kernel. 
Use the tokenizer we trained before, we can convert the text in review to sequence. Then use pad_sequence to transforms a list of sequence into a 2D numpy array. 
The activation function I use is sigmoid and I use Adam optimizer.

### Result 
According to evaluation matrix, the best performance I reached is 0.94489. I’ve saved all the result in result.txt file. 
Then, I draw AUC graph based on predicted result.

![alt text]()
