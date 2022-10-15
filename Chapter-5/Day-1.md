1. List all the possible transaction status codes and what each of them mean.

 - 0	Unknown
 - 1	Transaction Pending - Awaiting Finalization
 - 2	Transaction Finalized - Awaiting Execution
 - 3	Transaction Executed - Awaiting Sealing
 - 4	Transaction Sealed - Transaction Complete. At this point the transaction result has been committed to the blockchain.
 - 5	Transaction Expired


2. 2a. What does setTimeout do? 

-> setTimeout will call the functon after specific time , which was given by us

  ```
  setTimeout(//Our functiion , //Time in millisecound);
  ```

2b. How would we change our code if we wanted the txStatus variable to reset back to its original state after 5 seconds?

 - we have to put a setTimeout function which will reset our  txStatus state 

 ```
 setTimeout(  setTxStatus('Run Transacton') , 5000);
 ```

