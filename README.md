# Investigating Medals as the Olympic Games using Featuretools
##### [Goals](##goals) | [Installation](##installation) | [Featuretools Basics](##featuretools basics: FeaturetoolsPredictiveModelingSimple.ipynb)
| [Baselines using Featuretools](##Baselines using Featuretools: BaselineSolutions.ipynb)
| [Generating Labels](##[Coming soon] Generating Labels (Prediction Engineering))
| [Deeper Exploration](#[Coming soon] Deeper Exploration)
| [Linking Multiple Datasets](#[Coming soon] Linking Multiple Datasets)
| [Performance Evaluation](#[Coming soon] Performance Evaluation)
| [Constrained Feature Exploration](#[Coming soon] Constrained Feature Exploration)

[Featuretools](https://www.featuretools.com/) is a framework to perform automated feature engineering. It excels at transforming transactional and relational datasets into feature matrices for machine learning. This demo uses Featuretools to investigate the medals won by each country at each historical Olympic Games (dataset pulled from [Kaggle](kaggle.com/the-guardian/olympic-games)).

## Goals
The various notebooks provided in this repo show how Featuretools:
 * Simplifies the code needed to produce both simple and complex predictive models,
 * Exhaustively generates and computes tens of thousands of features, while avoiding label-leakage problems that crop up easily when writing feature computations from scratch
 * Allows for innovative data science workflows not possible using lower-level libaries and techniques
 * Lets us easily combine separate datasets into joint models and investigate interactions between these datasets

## Installation

```sh
pip install -r requirements.txt
```

You will also need these datasets.
The dataset for notebooks 1, 2, and 3 is found <a href=https://www.kaggle.com/the-guardian/data>here</a>.

Notebooks 4, 5 and 6 will require the following additional datasets:
    * Economic data <a href=https://www.kaggle.com/worldbank/world-development-indicators>Economic Data</a>
    * Economic data <a href=https://unstats.un.org/unsd/methodology/m49/overview/>Region Data</a>


## Featuretools Basics: FeaturetoolsPredictiveModelingSimple.ipynb

In this notebook, I'll explain how to use out-of-the-box methods from Featuretools to transform the raw Olympics dataset into a machine-learning-ready feature matrix.
Along the way, we'll build some machine learning models, explore which features were the most predictive, and make some interesting predictions.

## Baselines using Featuretools: BaselineSolutions.ipynb

Machine learning performance scores should never be taken at face value.
To have any merit, they must be compared against a simple baseline model to see how much improvement they produced.
In this notebook, we'll examine several baseline solutions, and see how much simpler the code to produce these baselines is when using Featuretools as compared to lower-level libraries.

## [Coming soon] Generating Labels (Prediction Engineering)

I'll show a way to generate the labels for supervised machine learning we use throughout this demo.
Note that this is a non-trivial problem in general, as we need to scan through the time-varying components of a dataset and choose windows of time in which we compute a function that then determines a label.
This process is called *Prediction Engineering*, and is a core component of the paid platform of Feature Labs (the company I work for that maintains Featuretools). The open-source Featuretools does not come with built-in ways to do prediction engineering.

These labels define our goal, in this case to predict the number of medals a country will win at the next Olympics.
There are many other possible goals we could have had in mind. We could have built models to predict the number of medals an athlete will win over his or her career,
or the location of the next Olympic Games, or the sport with the highest number of competing athletes.
We stick with a single problem, which lends itself to enough complexity to make for an interesting demo. A good way to sharpen your data science skills would be to try out one of these other problems yourself.

## [Coming soon] Deeper Exploration

Now that we understand the dataset and the basics of Featuretools, we'll take a deeper dive into some more advanced aspects of Featuretools.
Through this process we'll examine where our prediction model breaks down, as well as seek to understand the dataset from a predictive perspective.

## [Coming soon] Linking Multiple Datasets

Linking several independently-sourced datasets is an interesting component of the data science process that Featuretools can help with.
In this notebook we'll show how to add in economic and region information about each country to our dataset, and easily rerun our pipeline with this new data.

## [Coming soon] Performance Evaluation

At this point we've seen several different approaches to understanding the data.
In this notebook, we'll examine some unique feature selection techniques that Featuretools makes possible, as well as make some comparisons between many different models by examining their predictive power.

## [Coming soon] Constrained Feature Exploration

The prediction problem we've defined is fairly easy to solve. What this means is that we can experiment with limited sets of features, which each hold predictive power independently from each other.
Using a limited feature set allows us to make good comparisons between different types of features.
For instance, we'll investigate how using only economic features shows us which economic indicators are most important (at least for determining the outcome of the Olympics) at different times in history.