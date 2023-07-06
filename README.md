# CUSTOMER LIFETIME VALUE DETERMINATION

The Beta-Geometric Negative Binomial Distribution (BG-NBD) model is an influential probabilistic model for describing customer behavior 
and for predicting customer lifetime value (CLV).

This work uses the  Python library called lifetimes created by Cam-Davidson Pillon. Lifetimes abstracts away the internal complexity of BG-NBD and allows us to focus on deriving insights 
and business values out of the model.

![CLV](clv.png)

Before fitting the BG-NBD model, we need to first restructure this table to the canonical “RFM” format. 

![RFM](rfm.png)
