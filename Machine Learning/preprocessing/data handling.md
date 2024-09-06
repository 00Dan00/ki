# Missing data
- usually not wanted since it could lead to a lot of data being dropped and missing

## 1 Drop Columns with missing data
```python
df_clean = df.dropna(axis=1)
```

## 2 Simple Imputer
imputes the values with the mean (or w.e strategy is chosen )
```python
imputer = SimpleImputer(strategy='mean')  # Other strategies: median, most_frequent, constant

# Use fit on training data to fit the imputer to the training data (doesn't need to be fitted again for the validation data)
imputed_X_train = pd.DataFrame(imputer.fit_transform(X_train))
imputed_X_valid = pd.DataFrame(imputer.transform(X_valid))

# columns were deleted
imputed_X_train.columns = X_train.columns
imputed_X_valid.columns = X_valid.columns
```
Could also create another column ('_was_missing') indicating if a column was missing to give the model further information

## 3 fill with outlier number
- example in pandas 
```python
df.fillna(value=-999999, inplace=True)
```

# Categorical Data

## Ordinal Encoding
- used for input data (X)
assigns each unique value a different integer. Only works if there is a hierarchy 
```python
from sklearn.preprocessing import OrdinalEncoder
# use ordinal values and sort them in ascending order for our encoder
ordinal_encoder = OrdinalEncoder(categories=[["poor", "fair", "good", "very good", "excellent"]])

df['ordinal_column'] = ordinal_encoder.fit_transform(df[['ordinal_column']])

```

## Label Encoder
- used for output (y)
```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()
y_encoded = encoder.fit_transform(y)

```
# One Hot Encoding
if our categorical data doesn't have a hierarchy (ex. colors)

### sk learn
```python
from sklearn.preprocessing import OneHotEncoder

#example column named colors
data = {'colors': ["green", "yellow", "red", "blue", "purple"]}
df = pd.DataFrame(data) # usually contains more information

# OH encoding the values for colors
OH_encoder = OneHotEncoder(handle_unknown='ignore', sparse_output=False)
OH_encoded = OH_encoder.fit_transform(df[['colors']])
OH_df = pd.DataFrame(OH_encoded, columns=OH_encoder.get_feature_names_out(['colors']))

df = pd.concat([df.drop(columns='colors'), OH_df], axis=1)

# results in df with oh encoding. Can be used with a pipeline and irgnores unknown values 
```

### df get dummies
```
df = pd.get_dummies(df,columns=["column"])
```
# String data 

### Count Vectorizer
- Tokenization: Splits text into individual tokens (default on whitespace and removes punctuation)
- Builds the vocabulary of unique tokens in the corpus (words or n-grams)
- transforms each document into a vector with the token integer values
```python
from sklearn.feature_extraction.text import CountVectorizer

vectorizer = CountVectorizer()
# Vectorizer parameters:
# stop_words = 'language' : removes stop words from corpus
# max_features = 'n' only uses the top n features 

# creates a sparse matrix
X = vectorizer.fit_transform('string data')
X_np = X.toarray()
```

### TfidfVectorizer
- Tokenization and Vocabulary building just like count vectorizer
- TF-IDF calculations 
- Term Frequency (TF): counts the occurences of each token in each document
- Inverse Document Frequency (IDF): Computes the importance of each token across the corpus
- TF-IDF score: assigns a weight to each token, emphasizing tokens that are important to a document but not common across all documents.
```python
from sklearn.feature_extraction.text import TfidfVectorizer

tfidf_vectorizer = TfidfVectorizer() 
X_tfidf = tfidf_vectorizer.fit_transform(documents)
```