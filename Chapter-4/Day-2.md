
1. Instead of console logging the result after the script executes, I want you to:
 - Make a new variable named greeting using useState
 - Set the greeting variable to the response of the script call
 - Create a <p> tag after the <div className={styles.flex}> tag
 - Put the greeting variable inside of that <p> tag. This will make the result of your script show on your webpage! It should look something like this:

2a. I deployed a contract called SimpleTest to an account with an address of 0x6c0d53c676256e8c. I want you to make a button that, when clicked, executes   a script to read the number variable from that contract. If you're curious, you can see the contract here: https://flow-view-                             source.com/testnet/account/0x6c0d53c676256e8c/contract/SimpleTest

Submit all the code you used to call the script, and the result of the script.

 - Result of that script is ->  11

```

import * as fcl from "@onflow/fcl";
import * as t from "@onflow/types";
import Head from "next/head";
import { useEffect } from "react";
import { useState } from "react";
import Navbar from "./Navbar";

import styles from "../styles/Home.module.css";

const Home = () => {
  const [greeting, setGreeting] = useState("");
  const [newGreeting, setNewGreeting] = useState("");
  

  async function executeScript() {
    const response = await fcl.query({
      cadence: `
    import HelloWorld from 0x6c0d53c676256e8c

    pub fun main(): String {
        return SimpleTest.number
    }
    `,
      args: (arg, t) => [],
    });

   
    setGreeting(response);
  }




  return (
    <div className={styles.container}>
      <Navbar />
      <Head>
        <title>Duck DApp</title>
        <meta name="description" content="Created by Emerald Academy" />
        <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
      </Head>

      <main className={styles.main}>
        <h1 className={styles.title}>
          Welcome to my{" "}
          <a href="#" target="_blank">
            Duck DApp!
          </a>
        </h1>
      </main>
      <main
        style={{
          display: "flex",
          alignItems: "center",
          flexDirection: "column",
          justifyContent: "center",
          marginTop: "40px",
        }}
      >
        {/* <h3>Dapp by Jacob Tucker </h3> */}
        <p
          style={{
            padding: "100px 200px",
            color: "white",
            border: "2px solid #35e9c6",
            backgroundColor: "#176f6c",
          }}
        >
          {greeting}
        </p>
        <div
          style={{
            display: "flex",
            flexDirection: "column",
            marginTop: "7px",
            alignItems: "center",
            justifyContent: "space-around",
          }}
        >
          <input
            style={{ marginBottom: "8px", padding: "5px 10px" }}
            placeholder="Change..."
            value={newGreeting}
            onChange={(e) => setNewGreeting(e.target.value)}
            type="text"
          />
          <button
            style={{
              width: "150px",
              padding: "9px 12px",
              // fontWeight: "bold",
              fontSize: "15px",
              border: "none",
              backgroundColor: "rgb(163, 15, 52)",
              borderRadius: "4px",
              color: "white",
              cursor: "pointer",
            }}
            onClick={executeScript}
          >
           <P>{greeting}</P>
          </button>
        </div>
      </main>
    </div>
  );
};

export default Home;

```


2b. Then, I want you to remove the button, and make the script execute every time the page refreshes.

    Submit all the code you used to do this.
    
    
  --> Simply we need to use useEffect, and call that function in useEffect instead of onClick
    
  
```

import * as fcl from "@onflow/fcl";
import * as t from "@onflow/types";
import Head from "next/head";
import { useEffect } from "react";
import { useState } from "react";
import Navbar from "./Navbar";

import styles from "../styles/Home.module.css";

const Home = () => {
  const [greeting, setGreeting] = useState("");
  const [newGreeting, setNewGreeting] = useState("");
  

  async function executeScript() {
    const response = await fcl.query({
      cadence: `
    import HelloWorld from 0x6c0d53c676256e8c

    pub fun main(): String {
        return SimpleTest.number
    }
    `,
      args: (arg, t) => [],
    });

   
    setGreeting(response);
  }
  

 useEffect(() => {
    executeScript();
  }, []);
 

  return (
    <div className={styles.container}>
      <Navbar />
      <Head>
        <title>Duck DApp</title>
        <meta name="description" content="Created by Emerald Academy" />
        <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
      </Head>

      <main className={styles.main}>
        <h1 className={styles.title}>
          Welcome to my{" "}
          <a href="#" target="_blank">
            Duck DApp!
          </a>
        </h1>
      </main>
      <main
        style={{
          display: "flex",
          alignItems: "center",
          flexDirection: "column",
          justifyContent: "center",
          marginTop: "40px",
        }}
      >
        {/* <h3>Dapp by Jacob Tucker </h3> */}
        <p
          style={{
            padding: "100px 200px",
            color: "white",
            border: "2px solid #35e9c6",
            backgroundColor: "#176f6c",
          }}
        >
          {greeting}
        </p>
        <div
          style={{
            display: "flex",
            flexDirection: "column",
            marginTop: "7px",
            alignItems: "center",
            justifyContent: "space-around",
          }}
        >
          <input
            style={{ marginBottom: "8px", padding: "5px 10px" }}
            placeholder="Change..."
            value={newGreeting}
            onChange={(e) => setNewGreeting(e.target.value)}
            type="text"
          />
          
           <P>{greeting}</P>
          </button>
        </div>
      </main>
    </div>
  );
};

export default Home;

```
