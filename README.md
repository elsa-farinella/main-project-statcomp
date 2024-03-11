# The EM algorithm for different patterns of missingness
In this repository you can find our code for the main-project of the course [Statistical computation and visualisation](https://math-517.github.io/math_517_website/course-overview.html).  
In this project we approached two different problems:  
* Study of performances of the Expectation Maximization algorithm in a context with missing data.  
* Comparison of performances between EM algorithm and Maximum Likelihood Estimation after imputation.  
The most well-known missing data mechanisms are the three introduced in [5] by Rubin: Missing Completely at Random (MCAR), Missing at Random (MAR), Missing not at Random (MNAR). We used this three different mechanisms in every study we did in our project.

## Team  
Our team is composed by: 
* Di Gennaro Federico: [@FedericoDiGennaro](https://github.com/FedericoDiGennaro)   
* Farinella Elsa: [@elsa-farinella](https://github.com/elsa-farinella)      
* Scialanga Marco: [@marcoscialanga](https://github.com/marcoscialanga)

## Study of performances of the Expectation Maximization algorithm in a context with missing data  
The EM algorithm is an effective technique that is often used to perform MLE when faced with missing data. In the following subsections, we analyze how EM behaves when dealing with $P\%$ of missing values in the design matrix $X$, in three different frameworks:

1) *EM for Gaussian data*: Estimate the parameters $\mu$ and $\Sigma$ of a multivariate Gaussian random variable.

2) *EM for Linear Regression*: Estimate the parameters $\beta$ of a linear regression where the design matrix $X$ is such that $X_i \sim \mathcal{N}_p(\mu, \Sigma), \ i=1,...,n.$

3) *EM for Logistic Regression*: Estimate the parameters $\beta$ of logistic regression where the design matrix $X$ is such that $X_i \sim \mathcal{N}_p(\mu, \Sigma), \ i=1,...,n.$

In all three cases, we evaluate the performance of the EM algorithm with the root mean squared error (RMSE). 

## Comparison of performances between EM algorithm and Maximum Likelihood Estimation after imputation 
In this section we compare the accuracy of EM in estimating parameters $\beta$ in both Logistic and Linear regression on a task with missing data with the accuracy of estimating $\beta$ with Maximum Likelihood (ML) after having imputed the missing data with different methods. The imputation methods analysed were the following four and they are implemented in different libraries of R:  
- softImpute
- MICE
- missForest
- missMDA  

## Description of folders and files  
Here you can find a detailed description of what each file in this repository contains.  
|--- `report.pdf`: PDF of the report containing the results obtained from our study.  

|--- `report.qmd`: QMD file containing all the R code of our project and used to get the report.  

|--- `Personal Contributions`: The folder contains three brief statements, each independently written by a group member, detailing their respective contributions to the project, as required by the assignment for groups of three.

|--- `report_files/figure-pdf`: This folder will be automatically generated upon rendering the .qmd file and contains all the figures produced by the code within it. 

|--- `bibliography.bib`: This file includes all the references cited in our report.

|--- `ieee.csl`: This file ensures that the bibliography is formatted according to IEEE guidelines.

## Instructions on how to run the code
1. **Download the necessary files**
  
  Start by downloading the files *report.qmd*, *bibliography.bib*, and *ieee.csl*, located in the repository. Make sure to place all downloaded files in the same folder to enable correct rendering of the .qmd file.

2. **Render the .qmd File**

  Upon rendering the .qmd file, a PDF will be generated. The execution time is approximately 30 minutes. The extended run time is primarily due to the complex nature of the files being processed, which involves a considerable number of for loops. These loops are essential for averaging the results of the Expectation-Maximization (EM) algorithm.
  The rendered PDF document, produced from the .qmd file, is available in the repository or you can open the file by clicking [here](report.pdf); 

## Requirements
To ensure the correct execution of the code, please install the following packages:

- Amelia;
- devtools; 
- dplyr;
- ggplot2;
- ggpubr;
- gridExtra;
- MASS;
- mice;
- misaem;
- missForest;
- missMDA;
- missMethods;
- naniar;
- norm;
- softImpute;
- tidyr;
- VIM.

Furthermore, it is necessary to source specific R scripts that contain functions for data amputation and imputation. Please run the following commands in your R environment to source the scripts directly from the R-miss-tastic repository:

source('https://raw.githubusercontent.com/R-miss-tastic/website/master/static/how-to/generate/amputation.R')

source('https://raw.githubusercontent.com/R-miss-tastic/website/master/static/how-to/impute/CrossValidation_softImpute.R')

## References

[1] [Ibrahim, Joseph G., Ming-Hui Chen, and Stuart R. Lipsitz. 1999. “Monte Carlo EM for Missing Covariates
in Parametric Regression Models.” Biometrics 55 (2): 591–96.](https://ideas.repec.org/a/bla/biomet/v55y1999i2p591-596.html).  
[2] [Josse, Julie, and François Husson. 2016. “missMDA: A Package for Handling Missing Values in Multivariate
Data Analysis.” Journal of Statistical Software 70 (1): 1–31.](https://doi.org/10.18637/jss.v070.i01).  
[3] [Lavielle, Marc. 2014. Mixed Effects Models for the Population Approach: Models, Tasks, Methods and Tools.
Chapman and Hall/CRC.](https://hal.science/hal-01122873).  
[4] [Mazumder, Rahul, Trevor Hastie, and Robert Tibshirani. 2010. “Spectral Regularization Algorithms for
Learning Large Incomplete Matrices.” Journal of Machine Learning Research 11 (80): 2287–2322.](http://jmlr.org/papers/v11/mazumder10a.html).  
[5] [Rubin, Donald B. 1976. “Inference and Missing Data.” Biometrika 63 (3): 581–92.](http://www.jstor.org/stable/2335739). 
