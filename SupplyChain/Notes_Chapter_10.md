
# Inventory Management

**2 Major Questions**
1. How much inventory should be ordered at one time?
2. When should an order be placed

#### Stock Keeping Units

Control of individual items -> each own Configuration of one Item would get own SKU 

#### Lot Size Decision Rules

- Lot for Lot
- Fixed order quantity
- Periods of supply
- Dynamic order quantities

#### Economic Order Quantity

Minimizes Cost under the assumptions:
1. Demand is constant and known
2. item is purchased in predefined groups
3. costs are constant and known
4. replacements occur all at once

#### Relevant Costs

Are annual Costs of placing Orders and carrying inventory

When order quantity increases -> inventory and therefore costs of carrying increase -> number of orders per year and cost of placing orders decreases

Search for: 
> the Cost of *carrying inventory* and the *cost of ordering* will be at **minimum**

#### Inventory Costs

$A = \text{annual demand}$
$S = \text{ordering cost in dollars/order (setup)}$
$\text{i} = \text{annual carrying cost as a decimal or percentage (interest rate)}$
$c = \text{unit cost in dollars}$
$Q = \text{order quantity in units}$

$\text{Annual ordering Cost} = \dfrac {A} {Q} \times S$
$\text{Annual Carrying Costs} = \dfrac {Q} {2} \times c \times i$

#### Economic Order Quantity Formula
$\dfrac {\text{Qic}} {2} = \dfrac {\text{AS}} {Q}$
$\text{Q}^2 = \dfrac {2\text{AS}} {\text{ic}}$
$Q = \sqrt {\dfrac {2\text{AS}} {\text{ic}}}$ 

#### EOQ

Minimizes **Total Cost** *of Carrying and Ordering*

Cost to Order = Cost to Carry

#### Quantity Discounts

Encourages buying more than normal

Will increase inventory -> increases carrying cost <-> Decreases ordering Costs

Savings from lower unit cost need to more or at least equal to rising carrying costs

#### Period Order Quantity

**EOQ** asssumes demand is uniform -> orders quantity that attempts to balance the cost of ordering with the cost of carrying

**POQ** sets *time interval* that orders predetermined number of times per year -> can reduce carrying costs especially with non-uniform demand

$POQ_{weeks} = \dfrac {\text{EOQ}} {\text{average weekly usage}}$

#### When not to use EOQ

> 1. Make to Order
> 2. Shelf life short
> 3. other limitations like Tool life limited or batch size has limitations

#### Practical Considerations When Using the EOQ

- Lumpy demand
- Anticipation inventory
- Minimum order quantities
- Transportation inventory
- Multiple order quantities

##### Lumpy demand

EOQ assumes continuous demand -> use POQ otherwise

##### Anticipation Inventory

Planned buildup for future capacity or demand

##### Minimum order quantities

- suppliers may set a minimum order quantity
- may be the value of the total order

##### Transportation inventory

quantity ordered may be set by transportation consideration ( similar approach to quantity discounts)

