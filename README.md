Sales vehicle Assignment 

hive> create table salestab (ordernumber string, quatityorder string , priceeach string, orderlinenumber string, sales string, status string, Qtr_id string , month_id string , year_id string , productline string, msrp string, productcode string, phone string , city string , state string, postalcode string, country string, territory string , contactlastname string, contactfirstname string, dealsize string) row format delimited fields terminated by ',';
OK
Time taken: 0.108 seconds





hive>
    >
    >
    > load data local inpath '/home/cloudera/sales.txt' into table salestab;
    
    
    
    
Loading data to table practise.salestab
Table practise.salestab stats: [numFiles=1, totalSize=360233]
OK
Time taken: 0.471 seconds






hive> select * from practise.salestab limit 10;
OK

salestab.ordernumber    salestab.quatityorder   salestab.priceeach      salestab.orderlinenumber        salestab.sales  salestab.status salestab.qtr_id salestab.month_id       salestab.year_id salestab.productline    salestab.msrp   salestab.productcode    salestab.phone  salestab.city   salestab.state  salestab.postalcode     salestab.country        salestab.territory       salestab.contactlastname        salestab.contactfirstname       salestab.dealsize
ORDERNUMBER     QUANTITYORDERED PRICEEACH       ORDERLINENUMBER SALES   STATUS  QTR_ID  MONTH_ID        YEAR_ID PRODUCTLINE     MSRP    PRODUCTCODE     PHONE   CITY    STATE   POSTALCODE       COUNTRY TERRITORY       CONTACTLASTNAME CONTACTFIRSTNAME        DEALSIZE
10107   30      95.7    2       2871    Shipped 1       2       2003    Motorcycles     95      S10_1678        2125557818      NYC     NY      10022   USA     NA      Yu      Kwai    Small
10121   34      81.35   5       2765.9  Shipped 2       5       2003    Motorcycles     95      S10_1678        26.47.1555      Reims           51100   France  EMEA    Henriot Paul    Small
10134   41      94.74   2       3884.34 Shipped 3       7       2003    Motorcycles     95      S10_1678        +33 1 46 62 7555        Paris           75508   France  EMEA    Da CunhaDaniel   Medium
10145   45      83.26   6       3746.7  Shipped 3       8       2003    Motorcycles     95      S10_1678        6265557265      Pasadena        CA      90003   USA     NA      Young   Julie    Medium
10159   49      100     14      5205.27 Shipped 4       10      2003    Motorcycles     95      S10_1678        6505551386      San Francisco   CA              USA     NA      Brown   Julie    Medium
10168   36      96.66   1       3479.76 Shipped 4       10      2003    Motorcycles     95      S10_1678        6505556809      Burlingame      CA      94217   USA     NA      Hirano  Juri     Medium
10180   29      86.13   9       2497.77 Shipped 4       11      2003    Motorcycles     95      S10_1678        20.16.1555      Lille           59000   France  EMEA    Rance   Martine Small
10188   48      100     1       5512.32 Shipped 4       11      2003    Motorcycles     95      S10_1678        +47 2267 3215   Bergen          N 5804  Norway  EMEA    Oeztan  Veysel  Medium
10201   22      98.57   2       2168.54 Shipped 4       12      2003    Motorcycles     95      S10_1678        6505555787      San Francisco   CA              USA     NA      Murphy  Julie    Small
Time taken: 0.082 seconds, Fetched: 10 row(s)





hive>
    >
    >
    >
    >
    >
    >
    >
    > select sum(quatityorder) as totalsales from salestab;
Query ID = cloudera_20220928091111_fea2a745-a059-4be3-9a6d-a85837b47e51
Total jobs = 1
Launching Job 1 out of 1
Number of reduce tasks determined at compile time: 1
In order to change the average load for a reducer (in bytes):
  set hive.exec.reducers.bytes.per.reducer=<number>
In order to limit the maximum number of reducers:
  set hive.exec.reducers.max=<number>
In order to set a constant number of reducers:
  set mapreduce.job.reduces=<number>
Starting Job = job_1664379406561_0001, Tracking URL = http://quickstart.cloudera:8088/proxy/application_1664379406561_0001/
Kill Command = /usr/lib/hadoop/bin/hadoop job  -kill job_1664379406561_0001
Hadoop job information for Stage-1: number of mappers: 1; number of reducers: 1
2022-09-28 09:11:50,548 Stage-1 map = 0%,  reduce = 0%
2022-09-28 09:11:59,606 Stage-1 map = 100%,  reduce = 0%, Cumulative CPU 1.28 sec
2022-09-28 09:12:10,748 Stage-1 map = 100%,  reduce = 100%, Cumulative CPU 2.8 sec
MapReduce Total cumulative CPU time: 2 seconds 800 msec
Ended Job = job_1664379406561_0001
MapReduce Jobs Launched:
Stage-Stage-1: Map: 1  Reduce: 1   Cumulative CPU: 2.8 sec   HDFS Read: 370181 HDFS Write: 8 SUCCESS
Total MapReduce CPU Time Spent: 2 seconds 800 msec
OK
    
    
totalsales
99067.0
