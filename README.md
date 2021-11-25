# STS-Task
Semantic Textual Similarity (STS) measures the degree of equivalence in the underlying semantics of paired snippets of text. While making such an assessment is trivial for humans, constructing algorithms and computational models that mimic human level performance represents a difficult and deep natural language understanding (NLU) problem. 
Here we have tried out two approaches for STS 2016 Core - with English sentence pairs on Plagiarism Detection, Q&A Question-Question, Q&A Answer-Answer, Post-Edited Machine Translations and Headlines.

## Train Data
For train data, we have about 3000 records from STS 2015. 

## Test Data
Test data has about 9000 records split into various categories - Plagiarism Detection, Q&A Question-Question, Q&A Answer-Answer, Post-Edited Machine Translations and Headlines.

For more information, please check [STS 2016](https://alt.qcri.org/semeval2016/task1/).

## Model
Two approaches have been tried here.
- **Approach 1:** An extremely simplistic approach which gets the word embedding and compares the cosine similarity.
- **Approach 2:** Train a BERT model with LSTM layers on train data and then predict with the test data.

## Results
For each evaluation set, models generate a plain text output file having one line per STS pair. Each line provides the score assigned by an STS model for that pair. The output files are then evaluated using the pearson correlation. A script noconfidence.pl has been provided by the organisers for the same.

**Approach 1**

|Category	|Score|
|---|---|
|Answer-answer	|0.60547|
|Headlines	|0.74303|
|Plagiarism	|0.53249|
|Post edited Machine Translations	|0.79120|
|Question-question	|0.79479|

**Approach 2**
|Category	|Score|
|---|---|
|Answer-answer|	0.45165|
|Headlines|	0.73398|
|Plagiarism	|0.59267|
|Post edited Machine Translations|	0.78496|
|Question-question	|0.40795|

## Conclusion
We had trained BERT with just 3000 records and tested on data with about 9000 records. Traing BERT for more epochs and with more data should give better performance as compared to approach 1.
