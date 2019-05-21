# SAREK (Sonnet Affective Recommender with Embedding Knowledge) [Desktop version]
This is SAREK, a personal sonnet recommender for spanish poetry!

This repo is a web app that allows users to search for poems with a query that could consist in either a unique word or a sentence. After receiving it, SAREK searchs for the most relevant sonnet from a corpus of Spanish poetry sonnets (dating from S.XV to S.XX) and shows that poem in the application.

There are two different retrievals performed:
  * One is done using a joint function of the individual words of a stanza and with BERT embedding to assign each word an individual vector. The similarity among stanzas and the query text is computed using cosine similarity.
  * Another is done using also the joint function and cosine simmilarity but with a different embedding: word2vec in it's Skip-Gram version using the dataset available in: https://www.kaggle.com/rtatman/pretrained-word-vectors-for-spanish/
  
The purpose of this app is to offer the user the two possibilities so he or she can choose the retrieval method that yields better results.

## 1. Requirements
* Python 3.6.1 
* Pip

## 2. Setup
After cloning/downloading the repo install the requirements
```
$ pip install -r requirements.txt
```

After that, install Spacy language model with the following command

```
$ python -m spacy download es_core_news_sm
```

Then download the datasets needed for the application from:
```
https://unedo365-my.sharepoint.com/:f:/g/personal/abarbado5_alumno_uned_es/Eh6rYEkgXRdIsKgXjvv5NXoBFHMq1HNkayFHmGk_RY-_zg?e=PaZPoG
```
And move all files to the **datasets** folder before executing the application.

Then execute the interface_main.py file

```
$ python interface_main.py
```

And then, after some time, a pop up window will appear where you can interact with the system. Sometimes it takes a while to retrieve the sonnets (the code could be further optimized), so be patient.

## 3. Additional considerations
* The machine used to run the program shoudl have at least 4 gb of RAM and 2 cores
* As it's said, it takes a while for the program to start (around 2-5 min) 
* When the sonnets are loaded in the screen you can scroll down in anyone of them if the mouse is over the text of that specific sonnet. There may be some minor bugs that include not deleting the old contents
from the previous query results after that retrievals; for that cases simply scroll to the top sonnet available and that'd be the result of the last query.
* The user_results will contain all the user's interactions with the system. DO NOT delete it so later it will be possible to analyze the user's interactions.

Enjoy!
