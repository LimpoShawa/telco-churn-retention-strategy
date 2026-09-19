# Telco Customer Churn: Retention Risk Analysis

## Business Problem
The company wants to know which customers are most likely to cancel their 
subscription, and what's actually driving that risk price, contract type, 
or service experience so they can prioritize a retention intervention 
that's worth the cost.

## Hypothesis
Customers on month-to-month contracts with higher monthly charges and no 
add-on services (like tech support or online security) are far more likely 
to churn because they have less "lock-in" and less perceived value for 
the price.

## Approach
Exploratory analysis on the [Telco Customer Churn dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn) 
(7,043 customers, 21 features). Data was checked and cleaned first: no missing 
values or duplicates, but `TotalCharges` was stored as text due to 11 
brand-new customers (0 months tenure) with no completed billing cycle — 
fixed by converting to numeric and filling with 0.

## Key Findings
1. **Overall churn rate: 27%** — high for a subscription business, confirming 
a real retention problem.
2. **Contract type is the strongest lever**: month-to-month customers churn 
at 43%, vs. just 3% for two-year contracts — a ~15x difference.
3. **Price matters independently of contract type**: churned customers paid 
more than retained customers even within the same contract length, and this 
gap widens on longer contracts — suggesting price dissatisfaction can 
outweigh contractual lock-in.
4. **Not all add-ons reduce churn equally**: online security and tech 
support are strongly linked to retention, while streaming TV/movies show 
the opposite pattern suggesting reliability/support services create real 
dependency, while entertainment add-ons don't.

## Recommendation
Rather than pushing month-to-month customers into longer contracts which 
reduces churn numbers without addressing why customers want to leave the 
company should proactively target its highest-risk segment (month-to-month, 
above-average charges, no support add-ons) with a free trial of tech support 
and security services. This builds loyalty through real value instead of 
exit friction.

## Limitations
This is correlational, not causal. It's possible customers already intending 
to stay are simply more willing to try add-ons (reverse causality). Ideally, 
the company would validate this with a controlled test: offer free trials to 
a random sample of at-risk customers and compare churn against a similar 
group without the offer.

## How to Run
Open `telco-churn-retention-strategy.ipynb` in Google Colab or Jupyter. 
Requires `pandas`. Dataset available on Kaggle (link above).
