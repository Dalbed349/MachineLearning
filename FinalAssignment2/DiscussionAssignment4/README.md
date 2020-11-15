Dallas Alberti  11/15/2020

Discussion Assignment 4
Dallas Alberti 11/15/2020

Documentation Working HOG

  

UPDATE: Histogram of Oriented Gradients working. Testing pixels_per_cell=(15,15)

  

![](https://lh4.googleusercontent.com/qEUxwGn3zElLSfnetSd74GKf_1_a8_wHMvinZFJJwls2qRInDM6mcXKTrrDsk0s002pJIIN4UDlzguM9_gqgBzK8qVcPUY0xxYJgAXQlaUFhEyyHtiqGhYBB_mHg6gJKv-IEalcg)

  

Solution to previous errors ->process_raw_data function - > Since it is returning two things (the representation and a visualization of it), you need to reference the first item in the process_raw_data function.

-> features_list.append(image_manipulation(row['img_name'], images_fp))

Change to:

-> features_list.append(image_manipulation(row['img_name'], images_fp)[0])

  
  
  
  
  
  

Perceptron:![](https://lh5.googleusercontent.com/jy9zkwSSTE7jOV7Mud4DOZbbJ-1fDPHHGpgGvruEA8GlXkz-HNVpRSOQGFfdiyiM7Gg9HsLBs2Fis8aV-CcGR7bLQqrELeuu0MSGkL33jmnI65GFjm7CmFfhFKsaEFYY0-AoxJ_N)

  

Neural Network: ![](https://lh3.googleusercontent.com/xxXCZFOLJtEyzGSmS6jCMYg22Xp8c-dwDy2n94CSe-DyLdAaQ_RSxhRmNIRln9MRTKXXbQjg-RT6Hy7f2Y-ukM7p2i2nuNwhQtVGOxyiy-WiASuHZh9ghKB3eYsyrGudnXbw6C-c)

ROC:

  

![](https://lh3.googleusercontent.com/BxVGVLWj56pzYyF5UnW-gCmqRYmLC_l_NA4OI6CJfVFwlRHCLFSjgPTRlgTuhSXYYwFrz4FCTxGPJKw1kevXZukMX90O37CNRSSUdqAVVVlEkW0GYpCACeVFnt1PaQNiXjM3d9qP)
  
----------------------------------
I started off experimenting with the histogram of oriented gradients (hog) before running into errors and transitioning to the default canny edge detector.

  
![](https://lh4.googleusercontent.com/r8EgYbcyb96drnpzfotb7it8uxE3iXiDhYuzxnSzY-Fyx2uXLpv4gXrAz_VLn_gqsaSd4KiEVMiL7-dLPWyfehPIUzAg0jXsEmceNGlYq8mM6S0DOQwyGZ5Mf5GUyMw7WgHeHadK)

This image shows a setup for the hog. Pixels per cell are set to (4,4) which creates images closely resembling human vision. I noticed in the images_starter file that increasing these numbers redacted the granularity of the output images. The results for the neural network are shown below.

  
![](https://lh4.googleusercontent.com/BkFanKYcr37Xo7kp0bSs1tU5zKgs2xVLEm0adgnikCXHbWxNG2-IYAvmwhMl0ulmWuFSQXAvnxvL_eLFIsWwM6al2UwixejLUhskX4JKgTKp6-MNWJnyzNm98_yNWGdvJeRcU91A)  
  
  
  
![](https://lh4.googleusercontent.com/YvzyVO-4CZ6aLH45V41Khssvzt3--Nqr7OwHV5n1iXgBMJ_CjhdTnh0KfT7avVNEWKXBHJcCTgFrPZbyW6gbUw5k20l_JkWymjqwNg5zaGWuNz55PGoAwyPiyzzpS0GCh7w6enQK)  
  
  
  
  
  
  
  
  
  
  

The training performance for this model is at ceiling while the test performance for prc is at about .25 TP rate. The neural network TP rate is at about .425. Both show 0 or nearly 0 FP responses.

  
  
  
  
  
  
  

I wanted to continue to explore the granularity of the output images with the hog method by changing the values of the pixels per cell. Unfortunately I started running into this error and I had no clue what to do about it. ![](https://lh3.googleusercontent.com/QX1ZiorXKpJqRWlZfX9hIlGn64wtgdyL0hKPXFH2VJpQxrzDbse5xQSpX0SJIxCUTwNca_t08fVyRF0XQEkWLgD3ckY2mWeQCPezJLBQuUddItdfnHK-GWNoUaGbIq5fFa0hXHjP)

and : ![](https://lh3.googleusercontent.com/exN17fvTZsHPLRbk75Kx9pbtfUL7hs1yL_r3OWJBsSI7gplcNofkWL1J53DikF2iPIOOIh3AHj4KI5hYRfWsugFujIfZ2Y12EHxVGF8OdMhwWlwyMePmjm7htmtrIZn3x6tvjes1)

  

From here I redownloaded the whole plane images first full iteration and worked with changing sigma values for the default Canny Edge Detector.

  

1.  Sigma = 3:
    

  

Perceptron results:

![](https://lh3.googleusercontent.com/18GRDUQj6UsvC1ANs66__fRDxpbAyjZ8R-VOjncT8eiMh9RpNJJICbjeIOL0UNExs_5zakBd8rJqQaGY7S4lRHGv25b4iMCdrK7p8JOI0efWPxFDFuLNJZSNa9909ZCh9Exi7zw0)

Neural Network results:

  

![](https://lh5.googleusercontent.com/pALbnKD5R7U01mEC9NKQqyIWJDwWkQeuMzdLYvVUEugPmGtI6VZB5vnlYNLuWlbsEwyQY1Tm5KJbkTWwdolr8-ahxEyG1g5c7IIk_nTuHMIjFriMVLOKbWBnFiHvLoxlAtCMC6Pe)

  
![](https://lh3.googleusercontent.com/_2zikfM0QJceYyb8kQAVDRQ118itdVXZ9ciEzPDXoAnuApgR8xd1ZGTkQqxlbS2-3p2obZ0ACfs6bNojywedEeoqquuDcfP2cQk5jlTNX1DNvYMERDoljGZ0MLt9DnJknZraokPu)

A sigma value of 3 seemed to bring both the test and train performance of the two models down.

  
  
  
  
  
  
  
  
  

2.  Sigma = 1:
    

  

Perceptron results:

![](https://lh4.googleusercontent.com/skAz1MdWquSz-Ap2j9NUR8jI0z9lK3cpe5Z0DyFP1zFV1bKJrp4_SK9aMIcIQVeHopDY3Y4B_7YrhYpKgdVxDc92McnT9Qx2YYXVmMhMV06HCzCCfULBemDUknURgjtSUFOj8RJi)

Neural Network results:

  
![](https://lh3.googleusercontent.com/-BJyV5hR3bjvL7qGLEhtJJa1p_ysxjuJ7Kn8bfh7G9VwszYZGRlDqQyAviz5K9szjEOL-8fPaVjTopHRlyfQtFkTh8kB6DUNH8jFeGdcdnhKaUG2HWaYJo9oMVvNoN_P-ukzjFFU)  
  
  
  
  
  
![](https://lh3.googleusercontent.com/Hmhh7gYT40xmQVYCdKWG22CfWffABaOyR-zbzgC5OzbjWXp3C_0XxJPy63_H03P4i0Df7MSBlLE5mnUPdCbooKOFjgMtNEMkfKXPuMWe-uR372tqwsfnrzcstttdByxYdccrn9in)

A sigma value of 1 appeared to have a similar train performance for the perceptron as a sigma value of 3. The neural network model appeared to have a much higher training performance here. Both the test sets had a greatly improved TP rate as compared to the sigma value of 3.

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

3.  Sigma = .1:
    

  

Perceptron results:![](https://lh5.googleusercontent.com/y-JMN0oU51qEf8xoEwvSG3JT39QpcTZOvLtkPvdfU4wYDPJalw69qX7E8zrGP0IKlUM71j2PK7zXDWxl5MtyTZY5XIGYfZ-LFhAgmQCYDHZHsM4KiRytLJdUZkDU8Bq_BFrClfVy)

  
  
  
  
  

Neural Network results:

![](https://lh4.googleusercontent.com/TxWT9sYHeAGPEb2yFDJc6J6jJH_9kgL9TjiRHA0ggl7nChSztpYxOE0zGXkH0cpmnj72toJZjBA8op1lsfFgtLMPTzJtpuR0O4fJFphI_HAQppxPmXkXIof9kk3NEkLKgvZmE_-V)![](https://lh5.googleusercontent.com/6C2jXV8mXA9NT2d8zBpZAmY_KpMyUaEwu7-VukJ3y1xWM9F0FlA2_13G2YEG21Jp5fw0mokW-VKMXXaLT-77IOGRG6W85oFJ66HpfPVsfEmAl34nFWbeOn2oPhTBn5hgI9kq0VX1)

The sigma value of .1 increased the perceptron training performance to about .93 while not changing the neural network performance (as compared to sigma=1). Interestingly enough the perceptron test performance was decreased slightly. The neural network model took a large hit in TP performance moving from about .6 to .38 (compared to sigma=1).
