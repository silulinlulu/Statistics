# Statistics
Statistical problems  in my research

## Colinearity/Multicolinearity

As a biology student, dealing with non-linear regression, violated model assumptions and pseudoreplication is your normal life. Recently, i ecountered a new problem : colinearity in predictors (independent) variables.  

There is colinearity/multicolinearity if two or more predictors in your regression mdoel are correlated. For example, the fewer food, the smaller colony size. When we put these two variables in our model, the variance explained by food will be less likely significant since the variance might have already been captured by colony size, meanwhile, the significance level might be exaggerated for colony size. In other words, colinearly reduces the statistical significance of the one while enhance the significance of another. This will overinflate the SE of coefficients and in turn reduce the statistical significance of some predictors.

We can use variance inflation factors(VIF) to detect colinearity or multicolinearity. VIF estimate the the variance of an estimated increase of a regression coefficient (needed to calculate SE of the coefficient) if your predictors are correlated. The baseline of VIF is 1 which means there is no colinearity. 

to assess VIF in R
