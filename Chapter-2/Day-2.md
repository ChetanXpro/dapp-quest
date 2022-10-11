1. Change the color of "Emerald DApp" to whatever color you want

  ```
  .heading {
  color:"red"
  }
  
  ```
2. Change the font size of the title.

  ```
  .title {
   font-size: 20px;
  }
  ```
3. Change the "Emerald DApp" link to a different link (this means messing with the <a> tag)
There are two parts.

```
    Welcome to my <a href="https://youtube.com" target="_blank">Emerald DApp!</a>
```


4a. Inside of your <main> tag, add a <p> tag and put whatever text you want in it. 

```
return (
  <div>
  <Head>
  <title>Emerald DApp</title>
  <meta name="description" content="Created by Emerald Academy" />
  <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
</Head>
<main className={styles.main}>
  <h1 className={styles.title}>
    Welcome to my <a href="https://academy.ecdao.org" target="_blank">Emerald DApp!</a>
  </h1>
  <p> flow is best </p>
</main>
  </div>
)

```

4b. Go to the .main class and add this line: flex-direction: column. Watch what it does!
 
 - this will deplay our main h1 and p in column insted of row.

```
.main {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column
}

```
