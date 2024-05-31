# SQL and Databases ETL examples
## Project overview
This project refers to creating SQL queries to solve specific business questions, based on Adventureworks 2005 database hosted in BigQuery project.
The schema of the Adventureworks 2005 database can be accessed [here]( https://i0.wp.com/improveandrepeat.com/wp-content/uploads/2018/12/AdvWorksOLTPSchemaVisio.png?ssl=1)

## Tasks
### Task 1.1. Customers overview
Create a detailed overview of all individual customers (these are defined by customerType = ‘I’ and/or stored in an individual table). Write a query that provides:

Identity information : CustomerId, Firstname, Last Name, FullName (First Name & Last Name).
An Extra column called addressing_title i.e. (Mr. Achong), if the title is missing - Dear Achong.
Contact information : Email, phone, account number, CustomerType.
Location information : City, State & Country, address.
Sales: number of orders, total amount (with Tax), date of the last order.

Solution: [1.1. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/1.1.%20query)

### Task 1.2. No orders in 365 days
Get the data from the first query for the top 200 customers with the highest total amount (with tax) who have not ordered for the last 365 days.

Solution: [1.2. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/1.2.%20query)

### Task 1.3. Active and Inactive customers
Enrich your original 1.1 SELECT by creating a new column in the view that marks active & inactive customers based on whether they have ordered anything during the last 365 days.

Solution: [1.3. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/1.3.%20query)

### Task 1.4. North America
Business would like to extract data on all active customers from North America. Only customers that have either ordered no less than 2500 in total amount (with Tax) or ordered 5 + times should be presented.

In the output for these customers divide their address line into two columns, i.e.:

AddressLine1	address_no	Address_st
'8603 Elmhurst Lane'	8603	Elmhurst Lane
Order the output by country, state and date_last_order.

Solution: [1.4. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/1.4.%20query)

### Task 2.1. Sales by territory
Create a query of monthly sales numbers in each Country & region. Include in the query a number of orders, customers and sales persons in each month with a total amount with tax earned. Sales numbers from all types of customers are required. 

Solution: [2.1. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/2.1.%20query)

### Task 2.2. Cumulative sum
Enrich 2.1 query with the cumulative_sum of the total amount with tax earned per country & region.

Solution: [2.2. query](https://github.com/PatrycjaDanilczuk/SQL-and-Databases-codes/blob/main/2.2.%20query)

### Task 2.3. Sales rank
Enrich 2.2 query by adding ‘sales_rank’ column that ranks rows from best to worst for each country based on total amount with tax earned each month. I.e. the month where the (US, Southwest) region made the highest total amount with tax earned will be ranked 1 for that region and vice versa.

Solution: [2.3. query]

### Task 2.4. Taxes
Enrich 2.3 query by adding taxes on a country level:

As taxes can vary in country based on province, the needed column is ‘mean_tax_rate’ -> average tax rate in a country.
Also, as not all regions have data on taxes, you also want to be transparent and show the ‘perc_provinces_w_tax’ -> a column representing the percentage of provinces with available tax rates for each country (i.e. If US has 53 provinces, and 10 of them have tax rates, then for US it should show 0,19)
Hint: If a state has multiple tax rates, choose the higher one. Do not double count a state in country average rate calculation if it has multiple tax rates.

Solution: [2.4. query]

