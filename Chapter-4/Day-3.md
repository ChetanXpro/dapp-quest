1. Write a function that executes a script with all the Cadence types that we reviewed today. Call the script when the page refreshes. Return something        random from the Cadence script, and console log it to prove to me your script actually worked.


  ```
    async function executeScript() {
    const response = await fcl.query({
      cadence: `
      pub fun main(
        a: Int, 
        b: String, 
        c: UFix64, 
        d: Address, 
        e: Bool,
        f: String?,
        g: [Int],
        h: {String: Address}
      ):String {

        return b
        
      }
      `,
      args: (arg, t) => [
        arg("6", t.Int),
        arg("btw nice try", t.String),
        arg("34.0", t.UFix64),
        arg("0x3a822511e225831b", t.Address),
        arg(false, t.Bool),
        arg(null, t.Optional(t.String)),
        arg(["8", "7", "4"], t.Array(t.Int)),
        arg(
          [
            { key: "blocto", value: "0x2d4c3caffbeab845" },
            { key: "lilco", value: "0x39e42c67cc851cfb" },
          ],
          t.Dictionary({ key: t.String, value: t.Address })
        ),
      ],
    });
    console.log(response);
  }

  useEffect(() => {
    executeScript();
  }, []);
  ```

 ![exp](https://user-images.githubusercontent.com/107798155/195879130-4f18eff2-d059-4f91-a372-7eb8405fe60e.png)

