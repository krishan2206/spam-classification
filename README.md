# Multinomial Naive Bayes Classifier
###Uses the Naive Bayes Classifier to predict whether a given text/document is either spam or not spam (ham).

Set training folder with spam/ham subfolders.
Set test folder with spam/ham subfolders.
In case you want to classify a separate file as spam/ham,
pass the file through the read_file function first, which returns
terms in the file as a list. (probably will change this soon)
###A short explanation:
given a message M, find P(C | M) where C = (spam OR ham)
Bayes Rule states that :
P(C | M) = (P(M | C) * P(C)) / (P(M))
(posterior) (likelihood) (prior) (evidence)
where P(M | C) can be stated as the product of P(m | C) for every term m in M.
The predicted class returned is the one that has maximum value for P(C | M).

####Notes :

Log of probabilities is taken to prevent underflow (extremely small prob. values)
This changes the multiplication of likelihood and prior to addition.
Laplace smoothing (counts+1) is done to prevent multiplication by zero.
Evidence P(M) can be disregarded during calculation.
Metrics are calculated at the end to determine classifier performance.
