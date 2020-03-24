# Prosper Loan Data Exploration
## by Tom Schonig

## Dataset

The data source for this project will be the 'Loan Data from Prosper', one of the pre-approved data sources. This was selected because it exceeds all of the minimum requirements (size, number and types of variables, etc), and seemed most interesting to me.

After deciding on the dataset, I began wrangling and loaded the data into a Jupyter notebook. Although pre-approved by Udacity, I needed to validate the data's cleanliness and tidiness, and ensure all the columns were imported with the correct data types. Initial assesssment identified several columns that required conversion to datetimes. Likewise, I assessed each column to identify NaNs, duplicates, and the proportion of unique values (to assist in identifying potential unique keys, as well as categorical datatypes). 

In cleaning the data, I duplicated the original dataframe. Then, I dropped 871 records with duplicate keys, converted 5 columns to datetimes, and converted 6 columns to categoricals. A new .csv was saved upon completing all cleaning tasks.

## Summary of Findings

 - Overwhelming majority of loans are for the 3 year term
 - Most borrowers are charged ~18-22%, though there is a tail out into the 33-36% range
 - There is a long-left tail in the 'EstimatedEffectiveYield' - ie. infrequent but large losses
 - Most borrowers are new in their jobs, with a power-order distribution and very few with long tenure
 - Most borrowers have a credit score in the mid-600s
 - Most borrowers have 6-15 credit lines open
 - Most loans have never been delinquent, but there's a long tail of loans that have been delinquent for a long time
 - Most of borrowers only have 1 loan with Prosper
 - Most borrowers have less than $10,000 outstanding; amounts borrowed follow a power-order distribution, except for large spikes at round-lots (eg. $20,000 and $25,000)
 - No meaningful change in credit score between loans, for those with more than 1 Prosper loan
 - Most loans have been made in recent years, with rapid growth after the financial crisis (originations roughly doubling between 2013 and 2014)
 - Overwhelming majority of loans do not have a 'social' component, ie recommendations or investments from friends
 - Most loans have only ~119 investors, only a few have hundreds or thousands of investors
 - California is over-represented among borrowers
 - Borrowers are nearly-evenly split between homeowners and non-homeowners
 - Most borrowers are middle income, between $25-75k/year
 - Majority of loans are in good standing, only ~20% are past due, charged off or defaulted
 - Most borrowers began their credit histories in the 1990s
 - Most columns are not strongly correlated with one another (positively or negatively), except those that share definitional components (ie. the number of days delinquent and loan status)
 - Prosper's proprietary scoring mechanism ("ProsperScore") does have a semi-strong correlation with estimated losses and the rates paid by each borrower
 - Socially-funded loans tend to be less risky and perform better:
      - 


## Key Insights for Presentation

For my presentation, I will focus on the socially-funded loans, and their performance relative to non-social loans. To do this, I need to communicate several aspects of the dataset in a narrative:

    1 - What is the base-case; how many of Prosper's loans are non-performing and how many are socially funded?
            Visualization: Faceted time-series of loan standing and social-funding
        
    2 - How do the borrowers differ? How are they using Prosper and credit (generally) differently?
            Visualization: LoanOriginalAmount and AmountDelinquent plot
            
    3 - What does this mean for their loans? How do the socially-funded loans perform differently?
            Visualization: BorrowerRate and EstimatedLoss
    
    