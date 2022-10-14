1. I deployed a contract called SimpleTest to an account with an address of 0x6c0d53c676256e8c. I want you to make a button that, when clicked, sends a        transaction to change the number variable from that contract. If you're curious, you can see the contract here: https://flow-view-                          source.com/testnet/account/0x6c0d53c676256e8c/contract/SimpleTest

2. Immediately after you send the transaction, wait for the transaction to be "Sealed" just like we did today. Then, call a script to read the number        from the contract. Console log the result.

- Script result: 69

```
async function executeScript() {
    const response = await fcl.query({
      cadence: `
    import SimpleTest from 0x6c0d53c676256e8c

    pub fun main(): Int {
        return SimpleTest.number
    }
    `,
      args: (arg, t) => [],
    });

    console.log("Response from our script: " + response);
    setGreeting(response);
  }

  const runTransaction = async () => {
    // setIsLoading(true);
    const transactionId = await fcl.mutate({
      cadence: `
      import SimpleTest from 0x6c0d53c676256e8c

transaction(newNumber: Int) {

  prepare(signer: AuthAccount) {}

  execute {
    SimpleTest.updateNumber(newNumber: newNumber)
  }
}
 
      `,
      args: (arg, t) => [arg("69", t.Int)],
      proposer: fcl.authz,
      payer: fcl.authz,
      authorizations: [fcl.authz],
      limit: 999,
    });

    await fcl.tx(transactionId).onceSealed();
    executeScript();
  };

```
