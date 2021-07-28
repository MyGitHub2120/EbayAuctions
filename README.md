# EbayAuctions

The dataset below eBayAuctions.csv contains information on 1972 auctions transacted on eBay.comduring May–June 2004. The goal is to use these data to build a model that will distinguish competitiveauctions from noncompetitive ones. A competitive auction is defined as an auction with at least two bidsplaced on the item being auctioned. The data include variables that describe the item (auction category),the seller (his or her eBay rating), and the auction terms that the seller selected (auction duration,opening price, currency, day of week of auction close). In addition, we have the price at which theauction closed. The goal is to predict whether or not an auction of interest will be competitive

Step 1:
Preprocess the Data:

Create dummy variables for the categorical predictors. These include Category (18 categories),Currency (USD, GBP, Euro), EndDay (Monday–Sunday), and Duration (1, 3, 5, 7, or 10 days).
Bin the scheduled departure time into eight bins (in R use function cut()

Use these and all other columns as predictors (excluding DAY_OF_MONTH).
Partition the data into training and validation sets.

Step 2:
Once you've preprocessed the data, complete the following:
Create pivot tables for the mean of the binary outcome (Competitive?) as a function of the variouscategorical variables (use the original variables, not the dummies). Use the information in the tablesto reduce the number of dummies that will be used in the model. For example, categories thatappear most similar with respect to the distribution of competitive auctions could be combined.
Split the data into training (60%) and validation (40%) datasets. Run a logistic model with allpredictors with a cutoff of 0.5. If we want to predict at the start of an auction whether it will becompetitive, we cannot use the information on the closing price. Run a logistic model with allpredictors as above, excluding price. How does this model compare to the full model with respect topredictive accuracy?

Run a logistic model with all predictors as above, excluding price. You need to do this because if wewant to predict at the start of an auction whether it will be competitive, we cannot use the informationon the closing price. Then:

How does this model compare to the full model with respect to predictive accuracy? Then:
Interpret the meaning of the coefficient for closing price. Does closing price have a practicalsignificance? Is it statistically significant for predicting competitiveness of auctions? (Use a 10%significance level.)
Use stepwise selection (use function step() in the stats package or function stepAIC() in the MASSpackage) and an exhaustive search (use function glmulti() in package glmulti) to find the model withthe best fit to the training data. Which predictors are used?
Use stepwise selection and an exhaustive search to find the model with the lowest predictive errorrate (use the validation data). Which predictors are used?
What is the danger of using the best predictive model that you found?
Why the best-fitting model and the best predictive models are the same or different.
If the major objective is accurate classification, what cutoff value should be used?
