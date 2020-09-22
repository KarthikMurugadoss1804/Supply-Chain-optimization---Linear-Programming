# Supply Chain optimization - Linear Programming



To develop and optimize a Liner Programming model that helps decide what raw material to order from which supplier, where to manufacture the products, and how to deliver the manufactured products to the customers so that the overall cost is minimized.

## Files

1. **Data.xlsx**

	The input data for problem statement is in this file. The file contains 8 sheets:
	- **Supplier stock** 
	A table indicating how many units of each raw material each of the suppliers has in stock. - 
	- **Raw material costs** 
	A table indicating how much each of the suppliers is charging per unit for each of the raw materials. 
	- **Raw material shipping** 
	A table indicating the shipping costs per unit of raw material (the units for each material are the same) from each supplier to each factory.
	- **Product requirements**
	 A table indicating the amount of raw material required to manufacture one unit of each of the products. 
	 - **Production capacity** 
	 A table indicating how many units of each product each of the factories is able to manufacture. 
	 - **Production cost** 
	 A table indicating the cost of manufacturing a unit of each product in each of the factories. 
	 - **Customer demand** 
A table indicating the number of units of each product that have been ordered by the customers 
	- **Shipping costs** 
	A table indicating the shipping costs per unit for delivering a product to the customer

2. **Code.py**
	
	This is python implementation in which the problem statement has been solved. 
	
	
## Problem Statement

 Factories can order suppliers from multiple suppliers and products can be delivered to customers from multiple factories. The goal of this project is to develop and optimise a Liner Programming model that helps decide what raw material to order from which supplier, where to manufacture the products, and how to deliver the manufactured products to the customers so that the overall cost is minimised. 

## Solution approach

**Python Libraries Used**: Google OR Tools pywraplp, pandas

A. Load the input data from the file “data.xlsx”. Note that not all fields are filled, for example Supplier C does not stock Material A and hence it will be blank in the excel sheet. All the values are read directly from the excel sheet and not hardcoded. 

B. Identify and create the decision variables for the orders from the suppliers, for the production volume, and for the delivery to the customers using the OR Tools wrapper of the GLOP_LINEAR_PROGRAMMING solver. 

C. Define and implement the constraints that ensure factories produce more than they ship to the customers. 

D. Define and implement the constraints that ensure that customer demand is met. 

E. Define and implement the constraints that ensure that suppliers have all ordered items in stock. 

F. Define and implement the constraints that ensure that factories order enough material to be able to manufacture all items.

 G. Define and implement the constraints that ensure that the manufacturing capacities are not exceeded.
 
  H. Define and implement the objective function. Make sure to consider the supplier bills comprising shipping and material costs , the production cost of each factory , and the cost of delivery to each customer.

 I. Solve the linear program and determine the optimal overall cost.

 J. Determine for each factory how much material has to be ordered from each individual supplier.
 
 K. Determine for each factory what the supplier bill comprising material cost and delivery will be for each supplier.
 
 L. Determine for each factory how many units of each product are being manufactured. Also determine the total manufacturing cost for each individual factory.

 M. Determine for each customer how many units of each product are being shipped from each factory. Also determine the total shipping cost per customer N. Determine for each customer the fraction of each material each factory has to order for manufacturing products delivered to that particular customer. Based on this calculate the overall unit cost of each product per customer including the raw materials used for the manufacturing of the customer’s specific product, the cost of manufacturing for the specific customer and all relevant shipping costs.
 
Note: All constraints mentioned above are referenced in the code using comments. 
