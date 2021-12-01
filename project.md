## Deadline

Upload the report to Moodle: 

**Apprentis:** 19/12/2021 

**Others:** 02/01/2022 

## Environment

You will do the project in Zeppelin notebooks on Hadoop.

- Connect to VPN.
- Connect to Adaltas' cluster (through Putty or some other tool you are using).
- Go to the link `http://zep-1.au.adaltas.cloud:9995/`
- In the folder `ece-2021/spark/project`find your group (`bda-gr01`, `bda-gr02`, `si-gr01`, `si-gr02`).
- Inside the correct group, create a notebook with your last name.
- Go to `Permissions` (lock icon in top right corner) an put `petra` as Readers and Runners.

## General instructions

**Important:** Apprentis don't need to answer the questions 14 and 15. Those answers will count as bonus points. 

- The project can be carried out by 1 or 2 students.
- Each group needs to turn in one report in pdf format and a link to **one** notebook included to the report. The notebook should be clean and readable.
- If you want to work with your peer in one notebook, add him/her in the `Permissions` to all the levels.
- If you add the tables to the report, they shouldn't be longer than 10 rows.


- Documentation: https://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html

## Questions
 
You will be exploring NYC Taxi data. They consist of two datasets, Taxi fares and Taxi rides. The locations of the data are given, and also are the schemas.

1. Open the dataset Taxi fares:

- hdfs:///education/ece/spark/labs/2/nycTaxiFares.gz
- format: csv
- schema: 
    - 'ride_id', Integer
    - 'taxi_id', Integer
    - 'driver_id', Integer
    - 'start_time', Timestamp
    - 'payment_type', String
    - 'tip', Float
    - 'tolls', Float
    - 'total_fare', Float

2. How many lines are in the dataset?

3. What is the first and the last date (only date, without time)?

4. How many distinct drivers and distinct cars do we have in the dataset?

5. Are there any values that seem to be strange (in any column or as a result of aggregation)? Explain. You can also answer this question at the end of the project.

6. Calculate for each driver:

 - total number of rides
 - how much tips did he earn
 - how much did he pay for the tolls
 - how much did he charge for all the fares

7. Which driver did the most rides? Did he also earned the most tips? 

8. What % of fares represent the tips (on average)? We will consider that the tip is not included in the fares_total and you can compare them directly.

9. Do taxi drivers always drive the same car?

10. Which driver changed the most cars? How many distinct taxis did he drive?

11. Open the dataset Taxi rides:

- hdfs:///education/ece/spark/labs/2/nycTaxiRides.gz
- format: csv
- schema:
    - 'ride_id', Integer
    - 'is_start', String
    - 'end_time', Timestamp
    - 'start_time', Timestamp
    - 'start_lon', Float
    - 'start_lat', Float
    - 'end_lon', Float
    - 'end_lat', Float
    - 'passenger_count', Integer
    - 'taxi_id', Integer
    - 'driver_id', Integer

12. Join it with the Taxi Fares: inner join on the columns 'ride_id', 'start_time', 'taxi_id', 'driver_id'.

13. Keep only the lines where is_start = "END".

14. Calculate the longest and the shortest path. Write the formula you used in the report.

15. Calculate the longest and the shortest time.

16. How much time did a driver with the id 2013022317 spend driving each day?
