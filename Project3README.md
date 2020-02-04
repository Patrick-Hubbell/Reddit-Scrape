# Project 3 Read Me 
## Problem
My problem that I solved with this project was that Amazon's parental controls are lacking in the ability to tell different genres from one another. If parental controls are set a child can get any free book regarless of genre. Children should not be allowed to read books with adult content.
## The Prosess 
The adult genre I chose to be able to identify was the erotic genre. I would have loved to be able to include more genres I did not have the allotted time to be able to do so.
Using pushshift I pulled requests from the reddit APIs of two specific pages I used. As I brought in the data I also tokenized it just to try and be efficient, as well as removing most of the html artifacts. After tokenizing I lemmatized the data, this is to make all my words into the singular form so when I run a count over the data it doesn't give me counts for 'Nights' and 'Night'. Once my data was lemmatized I put it into a data frame. In my next notebook I did a little exploratory and checked for null values. While I did not find null values I did find that after removing the html some posts were empty lists. In addition some posts had been deleted and then had a deleted status. After making sure I got rid of those posts I my data was ready to be combined into one data frame and put through a count vectorizer. I used two two different transformers with my data and two different estimators. I made three different pipelines in order to find my best data.

## Results
|Transformer and Esimator| Results|
|------|------|
|Count Vectorizer with Logistic Regressor| Train - 99.7%, Test - 89.8%|
|Tfidf Vectorizer with Ligistic Regressor| Train - 95.8%, Test - 87.5%|
|Count Vectorizer with Bernoulli Nieve Bayes| Train - 81.9%, Test - 75%|

## Conclusion
While my Count Vectorizer and Nieve Bayes model has less room for error being only about 7% apart. My choice of model would be to use the Count Vectorizer and Logistic Regressor which is about 90% accurate. This makes my recommendation to use a predicter to discern the difference between Adult Erotic writing and literature that would be more appropriate for children.
