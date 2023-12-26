# Financial-Trading-In-New-England-Energy-Market
Project goal: Get at least 30% return from financial transactions in the ISO-NE wholesale energy market.

Background information:

Day-Ahead Market: "Day Ahead" refers to the trading and scheduling of electricity a day before actual delivery. Participants submit offers and bids for the next day's anticipated electricity consumption and production. Day Ahead is contractually binding.

Real-Time Market: "Real Time" in the energy market involves the immediate trading and dispatch of electricity to meet current demand. It accounts for unforeseen changes and is adjusted in real-time based on actual consumption and production needs. Real-time can be changed every 5 minutes.

Incremental Bid Transaction: Borrowing and selling electricities at DA price of one day, then buying them back at the actual market price of the same hour, yields a profit of spread through arbitrage.

Decremental Bid Transaction: Purchasing electricities at DA price for one day and selling them at the actual price of the same hour, yields a profit of price difference.

Transaction Step:

To make sure a specific transaction can be executed, there are several steps need to be followed:

Choose a node (1211 from ISO-NE, Node 4008 NEMASSBOST is our primary trading node).

Choose a date and hour ending.

Decide the type of transaction(INC or DEC).

Decide a bid offer price for the DA market before 10:30 am, one day before the desired transaction date.

If the bid-offer price is lower than the DA price, the contract will be cleared for INC. 

For DEC, the bid-offer price will be cleared if the bid-offer price is higher than the DA price. 

If the price is not cleared, the transaction fails.

The contract is executed for the next day for a cleared bid-offer price, and a reverse transaction will be executed from the RT market. 

The price difference(Spread) between the DA and RT market will be the profit/loss for the transaction.

Formula:
Spread/MWH: INC= DA Clearing Price - RT Clearing Price
           
            DEC= RT Clearing Price - DA Clearing Price

Model Purpose: Since DA price is very imporant because it determine whether our bid offer can be excuted for further transaction, it is essential to predict the Day-ahead price for the users as a benchmark price to bid in.

Model description: Machine learning and Deep learning algorithms predicted the DA price for the desired trading period.

Data used: Past three years DA price, System load Demand, fuel price, Forward threshold price, holiday availability, and hour ending.
ML model tested: Linear regression, Lasso and Ridge, Polynomial degree 1-3, Decision Tree, Random Forest, Gradient Boosting Tree, Support Vector Machine.
DL tested: Tensorflow.
Assessment of model Performance: Mean Absolute Error, Mean Absolute Percentage Error, and Root Mean Square Error.


