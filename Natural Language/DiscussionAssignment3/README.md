

Dallas Alberti  11/8/2020

Machine Learning Discussion Assignment 3

  

Feature Set:

  
![](https://lh3.googleusercontent.com/7qyxpTo4f-FroUb_kJpBW9JJv467BSdX1iYtt_Eg5WWP6JUwYtH9y9ou2s6GgfskaBVIYMe7EtB7Nu5sxUrtYjIIVa6YMEhKe_YGZ3A3gSnVFOJjjtHqsnHbzdgsZyLJifkiBOkM)  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

Error encountered: Failure to converge. Iterations increased from 1000 to 10,000 to 100,000. ![](https://lh6.googleusercontent.com/kwQkMrM_bZCvCZPnl9l_lCEmvYGjkuyiI5q9p0KXY5vcQb2vGl5wQg_YoF0AAxbCksGrGq4s4jIYesv0uBK67T6z5IimF3cC4lFuOz1FsVIl9X0o-_MV5f4ZCV_Aoh8f4Idnfose)

  
  
  
  
  
  
  
  

Tests: C=1, 0.7, 0.4, 0.1, 0.001, 0.0001

1.  SVC(C=1.0) ![](https://lh5.googleusercontent.com/sQ3_kIIgx18ADf5sclfRA1m6UaN7bPg53vy4GCVB6nw0m1Nh1Ye8U4YgTfIbVZ7me0l-tA-KYCdEoK90H4t_5c21iS65pFyyf1r-VeSplYc5izA2u8eLic1DImmTI1RMODBNO1p4)
    

  
  
  
  
  
  
  
  

2.  SVC(C=0.7)
    
3.  SVC(C=0.4)![](https://lh5.googleusercontent.com/KBetKZsI68SvrVZbnFLviTQWvPgH7puxIsuSDF619ZKEfshroTEg-klk9fegrHTm786KaxANpZ_6ZB4KmzqwiCN045uvs2_CwAr6r493ob6VSH5tcP3Tsn1JiS3_dmFezIfyfn15)
    

  
![](https://lh4.googleusercontent.com/AEQGw-QqUDpqARN4BkbQbHbMqbBh_N5yLyNou96jAs3ZL6DKBBMRXMPwocIBfGsHy4YOfqZ6up3UL37-MPXinybdZJG-2_9JdtpgSqYJLRwbAtr2cSQmIJ2eu6yywmUe3qeP7BRF)  
  

4.  SVC(C=0.1)
    

  
  
![](https://lh6.googleusercontent.com/5sSZd0LtNbnOVnVvVfBZNYhBwbeKqrjTCkxt8ySvFhgKPQi965d2ioe6qpZMXTS2SoYY5p4F9WhtxdikNqt4aw4WdCHi3GjnJZEMT64UF2wK24vUtMvhJmcNHPH53srXwfS6Vlek)  
  
  
  
![](https://lh3.googleusercontent.com/l-ObB7KqZUsJJacBh5Y_iTi4KfrokcJsF3a5oN7uNOesuf7v7stZxKy5a3J2GwC_Zi4RGlKnfiloKtwlzk8N7amX3StJTbUGDRr2uUiNVMpY3BuZZmFVhqRFA1rwqpVuxkuLkA5W)  
  

5.  SVC(C=0.001)![](https://lh5.googleusercontent.com/uWJ9z3KtSX2z66ubxqS6HH1R3SpyMc0M0zfc0IuouNT3G8-KNWXoW1ukSP22ZaG_BQK8KYixWMclW_bG-RjpQTh0cQZPLzo5V6zpFzHBYZid7FyhdxVDZ7TOFdSB0EtJHE07rPhh)![](https://lh6.googleusercontent.com/tguhiYJ9cjMjGDP3jSMaxhDUYVRU8GrkZmYars8zlw34PktBJkwvtHQEhIGnoRGXOf3joDvDRI5Vbq64oHUKFQ7umckO1G8TiH6A8F1_FOTsnp87m5utnag-045XA-bmEJhUWA0f)
    

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

6.  SVC(C=0.0001)
    

![](https://lh5.googleusercontent.com/GleHnyWekkprvt0dUnXi6jkWy1d0dnxyhiMvoi-dHFp-OJM7R0SwkjEr2uLvLfl6y3IO-6-JRq0qpJZ4q3XViOvPK9GKGwFsUlHXAilaW9AXRbFbOnxDTTKjRgJ6iiJ-JovDuv8-)![](https://lh4.googleusercontent.com/MeA8HRzKCv901p2D0VX8oISDQ6a0Fp9Yh8VpbnOzBaQIBpm0nDmNcRQC7ckPWliujUHxG9wUjyOtulnWxXeoqaTZZufF6FTBvJwaEfbNntEzYZc9_gdr5KzHTqbvPHYBY5a_1Mf5)

  

Writeup:

  

For discussion assignment 3 I introduce the ‘Linear Support Vector Classification’ as outlined in: [scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html#sklearn.svm.LinearSVC](https://scikit-learn.org/stable/modules/generated/sklearn.svm.LinearSVC.html#sklearn.svm.LinearSVC). The documentation for the C-Support Vector Classification suggests to use this LinearSVC when samples are beyond tens of thousands of examples. I introduce two new blocks of code. The first is placed below the ‘MODEL:SVM, linear’ in the starter code. Here I ‘comment in’ the full example of a LinearSVC in order to reference different parameters that might be changed however for the purpose of this assignment only C values and max iterations are altered.

The code block was written in similar format to the other models that are tested. Before discussing the effects of C value manipulations it is important to note that every time I ran the code I received the error “ConvergenceWarning: Maximum number of iterations reached before convergence. Consider increasing max_iter to improve fit.” This is shown in the second image of this document. I attempted to change the max iterations from 1000(Default) to 10,000 to 100,000 however no significant changes in performance were detected and my success measures did not change. The features used for this experimentation are outlined in image one.

I chose to begin the test with a default C value of C=1 and then work my way down to a value of .0001. One may notice that the scale of the graphs changes as I iterate through different values of C and that is because I started to realize that changes to this value were very small and often undetectable with an X-Scale of 0-1.0. My initial reaction was that as the C value was decreased the false positive rate would decrease. However upon looking at the 3 performance measures images for C=.1, C=.001, and C=.0001 we can see that FP initially decreases (.1) before increasing again (.0001). In addition to an increase in FP for the C=.0001 test, the FN rate greatly increases from 25(c=.001) to 494(c=.0001). The results of this testing would suggest that, for this feature set, an optimal C value would be closer to .001. In other words, regularization has a strong positive impact on the models accuracy until a certain threshold is met.
