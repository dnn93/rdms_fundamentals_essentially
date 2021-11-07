**Table partitioning** is a data organization scheme where table data is divided across multiple storage that is called data partitions or ranges, according to values in one or more table columns. Partitioning improves performance and simplifies data management.

Partitioning has the following advantages:

- Improved manageability for large tables.
- Increased query performance through data partition elimination. For example, if a query includes date, do not look in partitions that do not include that date.
- Fast online data roll in and roll out.
- Better optimization of storage costs.
- Larger table capacity.
- Fewer rows in each partition table.
- Smaller indexes on each partition table that provide faster seeks.
- Greater scalability.

Vertical vs Horizontal Partitioning :
- Horizontal Partitioning splits rows into partitions (Range or list)
- Vertical partitioning splits columns partitions (Vertical partitioning splits columns partitions )

![index](./img/partition2.png)

**Sharding** is a database architecture pattern related to horizontal partitioning — the practice of separating one table’s rows into multiple different tables, known as partitions. Each partition has the same schema and columns, but also entirely different rows. Likewise, the data held in each is unique and independent of the data held in other partitions.

Horizontal Partitioning (HP) vs Sharding:
- HP splits big table into multiple tables in the same database
- Sharding splits big table into multiple tables across multiple database servers
- HP table name changes (or schema)
- Sharding everything is the same but server changes


Ref
- Partition: [postgres 13](https://www.postgresql.org/docs/13/ddl-partitioning.html) , [mysql 8](https://dev.mysql.com/doc/refman/8.0/en/partitioning.html)
- Sharding : TODO