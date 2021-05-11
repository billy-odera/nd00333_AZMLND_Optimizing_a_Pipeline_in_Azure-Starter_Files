# Optimizing an ML Pipeline in Azure

## Overview
This project is part of the Udacity Azure ML Nanodegree.
In this project, we build and optimize an Azure ML pipeline using the Python SDK and a provided Scikit-learn model.
This model is then compared to an Azure AutoML run.

## Summary
This dataset contains data about bank marketing. We seek to predict if a client will subscribe a term deposit (variable 'y').

The best performing model was obtained through AutoML - <strong> VotingEnsemble </strong> with accuracy of <b>0.916</b></p>

## Scikit-learn Pipeline
<ol>
  <li>Setup Training Script
    <ul>
      <li> Import data using <i>TabularDatasetFactory</i> </li>
      <li> Cleaning of data -  handling NULL values, one-hot encoding of categorical features and preprocessing of date </li>
      <li> Splitting of data into train and test data </li>
      <li> Using scikit-learn logistic regression model for classification </li>
    </ul>
  </li><br>
  <li>Create SKLearn Estimator for training the model selected (logistic regression) by passing the training script and later the estimator is passed to the hyperdrive                 configuration</li><br>
  <li> Configuration of Hyperdrive
    <ul>
      <li> Selection of parameter sampler </li>
      <li> Selection of primary metric </li>
      <li> Selection of early termination policy </li>
      <li> Selection of estimator (SKLearn) </li>
      <li> Allocation of resources </li>
      <li> Other configuration details </li>
    </ul>
  </li><br>  
  <li>Save the trained optimized model</li>
</ol>

**parameter sampler choosen**
<p>The parameter sampler I chose was <i>RandomParameterSampling</i> because it supports both discrete and continuous hyperparameters.</p>

**early stopping policy choosen?**
<p> The early stopping policy I chose was <i>BanditPolicy</i> because it is based on slack factor and evaluation interval..</p>

## AutoML
<ol>
  <li> Import data using</li>
  <li> Cleaning of data</li>
  <li> Splitting of data into train and test data </li>
  <li> Configuration of AutoML </li>
  <li> Save the best model generated </li>
</ol>

## Pipeline comparison
<p>Both approaches follow the same data processing steps,the difference is in their configuration details. In approach 1,we use hyperdrive tool to find optimal hyperparametets while in approach 2,different models are automatically generated with their own optimal hyperparameter values.<p>

## Future work
**What are some areas of improvement for future experiments? Why might these improvements help the model?**

## Proof of cluster clean up
**If you did not delete your compute cluster in the code, please complete this section. Otherwise, delete this section.**
**Image of cluster marked for deletion**
