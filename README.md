# Plato-s_Pizza_BI
---------------------------------
## 1. Problem Statement

### 1.1 Customer Communication
>Welcome aboard, we're glad you're here to help!
>
>Things are going OK here at Plato's, but there's room for improvement. We've been collecting transactional data for the past year, but really haven't been able to put it to good use. Hoping you can analyze the data and put together a report to help us find opportunities to drive more sales and work more efficiently.
>
>Here are some questions that we'd like to be able to answer:
> - What days and times do we tend to be busiest?
> - How many pizzas are we making during peak periods?
> - What are our best and worst selling pizzas?
> - What's our average order value?
> - How well are we utilizing our seating capacity? (we have 15 tables and 60 seats)
>
>That's all I can think of for now, but if you have any other ideas I'd love to hear them – you're the expert!
>Thanks in advance,
> Mario Maven (Manager, Plato's Pizza)

## 2. Assumptions and Insights

### 2.1 Assumptions
1. The earliest order was between 9 AM and 10 AM so I assumed that the operating hours for Plato's Pizza is between 09:00 to 23:59.
2. The days with no orders (#8 days) have not been assumed as holidays just days with no orders.
3. Sunday evening to Thursday evening for the purposes of analysis have been considered school nights
4. For the purposes of capacity analysis, I have assumed this is a dine in restaurant and have no take out orders irrespective of the time of order.
5. Small pizzas are consumed by an individual, Medium pizza is shared between 2 individuals, Large Pizzas are shared between 4 individuals, Xtra Large pizzas are shared between 6 individuals and Xtra Xtra Large pizzas are shared between 8.
6. For Table capacity Analysis it is assumed that 4 chairs are available to each table and table sharing is not permitted. Also, if there are 1 - 4 people in a group they will need one table, 5-8 people in a group will need 2 tables and so on.
7. Seat capacity analysis is independent of Table capacity analysis. It is not required for an individual to have a dedicated table to eat their pizza. Tables can be shared. Each individual requires a seat to eat pizzas.
8. Key metrics for analysis are Total Orders, Total Revenue, Average Revenue per Day/Hour , Average Orders per Day/ Hour, Average Revenue per order, Average Pizzas produced by Day/ Hour, Table Shortage, Seat Shortage, Days with no Table/Seat shortage (stockout).

### 2.2 Basic Statistics (observation) from data
1. In a year Plato's Pizza 
   - Total orders received 21.35K orders
   - Average orders per day 58.33 
   - Total revenue generated is $817.86K
   - Average revenue per order is $38.31
   - Average revenue per day is $2.23K
 2. Most orders are received on Friday (3.54K) generating $136K followed by Thursday (3.24K) generating $123.53K. The least orders are recevied on Monday (2.62K) generating $99.20K.
 3. Average orders received on School nights are 56.15 while on Holiday nights are 63.77 orders per day.
 4. July is the busiest month with 62.42 orders per day on average generating $72.56K while the least busiest month was October with 53.10 average orders per day generating $64.03K
 5. November and October generates the highest revenue per order at $39.28 per order and $38.9 per order respectively.
 6. Hour wise analysis
    - Least Busy hours were 9 AM to 10 AM with 1 order, 10 AM to 11 AM with 8 orders and 11 PM t0 12:00 AM with 28 orders across the year.
    - Busiest time was between 12 noon to 1 PM with 2.52K orders (6.89 orders per day) generating $111.88K followed by 1 PM to 2 PM with 2.46K orders (6.71 orders per day) generating $106K
 7. Best Selling Pizzas
     - Pizzas #: Classic Deluxe Pizza (2,453)
     - Pizzas Small #: Big Meat Pizza (1,914)
     - Pizzas Medium #: Classic Deluxe Pizza (1,181)
     - Pizzas Large #: Thai Chicken Pizza (1,410)
     - Pizzas $: Thai Chicken Pizza ($43,434)
     - Pizzas Small $: Big Meat Pizza ($22,968). 2x of next best selling small pizza.
     - Pizzas Medium $: Classic Deluxe Pizza ($18,896)
     - Pizzas Large $: Thai Chicken Pizza ($29,258)
  8. Worst Selling Pizzas
     - Pizzas #: Brie Carre Pizza (490)
     - Pizzas Small #: Chicken Alfredo Pizza (96)
     - Pizzas Medium #: Spinach Supreme Pizza (267)
     - Pizzas Large #: Green Garden Pizza (96)
     - Pizzas $: Brie Carre Pizza ($11,588)
     - Pizzas Small $: Calabrese Pizza ($1,213). 
     - Pizzas Medium $: Mediterranean Pizza ($4,400)
     - Pizzas Large $: Green Garden Pizza ($1,924)

### 2.3 Key Insights
1. Busiest Day-Hour slot by
   - Total Orders: Thursday between 1 PM to 2 PM with 438 orders followed by same day 12 noon to 1 PM slot with 434 orders
   - Total revenues: Thursday between 12 noon to 1 PM generating $19K followed by same day 1 PM to 2 PM slot generating 18.8K
   - Total Pizzas: Thursday between 12 noon to 1 PM with 1149 pizzas followed by same day 1 PM to 2 PM slot with 1131 pizzas and Monday 12 noon to 1 PM with 1126 pizzas.
   - Pizzas Produced: Thursday between 12 noon and 1 PM with an average of 21.68 pizzas followed by Monday 12 noon to 1 PM with an average of 21.65 pizzas
 2. Busiest slots on Working days is lunch between 12 PM to 2 PM with gradual decline during the day and small peak in the evening (dinner orders) between 5 PM to 7 PM followed by another gradual decline in orders.
 3. Busiest slots on Weekends is dinner between 5 PM to 7 PM.
 4. Brie Carre Pizza is the worst selling pizza with only 490 pizzas ($11,588) sold across the year probably because it's only sold in small sku. This is the second best selling small pizza by revenue $.

### 2.4 Recommendations
1. Average revenue generated between 9 AM to 10 AM is ~$0.2 per day, 10 AM to 11 AM is ~$0.8 per day and slot 11 PM to 12 AM is ~$3 per day which is less than minimum wage thus we recommend to change the opening hours from 11 AM (or 10:30 AM) to 11 PM.
2. 


## X. Data Files

This dataset contains 4 tables in CSV format

- The Orders table contains the date & time that all table orders were placed
- The Order Details table contains the different pizzas served with each order in the Orders table, and their quantities
- The Pizzas table contains the size and price for each distinct pizza in the Order Details table, as well as its broader pizza type
- The Pizza Types table contains details on the pizza types in the Pizzas table, including their name as it appears on the menu, the category it falls under, and its list of ingredients

## X. Data Dictionary
| Table      | Field  | Description     |
| :---        |    :----:   | :---         |
| orders   | order_id   | Unique identifier for each order placed by a table  |
| orders   | date   | Date the order was placed (entered into the system prior to cooking & serving)   |
| orders   | time   | Time the order was placed (entered into the system prior to cooking & serving)   |
| order_details   | order_details_id   | Unique identifier for each pizza placed within each order (pizzas of the same type and size are kept in the same row, and the quantity increases)   |
| order_details   | order_id   | Foreign key that ties the details in each order to the order itself   |
| order_details   | pizza_id   | Foreign key that ties the pizza ordered to its details, like size and price   |
| order_details   |quantity   | Quantity ordered for each pizza of the same type and size   |
| pizzas   | pizza_id   | Unique identifier for each pizza (constituted by its type and size)   |
| pizzas   | pizza_type_id   | Foreign key that ties each pizza to its broader pizza type   |
| pizzas   | size   | Size of the pizza (Small, Medium, Large, X Large, or XX Large)   |
| pizzas   | price   | Price of the pizza in USD   |
| pizza_types   | pizza_type_id   | Unique identifier for each pizza type   |
| pizza_types   | name   | Name of the pizza as shown in the menu   |
| pizza_types   | category   | Category that the pizza fall under in the menu (Classic, Chicken, Supreme, or Veggie)   |
| pizza_types   | ingredients   | Comma-delimited ingredients used in the pizza as shown in the menu (they all include Mozzarella Cheese, even if not specified; and they all include Tomato Sauce, unless another sauce is specified)   |

