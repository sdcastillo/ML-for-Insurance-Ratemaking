# ML-for-Insurance-Ratemaking

# Introduction

A few months ago, I sat on the first conference call with 43 other actuaries from around the U.S. to talk about how machine learning is changing the actuarial industry. The Casualty Actuarial Society (CAS) had formed a working party to research this area, and the turnout has been bigger than anyone has expected. We have since divided into two sub-groups to focus on 1) producing a worked-example of using ML, which is where I am, and 2) researching how to encorporate ML while following regulatory limitations.

The purpose of this paper is to gain practical experience creating models for auto insurance claims.

## How is pricing insurance different than pricing anything else?

Right in front of me is a small English Breakfast cup of tea from Cafe Nero.  This delicious hot beverage had a price of \$2.49.  Why was it \$2.49?  Why not \$249.00?  Why not \$5.00 or \$10.00?  The price is \$2.49 because Cafe Nero knows exactly how much it costs them to create the tea, how much they pay their hourly employees to serve the tea, the cost of rent to keep the store open, and they know that the average person is willing to pay this price.  At \$2.49, they believe that their profitability is highest.  The price is set based on known, fixed quantities.  

In pricing a cup of tea, profit is a function of fixed quantities

> Profit per Cup of Tea = Price Customer Pays - Cost to Cafe Nero

If Cafe Nero was selling me insurance instead of a cup of tea, then finding the right price would be a different exercise.  Let's say that Cafe Nero sold me auto insurance for the next 12-months for \$249 per month.  Would they make profit off of this policy?  This would depend on whether I was involved in an accident that year.  In years where I was not involed in accidents, they would be profitable, but if I happened to get into an accident that cost more than the annual premium, then they would lose money.

Their profit equation would involve *random variables* instead of fixed amounts.  That is, on years where the claims are higher than the premiums, they are not profitable.

> Profit per Policy = Premium - Claims

Now imagine that Cafe Nero has crystal ball which could predict the future and tell whether or not I would be in an accident and exactly how much this could cost them in claims.  Then they could just set their premium to be larger than this by any amount that they choose.  For instance, let's say that they want to make \$50 per policy month.  Then they would just set their premium to be \$50 higher than the predicted future claims.

> Profit per Policy = $50 + Predicted Claims - Actual Claims = $50

This would only be true so long as $\text{Predicted Claims}$ is a good predictiion!  If the predictions were bad, then the profitability would be unstable.  One of the main goals of pricing insurance is to predict future claims, and this requires building models which can determine the risk of selling coverage to policyholders.  


