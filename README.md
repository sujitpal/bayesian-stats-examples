# bayesian-stats-examples

Python versions of things taught in the Bayesian Statistics courses on Coursera.

* [Bayesian Statistics: From Concept to Data Analysis](https://www.coursera.org/learn/bayesian-statistics) - taught by Herbert Lee from the University of California, Santa Cruz. Python notebooks for analogs of things taught in this class are in the folder `concept-to-data-analysis`.
* [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics) - taught by Matthew Heiner, also from University of California, Santa Cruz. Python notebooks for models taught in this class are in the folder `techniques-and-models`.

I decided to explore the subject further using the book [Bayesian Analysis with Python, 2nd Edition](https://www.packtpub.com/big-data-and-business-intelligence/bayesian-analysis-python-second-edition) by Osvaldo Martin, one of the contributors to the PyMC3 project. The book claims to be introductory, but goes further than the courses above. The `bayesian-analysis-exercises` folder contain my answers to the exercises in the chapters. You will need to `git clone` the book's code repository at the top level of this project (`git clone https://github.com/aloctavodia/BAP.git`) to get access to the data files used by the book, and referenced from my notebooks.

## Python packages used

* numpy
* scipy (for scipy.stats)
* statsmodels
* PyMC3
* matplotlib

## General impressions

* Course uses JAGS, PyMC3 has more natural syntax 
* statsmodels.OLS is not as flexible compared to R's lm().

## Caution

* Meant for understanding how to apply Python libraries to problems solved with R in the course.
* If used to answer quizzes, can lead to disappointment since answers don't always match exactly.

