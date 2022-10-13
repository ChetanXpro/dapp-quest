1. Change the printHello function to be called runTransaction.
2. Change the "Hello" text inside the button to "Run Transaction".
3. Inside the runTransaction function, add some code to console log your newGreeting variable to the developer console.
4. Go back to your webpage, type something into the input box, and press "Run Transaction". Open your developer console and you will see some thing being    printed!






```
import { useState } from "react";

import Head from "next/head";
import Nav from "../components/Nav.jsx";
import styles from "../styles/Home.module.css";

export default function Home() {
  const [newGreeting, setNewGreeting] = useState("");

  function runTransaction() {
    console.log(newGreeting);
  }
  function printGoodbye() {
    console.log("Goodbye.");
  }
  return (
    <div className={styles.container}>
      <Head>
        <title>Emerald DApp</title>
        <meta name="description" content="Created by Emerald Academy" />
        <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
      </Head>

      <Nav />

      <main className={styles.main}>
        <h1 className={styles.title}>
          Welcome to my{" "}
          <a href="https://academy.ecdao.org" target="_blank">
            Emerald DApp!
          </a>
        </h1>
        <p>This is a DApp created by Jacob tucker.</p>

        <div className={styles.flex}>
          <button onClick={runTransaction}>Run Transaction</button>
          <input
            onChange={(e) => setNewGreeting(e.target.value)}
            placeholder="Hello, Idiots!"
          />
        </div>
      </main>
    </div>
  );
}


```


![Screenshot from 2022-10-13 16-35-55](https://user-images.githubusercontent.com/107798155/195580836-b53336c5-22b8-4bbf-96a3-4f30dd846d1f.png)
