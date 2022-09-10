
# Matching Resumes

This repo is about matching 32 resumes with a job describtion in a json file.
It's divided into 2 notebooks.


## First Notebook

## Roadmap
in this notebook I used low level NLP to process text and generate the output. the problem is, it's very computationally expensive that's why I used aws machine to run it.
This notebook is inspired by https://github.com/peermohtaram/Vector-Space-Model.  

- created dictionary of keys as person name, values as his/her resume.
- created wordList_removePuncs func to remove stop words.
- calculated tf by creating termFrequencyInDoc func.
- calculated idf for every word.
- calculated tfidf score.
- finally created the VSM taking the job description as query.

## Second Notebook

## Roadmap
This notebook is faster than the previous one, due to more text cleaning and using libraries.

- created the same dictionary as before
- created words tokens using word_tokenize
- stemming words 
- removing stop words 
- removing some unnecessary words like 'aaa', 'aaaa' in the resumes as they don't add any value to the resume, and may lead to false score in ranking.
- calculated tf-idf score by TfidfVectorizer from sklearn, putting sublinear_tf as True to avoid repetition of words and exploding score.
- finally measuring cosine similarity between job description and the 32 resumes and rank them according to their level of skills must/should/nice to have.