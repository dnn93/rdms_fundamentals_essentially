A **transaction** is a logical, atomic unit of work that contains one or more SQL statements. A transaction groups SQL statements so that they are either all **committed**, which means they are applied to the database, or all **rolled back**, which means they are undone from the database.

![transaction](./img/transaction.gif)

A transaction has four basic key properties - known as **ACID properties** - is an acronym for the following:
- **Atomicity** All tasks of a transaction are performed or none of them are. There are no partial transactions.
For example, in an application that transfers funds from one account to another, the atomicity property ensures that, if a debit is made successfully from one account, the corresponding credit is made to the other account.

- **Consistency** Data is in a consistent state when a transaction starts and when it ends.
For example, in an application that transfers funds from one account to another, the consistency property ensures that the total value of funds in both the accounts is the same at the start and end of each transaction.

- **Isolation** The intermediate state of a transaction is invisible to other transactions. As a result, transactions that run concurrently appear to be serialized.
For example, in an application that transfers funds from one account to another, the isolation property ensures that another transaction sees the transferred funds in one account or the other, but not in both, nor in neither.

- **Durability** After a transaction successfully completes, changes to data persist and are not undone, even in the event of a system failure.
For example, in an application that transfers funds from one account to another, the durability property ensures that the changes made to each account will not be reversed.

To assure the ACID properties of a transaction, any changes made to data in the course of a transaction must be **committed** or **rolled back**.
- When a transaction completes normally, a transaction processing system *commits* the changes made to the data; that is, it makes them permanent and visible to other transactions.

- When a transaction does not complete normally, the system *rolls back* (or backs out) the changes; that is, it restores the data to its last consistent state.

Resources that can be rolled back to their state at the start of a transaction are known as *recoverable resources*: resources that cannot be rolled back are *nonrecoverable*. 

Ref: 
[postgres 13](https://www.postgresql.org/docs/13/tutorial-transactions.html) , [mysql 8](https://dev.mysql.com/doc/refman/8.0/en/sql-transactional-statements.html)