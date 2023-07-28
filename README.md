# Sentiment-Analysis-for-Market-Research
Performing text pre-processing, Bag of words, term frequency-inverse document frequency and building the classification model.

Text Pre-processing:

Html Tag Removal: Any HTML tags present in the text data are removed using regular expressions to clean the text.
Tokenization: The text is tokenized into individual words or tokens to break it down into smaller units for further analysis.
Remove Numbers: Any numeric digits present in the text are removed as they might not contribute significantly to sentiment analysis.
Removal of Special Characters and Punctuations: Special characters and punctuations are removed to focus on words' semantic meaning.
Removal of Stopwords: Common stopwords like "the," "is," "a," etc., are removed as they occur frequently and carry little sentiment information.
Conversion to Lowercase: All text is converted to lowercase to ensure that the model treats words with the same letters but different cases as the same word.
Lemmatization or Stemming: The words are lemmatized or stemmed to reduce them to their base or root form, ensuring variations of a word are treated as the same.
Vectorization:

CountVectorizer: The pre-processed text data is transformed into a sparse matrix of token counts, where each row represents a document, and each column represents a unique word (token) in the entire corpus. The values in the matrix represent the frequency of each word in the corresponding document.
TfidfVectorizer: The pre-processed text data is transformed into a sparse matrix using Term Frequency-Inverse Document Frequency (TF-IDF) representation. TF-IDF takes into account both the frequency of the word in a document and its rarity in the entire corpus, giving more weight to words that are rare in the entire dataset but frequent in a particular document.
Model Training and Evaluation:

The dataset is split into training and testing sets.
A classification model (Randomforest algorithm) is chosen for sentiment analysis.
The model is trained on the training set using the CountVectorizer and TfidfVectorizer transformed data separately
The model is evaluated on the testing set to measure its performance and accuracy in predicting sentiment labels.
Cross-Validation:To obtain a more robust estimate of the model's performance, k-fold cross-validation is applied.
The data is split into 5 subsets (folds), and the model is trained and evaluated 5 times, with each fold being used as the test set once.
The final performance metric is typically the average of the performance scores obtained from all 5 iterations.
Top Features:

After transforming the pre-processed text data using CountVectorizer or TfidfVectorizer, the feature names (words/tokens) are extracted from the vectorizers.
The top 40 features are printed, which represent the most frequent words (CountVectorizer) or the words with the highest TF-IDF scores (TfidfVectorizer) in the entire corpus, and then a wordcloud is built for both.
These steps collectively help in preparing the Twitter airline sentiment data for sentiment analysis and building a classification model that can predict the sentiment of airline tweets accurately. The process involves cleaning and transforming the raw text data into a suitable format for machine learning algorithms, enabling us to make data-driven insights and predictions about the sentiment of tweets.

Model Performance
Accuracy

TF-IDF: 79.5%
Count Vector: 80%
Estimators: 200

Dataset: Twitter sentiment analysis dataset (14,601 tweets)

Conclusion:

Both TF-IDF and Count Vector achieved high accuracy on the dataset.
Count Vector had a slightly higher accuracy than TF-IDF.
The number of estimators was set to 200.
