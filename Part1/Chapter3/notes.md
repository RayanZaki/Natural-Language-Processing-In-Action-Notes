# Intro:

Having collected and counted words (tokens), and bucketed them into stems or lem-
mas, it’s time to do something interesting with them. Detecting words is useful for
simple tasks, like getting statistics about word usage or doing keyword search. But
you’d like to know which words are more important to a particular document and
across the corpus as a whole. Then you can use that “importance” value to find rel-
evant documents in a corpus based on keyword importance within each document.

- This chapter covers how to convert words into a a descreter and continuous space.

### It will cover:
- Bag of words
- Bag of n-grams
- TF-IDF vectors


## 3.1. Bag of Words:
Two vatiations:

- Binary OR
    - For short texts it could be more usefull than long texts
- Occurence Counter


## 3.2 Vectorizing:
- Usually the size the of the docuement is not relevant hence the lenght of the vectors is negliged by using cosine similarity

## 3.3 Zipf's Law:
Zipf’s law states that given some corpus of natural language utterances, the
frequency of any word is inversely proportional to its rank in the frequency table.
