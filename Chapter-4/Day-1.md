1. How did we get the address of the user? Please explain in words and then in code.

  - we put a onClick function  on a button and then user will login through that. (there will be some login in onClick func with fcl and js)
  -  when user will login their address wll store in "user" and then we can get like this "user.addr"
  
  
2. What do fcl.authenticate and fcl.unauthenticate do?

 - with fcl.authenticate a user can login with their wallet.
 - with fcl.unauthenticate a user can logout from their account.

3. Why did we make a config.js file? What does it do?

 - We make config.js for various reasons like 
 - with config.js we can connect our dapp with testnet.
 - config.js allow us to connect with Blocto, lilico and Nufi wallet


4. What does our useEffect do?

  - Use effect will execute functons which are inside it , if we keep dependency "[]" empty useEffect will run on page on starting and refresh.
  - if we put a variable inside dependency [] then useEffect will run eachtime when our variable value change.
 
5. How do we import FCL?

 - import * as fcl from "@onflow/fcl";
 
6. What does fcl.currentUser.subscribe(setUser); do?

 - It wll make sure that user will not logout if he refresh page, if we dont do "fcl.currentUser.subscribe(setUser)" user have to login each time after he    refresh his page
