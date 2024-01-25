# 8-Week-SQL-Challenge
## Case Study #1 : Pizza Runner

<img src="https://user-images.githubusercontent.com/81607668/127271856-3c0d5b4a-baab-472c-9e24-3c1e3c3359b2.png" alt="Image" width="300" height="320">

## 📚 Table of Contents
- [Business Task](#business-task)
- [Entity Relationship Diagram](#entity-relationship-diagram)
- [Question and Solution](#question-and-solution)

Please note that all the information regarding the case study has been sourced from the following link: [here](https://8weeksqlchallenge.com/case-study-2/). 

***

## Business Task
Danny was sold on the idea that "80s Retro Styling and Pizza Is The Future!” and started venturing into the business of Pizza Delivery! But being a VC himself before, he knew that Pizza Delivery aline isn't gonna get him the seed funding he need to hack the growth of his Pizza Empire. so he had one more genius idea to combine with it - he was going to Uberize it - and so Pizza Runner was launched!

To help Pizza Runner to get on the train for accelerated growth, we look into the data for insight!

***

## Entity Relationship Diagram

![image](https://github.com/katiehuangx/8-Week-SQL-Challenge/assets/81607668/78099a4e-4d0e-421f-a560-b72e4321f530)

***

## Question and Solution 

> 1. How many pizzas were delivered that had both exclusions and extras?
<br>

````sql
SELECT COUNT(*) pizzas_delivered_with_both_exclusions_and_extras
FROM pizza_runner.customer_orders c
LEFT JOIN pizza_runner.runner_orders r
USING(order_id)
WHERE LENGTH(exclusions)>0 AND exclusions!='null'
  AND LENGTH(extras)>0 AND extras!='null'
  AND LENGTH(cancellation)>0 AND cancellation!='null'
````

#### Steps:
- Use **JOIN** to merge `dannys_diner.sales` and `dannys_diner.menu` tables as the required information `sales.customer_id` and `menu.price` are from both tables.
- Use **SUM** to compute `total amount spent`.
- Group the aggregated results by `sales.customer_id`. 

#### Answer:
| customer_id | total_sales |
| ----------- | ----------- |
| A           | 76          |
| B           | 74          |
| C           | 36          |

<br>

***

<br>
