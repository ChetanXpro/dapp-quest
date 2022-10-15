1. List all the possible transaction status codes and what each of them mean.

 - 0  ->	Unknown
 - 1	 ->	Transaction Pending - Awaiting Finalization
 - 2	 ->	Transaction Finalized - Awaiting Execution
 - 3	 ->	Transaction Executed - Awaiting Sealing
 - 4	 ->	Transaction Sealed - Transaction Complete. At this point the transaction result has been committed to the blockchain.
 - 5	 ->	Transaction Expired


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
 
 3. What does the fcl.tx(transactionId).subscribe(res => {...}) function do?

  - This will give us updated status code accoding to transaction status in res=>{...}

  - Like if our transacton is pending it will give status code -> 1


4. Make at least 3 changes to the styling of the application. It can be anything (part of this quest is being creative!). List the 3 changes and point      them out in a screenshot.

  - Make seprate container for user address, Also user will see a logout button to logout

   ![Screenshot from 2022-10-14 21-32-16](https://user-images.githubusercontent.com/107798155/195975551-81d26547-0623-4b6b-ae4e-31751e826e73.png)
   
   
   
  -  Added a button to Show and hide transaction id , it will show last transdaction id of their transacton.
  
  -  In transacton id container user can see another button to view more info about transacton , it will redirect user to flow testnet scan website 
     with their transacton id 

   ![redirect](https://user-images.githubusercontent.com/107798155/195975588-bce3d80c-bd96-48bd-bb0a-9f3a8ff89e9a.png)
   
   
  - Now user can see time Taken by  transaction. user can see time just after their transaction sealed .
   
   ![tme](https://user-images.githubusercontent.com/107798155/195976350-aed09e86-752e-409d-9cb0-24df51a7a7da.png)
   
   
   - Added some Toast.
   
   a. User will get a success notification after transacton sealed.
   b. User will see a warning if he/she try to view transacton id before login.
   c. User will get a warning if he/she try to view transaction id before even doing a transaction.
   
   a. ![seal](https://user-images.githubusercontent.com/107798155/195975594-ed8135b9-ae12-41c4-bda2-4507c3d340f6.png)
   
   b. ![warn](https://user-images.githubusercontent.com/107798155/195976696-4f0bebc2-4723-45ff-aabd-870dee036a5f.png)
   
   c. ![nohistory](https://user-images.githubusercontent.com/107798155/195976716-2b26dc15-ff9b-48e0-bbd7-5d7209a856bd.png)

   

  

