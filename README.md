# Statistics
Statistical problems  in my research

## Colinearity/Multicolinearity

As a biology student, dealing with non-linear regression, violated model assumptions and pseudoreplication is your normal life. Recently, i ecountered a new problem : colinearity in predictors (independent) variables.  

There is colinearity/multicolinearity if two or more predictors in your regression mdoel are correlated. For example, the fewer food, the smaller colony size. When we put these two variables in our model, the variance explained by food will be less likely significant since the variance might have already been captured by colony size, meanwhile, the significance level might be exaggerated for colony size. In other words, colinearly reduces the statistical significance of the one while enhance the significance of another. This will overinflate the SE of coefficients and in turn reduce the statistical significance of some predictors.

We can use variance inflation factors(VIF) to detect colinearity or multicolinearity. VIF estimate the the variance of an estimated increase of a regression coefficient (needed to calculate SE of the coefficient) if your predictors are correlated. The baseline of VIF is 1 which means there is no colinearity. 

to assess VIF in R
...to be conotinued

## Testing the significance of correlation
Correlation is a concept based on regression model but it is intensively used in the weighted gene coexpression network analysis. not sure that is appropriate to do?
anyway: if you got a correlation and if ou want to know how reliable this is, you need to conduct a hypothesis test. two things are reuiqred: alpha and df. df=n-m, n is number of samples, m is the number of factors that will are estimated to influence the meaured values of samples. fii you have more factors in your regression model, the reliability of your model will drop, especially when your sample size is small. this is also a reason why you need to use mixed model. In my WGCNA analysis, i assumed the correlation coefficient (Person) follows a  student T distribution and tested two tailed. 

## Gene count data...
Gene counts describes the activities of an organism. In a gene count matrix, you can see some genes' expression level extremely high/low depending on the activities and feeling of the organism. This extreme difference in expression are handled using 'GLNB' and 'Qusai-poisson'. I illustrate the differences between these two using two R packages commonly used in DEG analysis below. Difference between edgeR and DeSeq2: EdgeR applies generalized qusai-poisson model while SeSeq2 uses Generalized binominal model (raise to power p). Qusai-poisson (times some number? Cannot remember clearly) and negative binominal are means to deal with unvalidated module assumption for Poisson distribution (mean is equal to variance). 


## The difference between deseq2 and WGCNA in differential gene expression
1)	Input for deseq2 is integer count matrix and it applies generalized negative binominal model, input for WGCNA are normalized count matrix(non-integer). 
2)	There is no target gene to examine whether it is differentially expressed. The purpose of deseq2 is to identify differentially expressed genes between treatment. For WGCNA, differentially expressed gene analysis is conducted after network analysis when you already know the candidate genes from the identified network.


