## advanced-databases-ntua: MapReduce, PySpark, HDFS, K-Means
An ML system developed with PySpark and MapReduce, that reads from HDFS a dataset of trip records from all trips completed in yellow taxis in NYC from 1/2015 to 6/2015, and finds the coordinates of the top five client-pickup locations using K-Means clustering.  

## How to run
1. Upload data in Hadoop Distributed File System (HDFS)  
```
hadoop fs -put ./yellow_tripdata_1m.csv hdfs://master:9000/yellow_tripdata_1m.csv
```
2. Install pyspark  
```
pip install pyspark
```
3. Submit task in Spark environment   
```
spark-submit map_reduce_kmeans.py
```
4. Get Results  
```
hadoop fs -getmerge hdfs://master:9000/map_reduce_kmeans.res ./map_reduce_kmeans.res
cat map_reduce_kmeans.res 
```
