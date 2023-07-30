# Operations on a Dataset

## Agenda

1. Joins
2. Relationships
3. Multiple Connection and Cross Dataset Joins
4. Multiple Data Sources
5. Blending



## Concepts

* Handle Multiple Dataset
  * Joins
  * Unions
  * Relationships


### **Join**
* With Exel and Google sheets we can visualize data but we can't join data from multiple tables across different datasources. This is where tools like Tableu shines.
* Joins
    * Inner Join
    * Left Outer Join
    * Right Outer Join
    * Full Outer Join

* While joining, the dimensions and measures gets split up by table name

* Find actual sales for year 2017 where actual sales means total sales - returned sales

    `actual sales = total sales - returned sales`

* From the joined data find the total number of returned orders

* Find total sales
    
    While doing left join if there are duplicate row on the right table, due to duplication we can't reliably use measures

* Aggration calculation may be incorrect for direct table queries inacse of joins in tableau
    
    If you join the dataset, queries on individual table or the original table will not work.
    If you join two tables - you can't directly use original table for your calculations as duplications may affect all aggregations

    So while using joined table try using atleast one field from each table for aggregation functions to work correctly, else take a different approach.


### Relationships

* The main difference between join and relationship is that with Relationships data is only joined if needed.
* This means if we are using aggregate functions on a single table, the same will work(as data would not be joined)
* With relationship it's full join.
* To use Right join, Left Join and Inner join we apply filters accordingly.

## Difference and usage: Joins vs Relationships
* If you are using fields from both tables use joins, if you are using fields from just one of the tables use relationsips.


* Find Product with highest sales
* Find order with multiple products and corresponding users


## Unions
* Merging data vertically
* Drop table on top of another table, this will create union



## Connection vs Datasource

* Connection: used to connect to a database(csv, postgres)
* Datasource: place from where tableau sheets read the data.
  * filtering
  * live vs exrtact
  * joins
  * unions

    all of these happens at datasource level.

* Multiple Connection

    * A data source may have multiple connections.
    * The sheets and dashboard reference the datasource(not the connection)
    * **Cross Dataset joins**: If you are using Join across connection, then it's called a cross-dataset join.
    * If we need a single join type, then we go for multiple connections
        * For each country find their co2 emission and number of medals won in olympics
            * join co2 data +  olympics data

* Multiple Datasources
    * Here there will be multiple data source
    * each data source will have one or more connections
    * when we have multiple type join types we can go for Multiple Data source
        * For each country find their co2 emission and number of medals won in olympics
        * join co2 data +  olympics data
        * Find co2 emission and orders in US for the same year
            * join co2 data +  orders data
        * Find olympics medals abd order every year for usa
            * join olympics data +  orders data


* Two connect DB: usually go with multiple connection. 
  * Example where there is a relation among the tables Orders, Products, Sales
* Two disconnected DBs: usually go with multiple datasources
    * Example where there is no relation among the tables Sales, Olympic Medals


* Benefit of Datasource over connection
  * Incase your backend db changes, it's easier to change the datasource rather than connections.

### Data Blending
 * This happens at differnt datasources
 * Data Blending is always left join
 * if both table has exactly same name , insome cases tableu might show the link symbol.
 * Data -> blending

 * joins vs blends
    * joins happens at the same source. all type of joins avaiable. single granularity
    * blends happen at multiple datasource. only left join. multiple granularity.


## Industry
* When we have multiple table, 90% of the type data blending(multiple data sources) are used
* Rent 7% Relationships are used
* 3-5% of the cases Joins are used

