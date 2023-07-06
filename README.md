# CUSTOMER LIFETIME VALUE DETERMINATION

The Beta-Geometric Negative Binomial Distribution (BG-NBD) model is an influential probabilistic model for describing customer behavior 
and for predicting customer lifetime value (CLV).

This work uses the  Python library called lifetimes created by Cam-Davidson Pillon. Lifetimes abstracts away the internal complexity of BG-NBD and allows us to focus on deriving insights 
and business values out of the model.

![CLV](clv.png)

Before fitting the BG-NBD model, we need to first restructure this table to the canonical “RFM” format. 

![RFM](rfm.png)

# Calibration-holdout split

When reformating our table into the RFM format, we have the option to also perform a calibration-holdout split, which is similar in spirit to the train-test split procedure we’re all familiar with. The calibration-holdout split divides our transactions into two depending on whether they fall into the calibration period or the observation period. The transactions that took place during the calibration period are used to train the model, whereas those occurring during the observation period (“holdout’” transactions) are used to validate the model.

# Business applications

CLV estimation using BG-NBD

We’ve seen how we could use the BG-NBD model to predict the probability-of-being-alive p as well as number of purchases in the next k periods. These two predictions can in turn be used to calculate a rough estimate of the customer’s value for the next k periods. The estimate can be calculated as follows:

![Formula(formula.png)

This estimate relies on the following two simplistic assumptions:

1) The probability-of-being-alive p remains unchanged in the next k periods
  
2) The average value of purchases in the next k periods equals the average purchase values in the observation period.
   
Do note that these naive assumptions have weak theoretical underpinnings — in reality, p usually changes after every purchase and the future purchase value might diverge significantly from the past values. As such, the resulting estimate is a rough one. 
