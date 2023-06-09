# Home_sales challenge
# The Dataset
A Spark DataFrame is created from the dataset

![Screenshot 2023-04-11 235114](https://user-images.githubusercontent.com/115653868/231305518-0cf46773-f792-41da-87c8-7c8afd14092d.png)



# QUERIES

A query is written that returns the average price, rounded to two decimal places, for a four-bedroom house that was sold in each year. 

![Screenshot 2023-04-11 235501](https://user-images.githubusercontent.com/115653868/231306147-35efb45a-1eee-4e2a-9ed7-339df09aca14.png)

A query is written that returns the average price, rounded to two decimal places, of a home that has three bedrooms and three bathrooms. 


A query is written that returns the average price of a home with three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet for each year built rounded to two decimal places. 

A query is written that returns the view rating for the average price for homes that are greater than or equal to $350,000, rounded to two decimal places. 

start_time = time.time()
spark.sql("""
SELECT ROUND(AVG(view), 2) AS avg_view
FROM home
WHERE price >= 350000
""").show()
print("--- %s seconds ---" % (time.time() - start_time))


A cache of the temporary "home_sales" table is created and validated. 

The query from step 6 is run on the cached temporary table, and the run time is computed. 

A partition of the home sales dataset by the "date_built" field is created, and the formatted parquet data is read. 

A temporary table of the parquet data is created. 

The query from step 6 is run on the parquet temporary table, and the run time is computed. 

The "home_sales" temporary table is uncached and verified. 



