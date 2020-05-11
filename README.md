# bayesian-stats-examples

Python versions of things taught in the Bayesian Statistics courses on Coursera.

* [Bayesian Statistics: From Concept to Data Analysis](https://www.coursera.org/learn/bayesian-statistics) - taught by Herbert Lee from the University of California, Santa Cruz. Python notebooks for analogs of things taught in this class are in the folder `concept-to-data-analysis`.
* [Bayesian Statistics: Techniques and Models](https://www.coursera.org/learn/mcmc-bayesian-statistics) - taught by Matthew Heiner, also from University of California, Santa Cruz. Python notebooks for models taught in this class are in the folder `techniques-and-models`.

I decided to explore the subject further using the book [Bayesian Analysis with Python, 2nd Edition](https://www.packtpub.com/big-data-and-business-intelligence/bayesian-analysis-python-second-edition) (BAP) by Osvaldo Martin, one of the contributors to the PyMC3 project. The book claims to be introductory, but goes further than the courses above. The `bayesian-analysis-exercises` folder contain my answers to the exercises in the chapters. You will need to `git clone` the book's code repository at the top level of this project (`git clone https://github.com/aloctavodia/BAP.git`) to get access to the data files used by the book, and referenced from my notebooks.

## Environment

Initially I just created a conda environment making sure I had the following packages installed.

* numpy
* scipy (for scipy.stats)
* statsmodels
* PyMC3
* matplotlib

Later when I started following the BAP book, I needed some additional packages such as arviz, graphviz, etc., so I just ran the [BAP YAML file](https://github.com/aloctavodia/BAP/blob/master/bap.yml) in the same environment.

`conda env create --file bap.yml`

Later I encountered issues with Theano not being able to compile the PyMC3 code that I couldn't figure out how to fix, so I created a completely new environment from a __slightly modified__ clone of bap.yml, available as [environment.yml](environment.yml). The modifications were to move the versions of `numpy` and `pandas` up for `xarrow` to be installed, which is needed by `arviz`.

`conda env create --file environment.yml`

In addition, when importing pymc3 and friends into the notebook, it complained about `mkl` and `mkl-service` so these needed to be installed as well.

```
conda install mkl
conda install mkl-service
```

Optionally, if your environment does not do this automatically, in addition to running Jupyter notebooks inside your newly created environment, you might need to create a Jupyter notebook kernel. To do this, run the following commands.

```
source activate bap
python -m ipykernel install --user --name bap --display-name "Python (BAP)"
```

To delete the environment and the kernel after you are done exploring, use the following commands:

```
source activate bap
jupyter kernelspec uninstall bap
source deactivate
conda remove --name bap --all
```

## General impressions

* Course uses JAGS, PyMC3 has more natural syntax 
* statsmodels.OLS is not as flexible compared to R's lm().

## Caution

* Meant for understanding how to apply Python libraries to problems solved with R in the course.
* If used to answer quizzes, can lead to disappointment since answers don't always match exactly.

