The **Multi-Version Concurrency Control (MVCC)** feature allows higher concurrency than using exclusive table level or row level locks. When using MVCC in this database, delete, insert, and update operations only issue a shared lock on the table. An exclusive lock is still used when adding or removing columns, when dropping the table, and when using SELECT... FOR UPDATE. Connections only see committed data, and their own changes.

That means, if connection A updates a row but has not committed the change, connection B sees the old value. Only when the change from connection A is committed, the new value is visible to other connections (read committed). If multiple connections concurrently try to update the same row, the database waits until it can apply the change, but at most until the lock timeout expires


...to be continued

Ref: [postgres 13](https://www.postgresql.org/docs/13/mvcc.html) , [mysql 8](https://dev.mysql.com/doc/refman/8.0/en/innodb-locking-reads.html)