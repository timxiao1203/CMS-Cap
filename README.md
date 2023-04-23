# CMS-Cap

CMS stands for constant maturity swap. A CMS cap/floor consist of a number of caplet/floorlet on the index rate of a CMS rate. Pricing a CMS cap/floor is equivalent to price a portfolio of a continuum of vanilla interest rate swaptions. The SABR model is applied to evaluate the replicating interest rate swaption portfolio.

A traditional method of pricing CMS products involves so-called convexity adjustment. There are three major drawbacks of that approach, not even mentioning the lack of rigorousness of the method. 

Firstly, in the traditional method, the correlation between a CMS rate and a forward rate is required. This parameter is not market observable. The start date of the accrual period of the forward rate is the reset date of the CMS rate and the end date is the payment date. 

Thus, in some cases, this forward rate is not even well defined in the market, i.e., it has to be implied from a zero rate curve, which implies that it is also difficult to obtain the statistic correlation through historical data. This drawback makes the application of the method in a subjective way since a user may manipulate the result by changing the correlation. 

Secondly, one needs to input two volatilities into the convexity adjustment formula, which are the volatility of the CMS rate and the one of the forward rates. The CMS rate volatility can be got from the swaption market. 

However, for the same reason mentioned previously, the volatility of the forward rate is not well defined in the market. Some interpolation has to be done through a cap/swaption volatility surface to estimate this volatility. Furthermore, it is certainly questionable how to incorporate the market volatility smile and skewness. This is a crucial issue in model applications.

Thirdly, if it’s not finally, how does one hedge the “convexity adjustment”? Or more explicitly, how is the CMS derivative product to be hedged? The traditional method did not provide any clue. Based on the above analysis, the traditional approach is not recommended.

A new method proposed is based on the replication of CMS caps/floors by using a portfolio of IR swaptions with all strikes, which implies that CMS derivative hedging is clearly provided. In this approach, there is no any parameter which is market imperceptible. Further, the market smile and skewness is naturally embedded into the swaption portfolio. 

Let us elaborate in the following. If we know the current prices of the CMS cap and floor, denoted by cmsCap(S0,K) and cmsFlr(S0,K), respectively, where S0 is the current value of the index swap rate, then by using call-put parity and under a numeraire of the zero bond P(·, tp), we have a formula.

Hence, computing the CMS cap and floor prices is primary. In Felix’s approach, the CMS cap price is given. Similarly, for the CMS floor, we have a solution.

In the above, the correction factor μT is given in [2], ˜g is given in [4], SwptP(S0, ·) and SwptR(S0, ·), the RTP- and RTR-swaption prices, are given by SABRN-model. It should be noted that the above approach is approximate arbitrage-free. In the above integrations, integral intervals may be further divided into two pieces which are corresponding to out-of-the-money IR swaptions.

Reference:

https://finpricing.com/product.html

