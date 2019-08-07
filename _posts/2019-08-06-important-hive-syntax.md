---
title: "Some Important hive syntax"
date: 2019-08-06T03:17:00+05:30
date: 2019-08-06T03:17:00+05:30
draft: false
tags: ["hive"]
categories: ["big-data"]
toc: false
autoCollapseToc: false
summary: "Some Important hive syntax"
---

```sql
analyze table tableName partition(partitionName) compute statistics noscan;
```

```sql
set hive.mapred.mode=nonstrict;
```

```sql
set hive.enforce.bucketing=true;
```

```sql
SET hive.exec.dynamic.partition = true;
SET hive.exec.dynamic.partition.mode = nonstrict;
```

### Inserting data to partitioned table

```sql
insert into table c1_part_buck partition(countrycode) select c1.id, c1.name, c1.email, c1.countrycode from c1;
```

```sql
create table c1_part_buck (id int, name string, email string) partitioned by (countrycode string) clustered by (id) into 10 buckets;
```

### Inserting data to bucketed table
```sql
insert overwrite into table c1_part_buck partition(countrycode) select c1.id, c1.name, c1.email, c1.countrycode from c1;
```

### For transactional tables
```sql
set hive.compactor.initiator.on = true;
set hive.support.concurrency = true;
set hive.txn.manager = org.apache.hadoop.hive.ql.lockmgr.DbTxnManager;
```
