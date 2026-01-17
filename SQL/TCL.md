Transactions group a set of tasks into a single execution unit. Each transaction begins with a specific task and ends when all the tasks in the group are successfully completed. If any of the tasks fail, transaction fails. Therefore, a transaction has only two results: success or failure.

|Command|Description|Syntax|
|---|---|---|
|BEGIN TRANSACTION|Starts a new transaction|BEGIN TRANSACTION [transaction_name];|
|COMMIT|Saves all changes made during the transaction|COMMIT;|
|ROLLBACK|Undoes all changes made during the transaction|ROLLBACK;|
|SAVEPOINT|Creates a savepoint within the current transaction|SAVEPOINT savepoint_name;|
