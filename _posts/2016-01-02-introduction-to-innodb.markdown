---
layout: post
title:  "Introduction to InnoDB"
date:   2016-01-02 12:00:00
categories: mysql
---

## Introduction to InnoDB

InnoDB is a general-purpose storage engine that balances high reliability and high performance. In MySQL 5.7, InnoDB is the default MySQL storage engine. Issuing the CREATE TABLE statement without an ENGINE= clause creates an InnoDB table. 

### Key Advantages of InnoDB

Key advantages of InnoDB tables include: 

- Its DML operations follow the **ACID** model, with transactions featuring **commit**, **rollback**, and **crash-recovery** capabilities to protect user data. 
- Row-level locking and Oracle-style **consistent reads** increase multi-user concurrency and performance. 
- InnoDB tables arrange your data on disk to optimize queries based on primary keys. 
- To maintain data integrity, InnoDB also supports FOREIGN KEY constraints. With foreign keys, inserts, updates, and deletes are checked to ensure they do not result in inconsistencies across different tables. 
- You can freely mix InnoDB tables with tables from other MySQL storage engines, even within the same statement. For example, you can use a join operation to combine data from InnoDB and MEMORY tables in a single query. 
- InnoDB has been designed for CPU efficiency and maximum performance when processing large data volumes.

The InnoDB storage engine maintains its own buffer pool for caching data and indexes in main memory. By default, with the **innodb_file_per_table** setting enabled, each new InnoDB table and its associated indexes are stored in a separate file. When the **innodb_file_per_table** option is disabled, InnoDB stores tables and indexes in the single system tablespace, which may consist of several files (or raw disk partitions). As of MySQL 5.7.6, InnoDB tables can also be stored in general tablespaces, which are shared tablespaces that can store data for multiple tables. InnoDB tables can handle large quantities of data, even on operating systems where file size is limited to 2GB. 

To compare the features of InnoDB with other storage engines provided with MySQL, see the Storage Engine Features table in [Alternative Storage Engines](/mysql/2016/01/03/alternative-storage-engines.html)


