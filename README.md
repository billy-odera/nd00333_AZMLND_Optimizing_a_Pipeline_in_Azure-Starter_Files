# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
This dataset contains data about bank marketing. We seek to predict if a client will subscribe to a term deposit.
The best performing model was obtained through AutoML - <strong> VotingEnsemble </strong> with accuracy of <b>0.916</b></p>

## Scikit-learn Pipeline
<ol>
  <li>Setup Training Script
    <ul>
      <li> Import data </li>
      <li> Cleaning of data </li>
      <li> Splitting data into train/test </li>
      <li> Using scikit-learn logistic regression model for classification </li>
    </ul>
  </li><br>
  <li> Configuration of Hyperdrive
    <ul>
      <li> Selection of parameter sampler </li>
      <li> Selection of primary metric </li>
      <li> Selection of early termination policy </li>
      <li> Selection of estimator (SKLearn) </li>
      <li> Allocation of resources </li>
    </ul>
  </li><br>  
  <li>Save the trained optimized model</li>
</ol>

**Parameter Sampler**
<p>The parameter sampler I chose was <i>RandomParameterSampling</i> because it supports both discrete and continuous hyperparameters.</p>

**Early Stopping Policy**
<p> The early stopping policy I chose was <i>BanditPolicy</i> because it is based on slack factor and evaluation interval..</p>

## AutoML
<ol>
  <li> Import data</li>
  <li> Cleaning of data</li>
  <li> Splitting of data into train and test data </li>
  <li> Configuration of AutoML </li>
  <li> Save the best model generated </li>
</ol>

## Pipeline comparison
<p>Both approaches follow the same data processing steps,the difference is in their configuration details. In approach 1,we use hyperdrive tool to find optimal hyperparametets while in approach 2,different models are automatically generated with their own optimal hyperparameter values.<p>
  
**Pipeline for both approaches**
<img src = 'https://github.com/billy-odera/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files/blob/master/explanation3.jpg'>

**Results for AutoML**
<img src = 'https://github.com/billy-odera/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files/blob/master/explanation1.jpg'>

**Results for best model**
<img src = 'https://github.com/billy-odera/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files/blob/master/explanation2.jpg'>

## Future work
<ol>
  <li> work on this error WARNING:azureml.train.sklearn:'SKLearn' estimator is deprecate</li>
  <li> feature engineering</li>
</ol>
## Proof of cluster clean up
<img src = 'https://github.com/billy-odera/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files/blob/master/explanation4.jpg'>
<img src = 'https://github.com/billy-odera/nd00333_AZMLND_Optimizing_a_Pipeline_in_Azure-Starter_Files/blob/master/explanation5.jpg'>
