# Relevant Formulas for the Supply Chain Final Exam

## Chapter 10 Order Quantities

- `A` Annual demand in units
- `S` Setup, ordering costs per order in $
- `i` Annual Carrying Costs as a decimal or percentage
- `c` Unit cost in $
- `Q` Order quantity in units, number of items per single order

Annual Ordering Costs (Number of Orders * Cost per Order): 
$\frac {A} {Q} \times S$ 

Annual Carrying Costs (Average Inventory * Carrying Cost): 
$\frac {Q} {2} \times i \times c$

Economic Order Quantity (EOQ): 
$\sqrt{\frac{2 \times A \times S}{i \times c}}$

**Monetary** Unit Lot Size: 
$\sqrt{\frac{2 \times A \times c \times S}{i}}$

Period Order Quantity (POQ) in weeks: 
$\frac{EOQ}{\text{average weekly usage}}$

K constant fr POQ: 
$\sqrt{\frac{2 \times S}{i}}$

$K \times \sqrt{A_D} = \frac{\text{Annual Demand }A_D}{\text{Orders per year N}}$

$K \times \sqrt{A_D} = \frac{A_D}{N}$

**for finding k**

$k = \dfrac {\sqrt {A_D}} {N}$

*if multiple items*

$k = \dfrac {\sum_i \sqrt {A_{D},_i}} {\sum_i N_i}$

---

## Chapter 11 Independent Demand Ordering Systems 

Order Point: 
$OP = \text{Demand during Lead Time DDLT} + \text{Safety Stock SS}$

Average Inventory: 
$\frac{\text{Order Quantity Q}}{2} * SS$

Safety Stock Items: 
$SS = \sigma * \text{Safety Factor}$

Lead Time Intervals and Forecast Intervals:
$\sigma_\text{LTI} = \sigma_\text{FI} * \sqrt{\frac{LTI}{FI}}$

Target Level T: 
$T = \text{Demand during Review} + \text{Demand during Lead Time} + \text{SS} = D(R + L) + SS$

Periodic Review:
$\text{Quantity to order} = T - \text{On hand} <=> Q = T - I$


