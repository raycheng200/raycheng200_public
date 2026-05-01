Customer Segmentation via Manual SVD

Project Overview:

This project performs an exploratory data analysis on the Kaggle Customer Segmentation Dataset. The goal is to uncover hidden "archetypes" within the customer base using Singular Value Decomposition (SVD).
Instead of using the libraries directly, this project implements the SVD manually via the Power Method and Deflation.

Methodology:

I applied mixed imputation, where numerical features were imputed with the mean, while categorical features were imputed with the most frequent value.
I used ordinal encoding in the columns "Gender", "Ever_Married", "Graduated" and "Spending_Score".
I used One-Hot encoding in the nominal features "Profession" and "Var_1".
I centered and scaled the data using StandardScaler. 

Manual SVD Implementation:

The SVD was computed using Power Method, that is to iteratively find the dominant eigenvector of the similarity matrix $A^\top A$.
Deflation: To find the next dominant eigenvector by removing the influence of the previous singular vectors ($A_{k+1} = A_k - \sigma_k \textbf{u}_k \textbf{v}_k^\top$) and continue until all the eigenvectors are found.

Project Results:

Clustering: The first two columns of $U$ and $V$ reveals different segments of the market.
Dimensionality Reduction: 15 singular values were found to capture 85.76% of the total variance in the dataset.

License of the Kaggle Dataset:
CC0: Public Domain
No Copyright
The person who associated a work with this deed has dedicated the work to the public domain by waiving all of his or her rights to the work worldwide under copyright law, including all related and neighboring rights, to the extent allowed by law.
You can copy, modify, distribute and perform the work, even for commercial purposes, all without asking permission.

Citation:
"Customer Segmentation", Kaggle, https://www.kaggle.com/datasets/vetrirah/customer/data