---
title: ":paperclip: Income Prediction Project"
layout: post
date: 2018-12-01 22:10
tag: [R, Docker, Make, Machine Learning, UBC MDS]
image: https://mani-kohli.github.io/assets/images/income5.png
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "Income Prediction."
category: project
author: johndoe
externalLink: false
---

#### UBC MDS Project
## Income Prediction

### Introduction
There are huge disparities in salary amongst the population today. Why does someone receive a higher salary than the next person? There could be many, many factors as to why.  How do we narrow down these factors?  One approach would be to analyze collected data from censuses which would give us pre-defined attributes, including salaries.

The research proposal for this project is to determine what the strongest predictors (attributes) would be to determine a salary greater than $50,000.  

The goal is to build a model on census data for a specific year with the hopes that it could be applied on more recent census data as well.


### Dataset
The public data set for the project is https://archive.ics.uci.edu/ml/datasets/Adult from UCI machine learning repository. The data used for this project is from the 1994 US Census Database.

**Dataset Attributes**
"age", "workclass", "fnlwgt", "education", "educationNum", "married", "occupation", "relationship", "race",  "sex", "capitalGain", "capitalLoss", "hrPerWeek", "nativeCountry", "income"

Script to load the dataset: [R script](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/master/src)  
Dataset file: [Data](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/master/data)  


### Research Question
Our research proposal for this project is to determine, *what are the strongest attributes to determine a salary greater than $50,000?* This will be a predictive question.

### Plan

**WorkFlow for our project:**

![WorkFlow](/assets/images/process.png)

**Fig 1: Project workflow**
{: style="color:#000000; font-size: 90%; text-align: center;"}   


1. load the dataset into R
2. explore the dataset
3. data wrangling to clean and prepare the data according to the research project
4. divide the dataset into training and testing
5. use a decision tree algorithm on the training set
6. apply the resulting model to the testing set

A decision tree model was chosen in order to predict which specific features were used to classify the target value. In addition, this approach allowed for the prediction of the rules which helped predict the target variable.


### Summary
* compare the testing statistics to the training statistics (ex. accuracy) in a table or visualization such as a tree
* return to the decision trees to determine the strongest attributes leading to a salary greater than $50,000.  


### Final Report
Our final report is [here](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/blob/master/doc/final_report.md).


### Scripts
Our scripts can be found [here](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/master/src).  
For usage of these scripts, please reference the *Usage* description in the comment section of each script. These scripts should be run under the root directory of our project. To run each script, copy the code after *Example:*, in the comment section at the beginning of each script, into terminal.


### Usage

### Method 1 Run the analysis using shell script

Each script should be run under the root directory of this project.

In a command line, run the following code to load tidy data:

<pre><code>Rscript src/script_01_load_tidy_data.R htt<span>ps:</span>//archive.ics.uci<span>.e</span>du/ml/machine-learning-databases/adult/adult.data data/tidy_data_viz.csv data/tidy_data_ml.csv</code></pre>


Run the following code to generate visualizations:

<pre><code>Rscript src/script_02_visualizations.R data/tidy_data_viz.csv results/data_viz_01.png results/data_viz_02.png results/data_viz_03.png</code></pre>


Run the following code to do machine learning and create summary tables:

<pre><code>python src/script_03_machine_learning.py data/tidy_data_ml.csv results/depth_summary.csv results/feature_summary.csv</code></pre>


Run the following code to create summary graphs:

<pre><code>Rscript src/script_04_create_summary_graph.R results/depth_summary.csv results/feature_summary.csv results/depth_graph.png results/feature_graph.png</code></pre>


### Method 2 Run the analysis using make

The makefile should be run under the root directory of this project.

In a command line, run the following code to run the anlysis:

<pre><code>make all</code></pre>

Run the following code to have a fresh start:

<pre><code>make clean</code></pre>


### Method 3 Run the analysis using docker

Install Docker

Download and clone this repository

Run the following code in terminal to download the Docker image:
<pre><code>docker pull olivialin/dsci_522_income_prediction</code></pre>

Use the command line to navigate to the root of this repo

Type the following code into terminal to run the analysis:  
<pre><code>docker run --rm -e PASSWORD=income -v <span><</span>ABSOLUTE PATH OF REPO<span>></span>:/home/income incomeprediction:2.2 make -C 'home/income' all</code></pre>

If you would like a fresh start, type the following:  
<pre><code>docker run --rm -e PASSWORD=income -v <span><</span>ABSOLUTE PATH OF REPO<span>></span>:/home/income incomeprediction:2.2 make -C 'home/income' clean</code></pre>


### Dependencies

**R Packages:**

- tidyverse (v1.2.1)
- ggplot2 (v3.0.0)
- GGally (v1.4.0)

**Python Packages:**
- pandas (v0.23.0)
- sklearn (v0.19.1)
- matplotlib (v2.2.2)
- argparse (v3.2)


### Release Versions  

* [Version 0.0](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v0.0)
* [Version 1.0.1](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v1.0.1)
* [Version 2.0.0](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v.2.0.0)
* [Version 2.1.0](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v.2.1.0)
* [Version 2.2.0](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v.2.2.0)
* [Version 3.0.0](https://github.com/UBC-MDS/DSCI_522_Income_Prediction/tree/v.3.0.0)


[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/


### Team Members

* [Mani Kohli](https://github.com/mani-kohli)
* [Olivia Lin](https://github.com/olivia-lin)


### Full Project Repository
[Income Prediction](https://github.com/mani-kohli/DSCI_522_Income_Prediction)
