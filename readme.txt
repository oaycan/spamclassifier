
--------------------------------------
ReadMe File - SpamFilter in Python
--------------------------------------

** Purpose of the Document **
-----------------------------
This readme file is prepared to explain how I designed my spam filter to classify the messages and provide details on my approach
and the decisions I have made throughout the design stage.

** General Explanation on the Approach and the Algorithm Selected **
--------------------------------------------------------------------
As we investigate the behaviour of the spam filter we can conclude that this requires binary classification.
Therefore, I have decided to implement Naive Bayes to produce a strategy for classifying the messages.

** Algorithm Test/Development Phase **
--------------------------------------
First of all, I have implemented my Naive Bayes algorithm with the guidance of mathematical representation of the problem.
I defined the probabilities that needs to be computed and created dedicated functions for each of them. Fist of all,
I selected my alpha as "1" and found out my accuracy relatively low. Afterwards, I decided to fine tune my alpha using
K-fold cross validation and eventually could increase my accuracy accordingly.

** General Structure of the Code ** 
-----------------------------------
My code is structured under a class called SpamClassifier which has two main and two inner functions as follows.
    
    * Main Function1: train *
    ------------------------
    This is the main function to train the Naive Bayes algorithm. Train function has two inner functions.

   	* Inner Function1: estimate_log_class_priors *
    	----------------------------------------------
    	Under this function we find the probabilities of class priors P(C=0)-class_priors_C0, P(C=1)-class_priors_C1
	and take their logarithms and return log_class_priors
	
    	* Inner Function2: estimate_log_class_conditional_likelihoods *
    	---------------------------------------------------------------
    	This function calculates the frequency of each message for each of the classes within the whole training set and
	create an array for each class, that includes the probabilities of each keyword drawn from a bag of words and 
	concatenate them into one array(theta) and return it

    * Main Function2: predict *
    ---------------------------
    In this function, using the information returning from the function above we make the class predictions of n_test_samples
    

** K-Fold Cross validation **
-----------------------------
As mentioned above, as a separate tool I also used k-fold cross validation technique in order to find the optimum hyper-parameter
"alpha" value for Naive Bayes, and used this alpha value (236) to train Naive Bayes algorithm for the best accuracy.
