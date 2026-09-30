# Northwind sales & stock analysis
## Questions to answer:
1. Which items are running out of stock right now?
2. What are our top-selling products versus how many we have left?
3. Which suppliers/carriers take the longest to ship orders?

## Hypothesis
1. Reorder triggers are taking too long to execute, or safety stock thresholds (ReorderLevel) were calculated based on static averages that no longer match current order volume.
Action: Immediately place stock replenishment orders for all non-discontinued items where UnitsInStock <= ReorderLevel to prevent stockouts and lost revenue.

2. Popular items generate high sales velocity, but because inventory management isn't dynamically linked to real-time sales rates, high-demand items are at constant risk of sudden stockouts.

Action: Prioritize inventory replenishment based on sales velocity (total units sold) rather than relying solely on static reorder flags.

3. Assigning orders to slower carriers like United Package increases overall customer lead times and creates delivery bottlenecks, especially for urgent or high-volume orders.

Action: Shift high-priority or best-selling product orders to Federal Shipping to minimize transit times, and re-evaluate service contracts with United Package.

## Findings 
### 1. Items in stock
* **lowest in stock:** Gorgonzola Telino, Sir Rodney's Scones, Louisiana Hot Spiced Okra are the items with lowest stock while 
* **highest in stock:** Gnocchi di nonna Alice, Wimmers gute Semmelkndel and Queso Cabrales	are the highest 
<img width="702" height="373" alt="Screenshot 2026-09-30 at 13 41 46" src="https://github.com/user-attachments/assets/81f1a641-208c-4ece-972d-beeaa6013d45" />


### 2. Top-selling products vs. stock remaining
* **Highest sales volume:** Camembert Pierrot, Raclette Courdavault, and Gorgonzola Telino lead overall sales volume.   
* **Inventory mismatch:** High-demand items like Gorgonzola Telino show significant sales volume but critical low-stock levels, exposing a high risk of stockouts compared to other products.

<img width="795" height="418" alt="Screenshot 2026-09-30 at 13 52 01" src="https://github.com/user-attachments/assets/8a3c2677-ae9a-4f59-9e16-65ef886b3d5e" />


### 3. Carrier shipping turnaround times
* **Fastest carrier:** Federal Shipping averages the fastest lead time at **7.5 day**s.
* **Slowest carrier:** United Package takes the longest to fulfill orders, averaging over **9.2 days**.

<img width="686" height="418" alt="Screenshot 2026-09-30 at 13 53 21" src="https://github.com/user-attachments/assets/18d40630-9b1a-4c41-a61f-e3a2365902e9" />



---

## Tools Used

* Python (Pandas, Seaborn, Matplotlib)
  
