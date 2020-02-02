# Delay-Flight-Prediction
The project is all about prediction of flight delay
In this notebook, I develop a model aimed at predicting flight delays at take-off. The purpose is not to obtain the best possible prediction but rather to emphasize on the various steps needed to build such a model. Along this path, I then put in evidence some basic but important concepts. Among then, I comment on the importance of the separation of the dataset during the traning stage and how cross-validation helps in determing accurate model parameters. I show how to build linear and polynomial models for univariate or multivariate regressions and also, I give some insight on the reason why regularisation helps us in developing models that generalize well.

From a technical point of view, the main aspects of python covered throughout the notebook are:

visualization: matplolib, seaborn, basemap
data manipulation: pandas, numpy
modeling: sklearn, scipy
class definition: regression, figures
During the EDA, I intended to create good quality figures from which the information would be easily accessible at a first glance. An important aspect of the data scientist job consists in divulgating its findings to people who do not necessarily have knowledge in the technical aspects data scientists master. Graphics are surely the most powerful tool to achieve that goal, and mastering visualization techniques thus seems important.

Also, as soon as an action is repeated (mostly at identical) a few times, I tend to write classes or functions and eventually embed them in loops. Doing so is sometimes longer than a simple copy-paste-edit process but, on the one hand, this improves the readibility of the code and most importantly, this reduces the number of lines of code (and so, the number of opportunities to introduce mistakes !!). In the current notebook, I defined classes in the modeling part in order to perform regressions. I also defined a class to wrap the making of figures. This allows to create stylish figures, by tuning the matplotlib parameters, that can be subsequently re-used thanks to that template. I feel that this could be useful to create nice looking graphics and then use them extensively once you are satisfied with the tuning. Moreover, this helps to keep some homogeneity in your plots.

Acknowledgement: many thanks to J. Abécassis for the advices and help provided during the writing of this notebook

This notebook is composed of three parts: cleaning (section 1), exploration (section 2-5) and modeling (section 6).

Preamble: overview of the dataset

1. Cleaning
  1.1 Dates and times
  1.2 Filling factor
  
2. Comparing airlines
  2.1 Basic statistical description of airlines
  2.2 Delays distribution: establishing the ranking of airlines

3. Delays: take-off or landing ?

4. Relation between the origin airport and delays
  4.1 Geographical area covered by airlines
  4.2 How the origin airport impact delays
  4.3 Flights with usual delays ?

5. Temporal variability of delays

6. Predicting flight delays
  6.1 Model nº1: one airline, one airport
    6.1.1 Pitfalls
    6.1.2 Polynomial degree: splitting the dataset
    6.1.3 Model test: prediction of end-January delays
  6.2 Model nº2: one airline, all airports
    6.2.1 Linear regression
    6.2.2 Polynomial regression
    6.2.3 Setting the free parameters
    6.2.4 Model test: prediction of end-January delays
  6.3 Model nº3: Accounting for destinations
    6.3.1 Choice of the free parameters
    6.3.2 Model test: prediction of end-January delays

Conclusion

