---
title: "Why is Random Forest better than Decision Trees?"
seoTitle: "Random Forest"
datePublished: Sun Dec 26 2021 13:00:16 GMT+0000 (Coordinated Universal Time)
cuid: ckxn9eklz06bf71s12puv8p78
slug: why-is-random-forest-better-than-decision-trees
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1640523650186/tK-W9-Ud-.jpeg
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1640523531272/mO_cjNRLD.jpeg
tags: statistics, algorithms, machine-learning, ml

---

### Prerequisites: Familiarity with Decision Trees.

Ok, so let us consider the Dataset given below.


![Dataset.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640517746058/9OnaWlLWb.png)

A Decision Tree fitting this dataset would look like something like this.


![tree.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640517889901/A_nD6Y-1i.png)

All good, right? But what if we encounter a change in the original data set? Would the Decision Tree still work as expected? Would it still generalize well to the changed Dataset and continue producing results in accordance with its earlier accuracy? 

The answer is No.

Let's see by changing the original dataset.


![changed.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640518196488/mTJ-PqS_W.png)


If we just change these two entries to no instead of yes. The Decision tree would have a 50% chance of predicting the correct result. And this is just in the Training Set. We can safely say that any change in the original Data reflects hugely on the performance of the Decision Tree generalized on the unchanged Data. So what do we do?

We used an ensemble technique called Random Forest.

## **Question Alert!**

What is an ensemble technique in Machine Learning?

Ensemble methods is a machine learning technique that combines several base models in order to produce one optimal predictive model. Meaning *Apes Together Strong*.

So, what actually happens in a Random Forest? Let's see.

## **Processes in Random Forests**


- Bootstrapping

- Random Feature Selection

- Simultaneous Model Training

- Aggregation


### Bootstrapping

We take rows from the dataset with replacement. We take as many rows as were present in the original dataset. This means that there may be repetitions in the new bootstrapped dataset. We make a number of these new datasets (a hyperparameter). 


![bootstrapping.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640520876145/jqfHzaMT7.png)

Notice that in the picture above, There are (maybe) repetitions in each bootstrapped dataset.

### Random Feature Selection 

We randomly select a few (another hyperparameter) columns (features) for each dataset.

For example First two features for the first dataset, the Last two for the second...

At this point, we have various individual Datasets. What to do next? Train a Decision Tree model on each of those.

### Simultaneous Model Training

Build Trees for all datasets. This brings along all the hyperparameters associated with each Decision Tree.

We now have completed all the parts in Random Forest. The next question is...


## How does it all come along?


![RF.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1640521372046/jRb39Ac7D.png)

Simple! The steps are


1. Bootstrap rows

2. Select Random Features

3. Train Decision Trees on each

4. Make predictions using all models. For **Classification** take the majority vote and for **Regression** take an average or weighted average or mode (whatever gives the best result).



## FAQ


### Q1. Why *Random*?

Ans. Due to Bootstrapping and Random Feature Selection which randomizes the datasets.

### Q2. Why *Forest*?

Ans. Because there are more than 1 Decision Trees. Trees. Get it? :D

### Q3. Why Bootstrap and Random Feature Selection?

Ans. Bootstrap ensures that we don't use the same data every time. So our model(s) is(are) less sensitive to the original dataset. Random Feature Selection on the other hand reduces the correlation between trees. If Random Feature Selection was not used all trees would produce very similar results and increase overall variance. Some trees would give bad results and others bad results in the opposite way thus balancing it out.

### Q4. What's the ideal size of the feature subset?

Ans. 2 values usually give the best result
        
- Log of the total number of features.

- Square root of the total number of features


## Note


1. High variance of Decision tree averages out to be low variance because

      - Each tree recognizes a few features.

      - We take majority or mean.
2. Change of Training Data will impact Random Forest much less than Decision Trees.


## Materials 

-  [My Notes on Random Forest](https://github.com/sbk2k1/ML-Notes/blob/master/MLTheories/SupervisedLearning/Regression/Ensemble%20Techniques/Bagging/Random%20Forest/Random%20Forest.pdf)

-  [Normalized Nerd video on Random Forest](https://www.youtube.com/watch?v=v6VJ2RO66Ag) 

## Links

-  [GitHub](https://github.com/sbk2k1)

-  [LinkedIn](https://www.linkedin.com/in/saptarshi-bhattacharya-b9346a203/) 


Cheers!
 

 













