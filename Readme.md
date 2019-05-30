# Sparkify project

### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [Files Description](#files)
4. [Result](#Result)
5. [Licensing, Authors, and Acknowledgements](#licensing)

## Installation <a name="installation"></a>

This project uses the following software and Python libraries:

Python

Spark

Pyspark

pandas

Matplotlib

Seaborn

You will also need to have software installed to run and execute a Jupyter Notebook.

If you do not have Python installed yet, it is highly recommended that you install the Anaconda distribution of Python, which already has the above packages and more included. And for Spark, you can do this using AWS or IBM Cloud.

## Project Motivation<a name="motivation"></a>

This is udacity's capstone project, using spark to analyze user behavior data from music app Sparkify.

Sparkify is a music app, this dataset contains two months of sparkify user behavior log. The log contains some basic information about the user as well as information about a single action. A user can contain many entries. In the data, a part of the user is churned, through the cancellation of the account behavior can be distinguished.

## Files Description<a name="files"></a>

**Sprakify .ipynb** Main file of the project, it demonstrates the process of using pyspark to explore the data and build the model.

## Result

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

## Licensing, Authors, Acknowledgements<a name="licensing"></a>

Must give credit to Udacity for the project.
