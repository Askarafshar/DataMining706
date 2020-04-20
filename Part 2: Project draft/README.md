<h3> SIMPLIFIEd TO ACCOUNT FOR COVID-19 CONSTRAINTS 3/21</h3>

Some parts moved to optional - if you need an extension, just ask!

Your project draft should build on and extend your earlier proposal.  It is essentially a rough draft of your final report.

Length 8-10 new pages (in addition to the revised proposal text)

First, include all text from the plan having addressed any changes requested by the peer reviewer or instructor.

Then, add the following sections:

Analytic Strategy: Very clearly explain "What is the thing that your model will predict?"

Training data:  Please describe what % of your total available data you have used for training.  If you used stratified sampling to ensure inclusion of any minority class data in your training sample, please describe. If you employed random sampling to create your training sample, explain how you generated a random sample.

Training data and Baseline:  Choose at least one baseline method (e.g. Zero R, One R) covered by the class materials and apply it to your training data.   Explain the results including measures of predictive performance and false positives/negatives from the confusion matrix.  Include screenshots of the WEKA output with explanations.

Main Model Approach (linear, tree, cluster).  Develop a model using one of the three main approaches addressed in class (linear regression, tree, cluster) that best fits your data and what you want to predict.  (Note you may need to convert categorical data into numbers to do so)  Note I expect most folks will choose either linear regression OR tree approach for this report.

Model creation and tweaking with Training Data:  

Create ONE model based on default algorithm parameters  for your chosen approach (e.g., linear regression or tree for most people). Explain the results including measures of predictive performance and false positives/negatives from the confusion matrix if applicable.  Include screenshots of the WEKA output with explanations.  (creation of additional models moved to optional.  Comparison of models moved to optional)

Testing Data:

Please describe what % of your total available data you have kept for this testing.  Take your model from above and apply it to your testing data.  Explain the results for including measures of predictive performance and false positives/negatives from the confusion matrix if applicable.  Include screenshots of the WEKA output with explanations. 

Reflection:  Analysis of test (short)

Explain how the test results are different from, or similar to the training results.  Try to explain any differences you see.  How is it different from the baseline?

Reflection: Next step (short)

Based on what you tried, what would be your next step in model development?  Just describe, don't do.  For example would you like to try a different main model approach (e.g., cluster instead of linear).  Do you want to improve your data set in some way?

 

Parts moved to optional:

(Optional) Variations: You should create additional variations of your model for three total models.  You can change either (a) something about your data (e.g., add or drop a variable) or (b) change the default settings of your chosen algorithm.   For each of the additional two models ,explain what changes you made in the algorithm parameters or your data. 

Create a table to compare the results for the new 3 total variations including measures of predictive performance and false positives/negatives from the confusion matrix if applicable.  Include screenshots of the WEKA output with explanations.

(Optional) Analysis of Training Data:

Create a table to compare your baseline results with the results from the 3 submodels.  Describe which might be said to have the best performance in terms of (a)  % predictions correct (b) false positives/false negatives (if applicable) (c) any other quality measure.  Which set of algorithm parameters seem best and why? or is the baseline better?
