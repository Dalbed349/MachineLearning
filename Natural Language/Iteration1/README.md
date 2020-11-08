# First Iteration: Naive Bayes Classifier 

Originally I had planned to submit a Ridge Regression model with a similar feature set. The TP and FPs were around .6 and .3 respectively. 

Upon making a change to n_features from 2 ** 17 to 2 ** 16 to 2 ** 15 I noticed a huge leap in performance for the Naive Bayes classifier. 

It is still possible that I will end up using another model but for the time being a true positive rate of about .75 seems too good to pass up. 




### Changes made to feature set:

1. Hashing Vectorizer: hv = HashingVectorizer( n_features=2 ** 15, alternate_sign=False, strip_accents='ascii', lowercase=True, ngram_range=(1,3))

2.     Additional Quantitative Features 

       toxic_data['word_count'] = toxic_data['comment_text'].str.split(' ').str.len()
       toxic_data['punc_count'] = toxic_data['comment_text'].str.count("\.")
       toxic_data['punc_count2'] = toxic_data['comment_text'].str.count("\!")
       toxic_data['upper_case'] = toxic_data['comment_text'].str.count(r'[A-Z]')
