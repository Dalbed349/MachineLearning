
# MachineLearning

## 10/18/2020 -- First Full iteration uploaded with the following changes. 
1. HashingVectorizer. Added the following changes : <br/>
        a. strip_accents ----- remove accents from corpus <br/>
        b. lowercase = True -----convert all letters to lowercase <br/>
        c. ngram_range=(1,3) ----- add trigrams to matrix. <br/>
```if (not test): # fit_transform()
        hv = HashingVectorizer(alternate_sign=False, strip_accents='ascii', lowercase=True, ngram_range=(1,3))
        
        ##### 3 changes. strip accents, lowercase, ngram_range,  ## CUT FROM ORIGINAL: n_features=2 ** 17,
```
2. I attempted to make quantitative feature changes but there was not much success:<br/>
       <br/>           a. I wanted to count the uppercase words in the corpus and landed on the code below unfortunately I
         am new to python and could not quite figure this out. My logic was to split the comments by space and then count uppercase only words.<br/> 
       <br/>         b. I was able to successfully add a quantitative feature counting the exclamation marks in the corpus although this was a simple change from the started code.
        
```
   a.  # toxic_data['case_count'] = toxic_data['comment_text'].str.split(' ').str.isupper()
   b.  # toxic_data['punc_count2'] = toxic_data['comment_text'].str.count("\!")
```
3. Current goals are to figure out how to count both uppercase letters / all uppercase words in a given wikipedia comment. 


## Canvas Discussion 2: Alpha Values


## Canvas Discussion 3: LinearSVM-C-Values 

