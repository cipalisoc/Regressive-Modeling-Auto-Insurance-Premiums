## Project 2

# Customer Lifetime Value: An Exploration of Auto Insurance Policyholders
Christian Palisoc

This project seeks to understand what is the projected lifetime value of a policyholder in terms of overall premium based on specific features, and how can we 
potentially expand (add more long term clients), retain (keep them coming back/renewing), and prolong (keep them longer) new and current policyholders.

## Data Source
https://www.kaggle.com/code/madhushreesannigrahi/jenks-natural-breaks-and-k-means-clustering/data

There are 9134 rows and 24 columns with our target feature, 'Customer Lifetime Value' with the rest of the features as data of individual policyholders.

## Exploratory Data Analysis

During the exploratory data analysis phase, boxplots were plotted for all the numerical features in our dataset to explain the distribution of the data. 


![CLV box](https://github.com/cipalisoc/Project2/blob/main/cust%20lifetime%20value%20boxplot.png?raw=true)
- The above boxplot depicts the data distribution of the feature, 'Customer Lifetime Value', which is also our target feature.

![num boxes](https://github.com/cipalisoc/Project2/blob/main/num%20features%20boxplots.png?raw=true)
- The above boxplots shows the distribution of the rest of the numerical features.

![cat bars](https://github.com/cipalisoc/Project2/blob/main/cat%20features%20bars.png?raw=true)
- The above barplots explain the counts of each categorical feature in our dataset.

## Explanatory Analysis
Prior to modeling our data, we wanted to see which features strongly correlated with each other, more specifically, which correlated strongest with our 'Customer
Lifetime Value' target feature. To accomplish this, we plotted a heatmap and found that although there aren't any correlations that stand out significantly, there
were still correlations still worth exploring. We saw that 'Monthly Premium Auto' paired with 'Customer Lifetime Value' and 'Monthly Premium Auto' paired with 
'Total Claim Amount' had the strongest correlations. Another correlation that was stronger than most related to our target feature was 'Number of Policies' vs 
'Customer Lifetime Value'.
![heatmap](https://github.com/cipalisoc/Project2/blob/main/heatmap.png?raw=true)
![sales_chan](https://github.com/cipalisoc/Project2/blob/main/val%20by%20sales%20channel.png?raw=true)

## Modeling
Our target feature, 'Customer Lifetime Value' is the overall premium amount that a customer will potentially pay throughout their total time insured with the
insurance company. In this case, we wanted to introduce a model that shows how well it would fit on our data to potentially explain a forecasted policyholder or
policyholder profile that would maximize profits for the insurance company. With this in mind, we focused on the R2 scorest of three regression models: a decision
tree, bagged tree, and random forest model. Initially, we ran the data through the three models with baseline parameters (no tuning) and then we tweaked a few 
parameters in the respective models to potentially obtain better R2 Scores.

The following are the R2 resuts of all three models:

- **Decision Tree Model**
  - R2 (Baseline Parameters): 37.66%
  - R2 (Tuned Parameters):    66.36%
- **Bagged Tree Model**
  - R2 (Baseline Parameters): 64.72%
  - R2 (Tuned Parameters):    65.56%
- **Random Forest Model**
  - R2 (Baseline Parameters): 67.12%
  - R2 (Tuned Parameters):    67.46%
  
## Insights and Recommendations
Although the above results did not produce a vast difference in R2 scores between the models, the tuned random forest model still had a better R2 score. We would 
have expected better scores, but as an insurance industry professional, the features used in our modeling do not fully explain a policyholders full lifetime value.
To improve the R2 score and better explain our target feature, I recommend introducing more features. More specifically, measure customer satisfaction, reason for
leaving prior carrier, and time/months insured with prior carrier. 

With our current data, there are strong correlations with our target feature and 'Monthly Premium Auto', 'Total Claim Amount' and 'Sales Channel' features. This 
provides insight as to policyholders being rate-driven as well as service-driven when it comes to customer loyalty. With insurance, policyholders do
not experience the "service" until a claim is made or when they seek changes needing to be made to their policy. With this in mind, I recommend instating a customer
loyalty discount or incentive that is capped after a period of time as a means to retain current policyholders and possibly discourage them from shopping. In the
previous visual explaining 'Sales Channel' and 'Total Lifetime Value', the best results came from a call center and branch. This may indicate that policyholders 
like consulting with an insurance professional vs online self-servicing. I recommend investing in the availability and access to insurance agents to make the
insurance process more personalized and consultative rather than transactional.  
