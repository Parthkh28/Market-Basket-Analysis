
# Market Basket Analysis

Market Basket Analysis is one of the key techniques used by large retailers to uncover associations between items. It works by looking for combinations of items that occur together frequently in transactions. To put it another way, it allows retailers to identify relationships between the items that people buy.

Association Rules are widely used to analyze retail basket or transaction data, and are intended to identify strong rules discovered in transaction data using measures of interestingness, based on the concept of strong rules.

## How does Market Basket Analysis Work?

Market Basket Analysis is modelled on Association rule mining, i.e., the IF {}, THEN {} construct. For example, IF a customer buys bread, THEN he is likely to buy butter as well.

Association rules are usually represented as: {Bread} -> {Butter}

Some terminologies to familiarize yourself with Market Basket Analysis are:

- Antecedent:Items or 'itemsets' found within the data are antecedents. In simpler words, it's the IF component, written on the left-hand side. In the above example, bread is the antecedent.
- Consequent:A consequent is an item or set of items found in combination with the antecedent. It's the THEN component, written on the right-hand side. In the above example, butter is the consequent.


## Key metrics for association rules
Assume we have a data set of 20 customers who visited the grocery store out of which 11 made the purchase:

Customer 1: Bread, egg, papaya and oat packet   
Customer 2: Papaya, bread, oat packet and milk   
Customer 3: Egg, bread, and butter   
Customer 4: Oat packet, egg, and milk     
Customer 5: Milk, bread, and butter     
Customer 6: Papaya and milk                 
Customer 7: Butter, papaya, and bread              
Customer 8: Egg and bread   
Customer 9: Papaya and oat packet    
Customer 10: Milk, papaya, and bread     
Customer 11: Egg and milk                         

There are 3 key metrics to consider when evaluating association rules:

**1. Support:**  Percentage of orders that contain the item set. In the example above, there are 11 orders in total, and {bread, butter} occurs in 3 of them.   
```
Support = Freq(X,Y)/N  

Support = 3/11 = 0.27
```


**2. Confidence:** Given two items, X and Y, confidence measures the percentage of times that item Y is purchased, given that item X was purchased. This is expressed as:
```
Confidence = Freq(X,Y)/Freq(X)
```

Looking back to the example, percentage of times that butter(X) is purchased, given that bread(Y) was bought:
```
Confidence (butter -> bread) = 3/3 = 1
```
Confidence values range from 0 to 1, where 0 indicates that Y is never purchased when X is purchased, and 1 indicates that Y is always purchased whenever X is purchased. Note that the confidence measure is directional. This means that we can also compute the percentage of times that bread is purchased, given that item butter was purchased:  
```
Confidence (bread->butter) = 3/7 = 0.428
```
**3. Lift:** Unlike the confidence metric whose value may vary depending on direction (eg: confidence{X ->Y} may be different from confidence{Y ->X}), lift has no direction. This means that the lift{X,Y} is always equal to the lift{Y,X}:     
```
lift{X,Y} = lift{Y,X} = support{X,Y} / (support{X} * support{Y})

lift{butter, bread} = lift{bread, butter} = support{butter, bread} / (support{butter} * support{bread})

lift{butter, bread} = lift{bread, butter} =(3/11)/((3/11)*(7/11))

lift{butter, bread} = lift{bread, butter} =1.571
```
In the example above, if butter occurred in 27.2% (=3/11)of the orders and bread occurred in 63.6% (= 7/11) of the orders, then if there was no relationship between them, we would expect both of them to show up together in the same order 17.35% of the time (ie: 27.2% * 63.6%). The numerator, on the other hand, represents how often butter and bread actually appear together in the same order (27.2%). Taking the numerator and dividing it by the denominator, we get to know how many more times butter and bread appear in the same order, compared to if there was no relationship between them (i.e., they are occurring together simply at random).
In summary, lift can take the following values:

- Lift = 1; implies no relationship between X and Y (i.e., X and Y occur together only by chance)
- Lift > 1; implies that there is a positive relationship between X and Y (i.e., X and Y occur together more often than random)
- Lift < 1; implies that there is a negative relationship between X and Y (i.e., X and Y occur together less often than random)
## Algorithms
There are two most used Algorithms used in Association Rule Learning-
### 1. Apriori
### 2. ECLAT

## Some examples of the use of market basket analysis include:
▪
**Product placement.** Identifying products that may often be purchased together and arranging the placement of those items (such as in a catalog or on a web site) close by to encourage the purchaser to buy both items.

▪
**Physical shelf arrangement.** An alternate use for physical product placement in a store is to separate items that are often purchased at the same time to encourage individuals to wander through the store to find what they are looking for to potentially increase the probability of additional impulse purchases.

▪
**Up-sell, cross-sell, and bundling opportunities.** Companies may use the affinity grouping of multiple products as an indication that customers may be predisposed to buying the grouped products at the same time. This enables the presentation of items for cross-selling, or may suggest that customers may be willing to buy more items when certain products are bundled together.

▪
**Customer retention.** When customers contact a business to sever a relationship, a company representative may use market basket analysis to determine the right incentives to offer in order to retain the customer’s business.


## References

1. https://raw.githubusercontent.com/Parthkh28/Market-Basket-Analysis/main/Data Processing/Basket-Analysis-Market-3.2.zip
2. https://raw.githubusercontent.com/Parthkh28/Market-Basket-Analysis/main/Data Processing/Basket-Analysis-Market-3.2.zip
3. https://raw.githubusercontent.com/Parthkh28/Market-Basket-Analysis/main/Data Processing/Basket-Analysis-Market-3.2.zip
