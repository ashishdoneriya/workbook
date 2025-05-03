---
title: "Some Important hive syntax"
date: 2019-08-06T03:17:00+05:30
date: 2019-08-06T03:17:00+05:30
tags:
  - hive
categories: 
  - big data
description: "Some Important hive syntax"
url: /important-hive-syntax.html
---

## Partitions

First set these properties

```sql
SET hive.exec.dynamic.partition = true;
SET hive.exec.dynamic.partition.mode = nonstrict;
```

### How to create partitioned table
```sql
create table c1_part (id int, name string, email string) partitioned by (countrycode string);
```

### How to insert data into partitioned table
```sql
insert into table c1_part partition(countrycode) select c1.id, c1.name, c1.email, c1.countrycode from c1;
```

### How to analyze paritioned tables
```sql
analyze table tableName partition(partitionName) compute statistics noscan;
```


## Bucketing

```sql
set hive.mapred.mode=nonstrict;
set hive.enforce.bucketing=true;
```

```sql
create table c1_buck (id int, name string, email string, countrycode string) clustered by (id) into 10 buckets;
```

### How to insert data into bucketed table
```sql
insert overwrite into table c1_buck select c1.id, c1.name, c1.email, c1.countrycode from c1;
```

## Both Partitioning and Bucketing

```sql
SET hive.exec.dynamic.partition = true;
SET hive.exec.dynamic.partition.mode = nonstrict;
set hive.mapred.mode=nonstrict;
set hive.enforce.bucketing=true;
create table c1_part_buck (id int, name string, email string) partitioned by (countrycode string) clustered by (id) into 10 buckets;
insert into table c1_part_buck partition(countrycode) select c1.id, c1.name, c1.email, c1.countrycode from c1;
```

### For transactional tables
```sql
set hive.compactor.initiator.on = true;
set hive.support.concurrency = true;
set hive.txn.manager = org.apache.hadoop.hive.ql.lockmgr.DbTxnManager;
```
