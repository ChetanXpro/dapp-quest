1.Explain why we wouldn't call changeGreeting in a script.
 
 - because we can only view data with script , to call changeGreeting we have to use transaction.
 
 
2.What does the AuthAccount mean in the prepare phase of the transaction?

 - AuthAccount is used to access data stored in that account, and it represent the account which sending the transaction.


3.What is the difference between the prepare phase and the execute phase in the transaction?

  - In prepare phase we can access user data and can store data and can also execute functions
  - In execute phase we can only call functions we cant access user data.
 

4. This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.


  - Add two new things inside your contract:

  - A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
  - A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber
  - Add a script that reads myNumber from the contract

  - Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by         running   the script again.
 
  
 
 ![contract](https://user-images.githubusercontent.com/107798155/195583504-c12071c9-5e2b-4052-b31f-6b85a2b7fa3a.png)
 
 ![sc](https://user-images.githubusercontent.com/107798155/195583517-d755ebaf-c428-45b0-b14b-edbc8e2e35b2.png)

 ![tr](https://user-images.githubusercontent.com/107798155/195583525-b3455363-81e8-4257-92f0-d51f2d2d0088.png)
