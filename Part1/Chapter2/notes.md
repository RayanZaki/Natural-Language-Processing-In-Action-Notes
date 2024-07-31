## Intro:

- feature extraction can rarely retain all the information content of the input data on any ml pipeline


## 2.1: Challenges:
    - stemming

## 2.2: Building the Grammar

### 2.2.1: For tokenization we can use NLTK

- A good tokenizer is Treebank (deafult for word_tokenize)
- casual_tokenize: is used for informal text

```
>>> fron nltk.tokenize import RegexpTokenizer
>>> tokenizer = RegexpTokenizer(r'\w+|$[0-9.]+|\S+')
>>> tokenizer.tokenize(sentensce)
['Thomas',
'Jefferson',
'began',
'building',
'Monticello',
'at',
'the',
'age',
'of',
'26',
'.']
```


- NLTK provides a list of stop words

- Spacy is more efficient since it doesn't assume the text is separated into sentences


### 2.2.2 Case folding (Normalizationn):

- Is whem you consolidate multiple spellings of a word that differ only in their capitalization 
- It is important to know when to use it and when not
- usualy it is not used
- Sometimes it is good to provide a way to deactivate normalization
- Case folding improves search recall but worstens search precision

### 2.2.3 Stemming:

- Stemming improces search recall but worstens searc precision
- Sometimes it is good to deactivate steeming


- Popular stemmers:
    - Porter Stemmer
    - Snowball stemmer


```python
>>> from nltk.stem.porter import PorterStemmer
>>> stemmer = PorterStemmer()
>>> ' '.join([stemmer.stem(w).strip("'") for w in
...
 "dish washer's washed dishes".split()])
'dish washer wash dish'
```



### 2.2.4 Lemmatization:
- We should ne carefull of spoofing;
- spoofing—when someone intentionally tries to elicit the wrong response from a
machine learning pipeline by cleverly constructing a difficult input.
- Lemmatization is a better way of stemming
- POS could be used for better accuracy
- Are only used in large scale information retrieval apps

```python
from nltk.stem import WordNetLemmatizer

lemmatizer = WordNetLemmatizer()
word = "running"
lemmatized_word = lemmatizer.lemmatize(word, pos='v')
print(lemmatized_word)  # Output: "run"

```

### 2.2.5 Use cases:
- **Stemmers**:
    - are faster to compute and requires les complex code and datasets
    - But they make more errors and stem far more words then a lemmatizer.

- Both will reduce vocab size and increase ambiguity
- Lemmatizers do a better job retaining information



- Stem and lematize improves recall
- They will reduce precision significantly 

- If app involves search --> focus on recall:
- If app is a chatbot --> focus on accuracy


- **Bottom line:** don't use stemming and lematization unless you have limited amount of text that contains usages and vapitalzations of the words you are interested in


## 2.3 Sentiment:

- No matter the representaion of the tokens, they contain some information
- An important part of this information is sentiment

### The two approaches to sentiment analysis:
- Rule Based ( hand crafted)
    - VADER
- ML based (learnde by machine)
    - Naive Bayes


## Chapter Summary:

- n-gram tokenization help retain some of the word order information in a document
- Normalization and stemming consolidate words into groups that improve the revall for search engines but reduce precision
- custom tokenizers like `casual_tokenize()` can improve prevision and reduce information loss
- Stop words can contain useful information and discarding them is not always helpful



[Next Page](../Chapter3/)
## TODO: Sentiment analysis project: page 67
