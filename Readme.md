# SPARKIFY PROJECT

### TABLE OF CONTENTS

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [Files Description](#files)
4. [Result](#Result)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## INSTALLATION <a name="installation"></a>

This project uses the following software and Python libraries:

Python

Spark

Pyspark

pandas

Matplotlib

Seaborn

You will also need to have software installed to run and execute a Jupyter Notebook.

If you do not have Python installed yet, it is highly recommended that you install the Anaconda distribution of Python, which already has the above packages and more included. And for Spark, you can do this using AWS or IBM Cloud.

## PROJECT MOTIVATION<a name="motivation"></a>

This is udacity's capstone project, using spark to analyze user behavior data from music app Sparkify.

Sparkify is a music app, this dataset contains two months of sparkify user behavior log. The log contains some basic information about the user as well as information about a single action. A user can contain many entries. In the data, a part of the user is churned, through the cancellation of the account behavior can be distinguished.

## FILES DISCRIPTION<a name="files"></a>

**Sprakify .ipynb** Main file of the project, it demonstrates the process of using pyspark to explore the data and build the model.

## RESULT

According to the results of the model, it is the frequency of Thumbs Down that has the greatest impact. Churn users have more Thumbs Down. Naturally, users will leave if they are not satisfied.

The result is not ideal, the recall rate of the model is very low, even the recall rate of the tree model is 0. I decided to undersample the training data, balance the categories of the training set to increase the recall rate and improve f1.

There is a strange problem here. Training results through cross-validation is good, but testing with validation sets is very poor. Logistic regression for example, the training result F1 score is 0.75, and the test result F1 score is 0.4. After the use of undersampling, the training result drops to 0.67, and the test result is 0.55.

F1 result:
Training: 0.758073899263998
Testing: 0.4
​
Training with undersample: 0.6696185966538797
Testing with undersample: 0.5517241379310345
The best model is logistic regression. According to the results of the model, it is the frequency of Thumbs Down that has the greatest impact. Churn users have more Thumbs Down. Naturally, users will leave if they are not satisfied.

Besides, the frequency of downgrade pages is also a big factor. I think this is because users hate the downgrade prompt. Registration time is also a factor, the longer the registration time users will not leave.

I post a blog about the detail, you can find it [here](https://medium.com/@kriti_agrawal02/predicting-user-churn-with-pyspark-193c9a3eb00e).

## CONCLUSION
The problem - The high intensity of this project is because of the large amount of data, all of our data wrangling and model creating has to be done using Apache Spark. This adds another level of abstraction on top of the already well-established process, but it does enable us to work with bigger data than we would otherwise be able to. 
 
Approach - I decided to undersample the training data, balance the categories of the training set to increase the recall rate and improve f1.

Solution - Finding the best F1 score was the solution implied. I implemented Logistic regression for which the training result F1 score is 0.75, and the test result F1 score is 0.4. 
After the use of undersampling, the training result drops to 0.67, and the test result is 0.55.F1 result: Training: 0.758073899263998 Testing: 0.4 ​ Training with undersample: 0.6696185966538797 
Testing with undersample: 0.5517241379310345 The best model is logistic regression. 

## IMPROVEMENTS
HOW MODEL PIPELINEING CAN BE IMPROVED:
To achieve the optimal user experience, using more capable hardware and moving the text extraction process from the cloud to the device would be essential. This would reduce the processing time and give access to the outputs of all of the modules of the text extraction pipeline, which would, in turn, enable the following features:
1. User-guided reading (e.g. read big text first, or read the text the user is pointing at)
2. Better support for languages other than English
3. Output filtering (e.g. ignore text smaller than some adjustable threshold)
4. Passive text detection (auditory cue on text detection, perhaps with additional information encoded in the tone and volume)

The user experience could also be improved significantly by using MXNet, which is a deep learning library that is better optimized for mobile devices than TensorFlow. The speedup wouldn’t be enough for running text extraction on the device, but it would reduce the classification delay significantly. 

UNDERSAMPLING: HOW IT HELPED?
Dealing with imbalanced datasets in this project required strategies such as using classification algorithms or balancing classes in the training data (data preprocessing) before providing the data as input to the machine learning algorithm.Undersampling helped to balance class distribution by randomly eliminating majority class examples.This is done until the majority and minority class instances are balanced out.




## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Udacity for the project.
