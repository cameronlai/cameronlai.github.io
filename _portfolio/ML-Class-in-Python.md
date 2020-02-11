---
title:  "ML Class In Python"
last_modified_at: 2016-02-17T15:31:00+08:00
---
Machine Learning Course Exercise in Python 

[Github](https://github.com/cameronlai/ml-class-python)

I have recently taken [Andrew Ng's machine learning course on Coursera](https://www.coursera.org/learn/machine-learning), which is very popular. I have found the course very interesting and presents many machine learning concepts in a very clear manner. The choice of programming language in the course is MATLAB / Octave. These languages have a simple syntax and are useful in prototyping machine learning concepts. However, in real life software development, these languages are seldom used and this project has transformed the coursework in the [Python language](https://www.python.org/). This hopes to give an example in how to implement algorithms in a different language. Moreover, the project also illustrates how to use [scikit learn](http://scikit-learn.org/), one of the most popular Python machine learning libraries, to achieve the same goal with the same data set. In my repository, there are some places where it can be perfected and you are more than welcome to submit a pull request or discuss in either [Github issues](https://github.com/cameronlai/ml-class-python/issues) or here. Some of the problems I encountered are listed below.

1.  [Issue #1](https://github.com/cameronlai/ml-class-python/issues/1) - In exercise 5, the graphs generated using scikit library are quite different from the Python / Octave implementation. I haven't been able to found the correct settings to make scikit learn run as the original code yet.
2.  [Issue #2](https://github.com/cameronlai/ml-class-python/issues/2) - In exercise 7, the PCA decomposition relies on the numpy.linalg.svd function. However, the function returns a different set of values than Octave and it can be seen in plot than the two components are not perpendicular to each other. I suspect that there is some error in the low level library versions.

Hope you can learn something from the code examples! 

![alt text](http://cameronlai.com/wp-content/uploads/2016/02/ml-class-in-python-ex7-bird-image-compression.jpeg)
*ML Class in Python ex7 bird image compression*