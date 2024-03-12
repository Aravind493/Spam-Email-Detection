# Spam-Email-Detection

This project aims to classify emails as spam or not spam using Natural Language Processing (NLP) techniques and machine learning algorithms. The dataset used contains raw text from emails labeled as either spam or non-spam (ham). The classification model is trained on this data to predict the category of new emails.

Step-by-Step Process:

1.Loading the Dataset:

  The dataset containing raw email text and their corresponding categories (spam or ham) is loaded into a pandas DataFrame.

2.Data Preprocessing:

  Irrelevant columns, such as 'FILE_NAME', are dropped from the DataFrame.
  A new column 'Length' is added to calculate the length of each email message.
  Maximum length of a message is found (234358 in this case).

3.Text Preprocessing:

  A PreProcessText class is defined to perform text preprocessing tasks.
  Text preprocessing involves:
  Removing punctuation from messages.
  Removing stopwords using NLTK's English stopwords corpus.
  Tokenizing the text (splitting into words).
  
4.Bag-of-Words Representation:

  CountVectorizer from scikit-learn is used to convert text data into a matrix of token counts (bag-of-words).
  The analyzer parameter of CountVectorizer is set to the token_words method of PreProcessText class for custom tokenization.
  
5.Sparse Matrix and Sparsity Calculation:

  The shape of the sparse matrix representing the bag-of-words is printed.
  Sparsity of the matrix is calculated to understand the density of non-zero elements.
  
6.TF-IDF Transformation:

  TF-IDF (Term Frequency-Inverse Document Frequency) transformation is applied to normalize the bag-of-words representation.
  TfidfTransformer from scikit-learn is used for this purpose.
  
7.Model Training:

  Multinomial Naive Bayes classifier is chosen as the machine learning algorithm.
  The model is trained on the TF-IDF transformed data along with the corresponding categories.
  
8.Model Evaluation:

  Accuracy of the trained model is calculated using the accuracy_score function from scikit-learn.
  The project achieves an accuracy of 96% in classifying emails as spam or not spam.
  
9.Prediction Function:

A function predict_spam_or_not is defined to predict whether a given message is spam or not.
User can enter the message and check whether the mail is spam or not through this function
