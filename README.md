# Application-of-Bootstrap-samples-in-Random-Forest

## Credits: https://www.appliedaicourse.com/ 

## Summary:
 - Here we will see the intuition of bagging in Decision trees and implementation of random forest from scratch and also we will see how to calculate the confidence intervals.
 - Random forest = Decision trees + Bagging.
 - Here we are using "Boston house prices" data set. 
 
 We already know about decision tree. So here we will see what is bagging and intution about random forest.
 
 # Bagging(Bootstaped aggregation):
  - Bagging is one of the "ensembling" technique. In ensembling we can group multiple models together and we will take majority vote on top of all models (for classification) and for regression we will take mean or median on top of all models ouput. Here we can call the models as "Base models".
  - So here we will use "Decision trees" as our base models. How many base models that we want to use is our hyper paramter.
  - But here we are not training the models on entire data. We will perform row sampling and column sampling.
  - In row sampling we will take the certain no.of rows and in column sampling we will take certain no.of columns. By using this data we will train our base models. For each base model we will take different samples of data.
  - Why we are doing this? To reduce the variance and to build strong models.
  - High variance is nothing but small change in data will cause large affects on predictions of models. Since we are doing the row sampling each model will see different sub-sets of data. So we will get our final models with low variance.
  - Then why column sampling? Since we are using base models (decision trees with depth = None). That means all of our base models are high variance models. If we are using same features for all this high variance models then the reault we will get is a high variance model. So to avois that we are doing column sampling.
  
 
 # Note:
  - Row sampling is sampling with repetition
  - column sampling is sampling without repetition
  
  ## Here one more term that we used is "Out of bag":
   - out of bag is nothing but the points that are not used for the model training. ex: Assume these are indexes of train data [1,2,3,4,5]. By using row sampling we got [1,2,4,4,2]. For this model out of bag points are [3,5]
   
   
  ## Regarding confidence interval:
   - First we will answer this question. What is meant by 95% confidence interval ?
   - 95% confidence interval does not eaxctly means that 95% of data lies in the gievn boundary. The exact meaning of that is if you are performing an experiment of taking samples from population and each sample have finite no.of observations and your keep on taking samples. Now 95% of times your population mean will fall in the confidence intervals calculated using the samples
   - To calculate the confidence interval of population mean we have some methods.
   - Here we are assuming that we don't know the population standard deviation, 
now we will take the sample with finite no.of observations from the population and we will calculate the mean and standard deviation of the sample and we will assume the standard deviation of the population is same as the standard deviation of sample. So now the standard deviation of sample  = (standard deviation of sample)/sqrt(n). 
where n = no. of observations in the sample.
 - 95% confidence interval = [sample_mean-2**standard deviation of sample ,  sample_mean+2**standard deviation of sample]
