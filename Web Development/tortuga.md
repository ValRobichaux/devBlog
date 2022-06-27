# Tortuga

## Tortuga is a web3 project my close friend is working on.

### This project involves
* Next.js
* Chakra-ui

- - - - 

## File structure

File structure remains relatively the same from my projects that I have done in the past, keeping my componenets compartmentalized so that it's easy for me as a dev to understand where all of my content regarding certain components are.

``` html
    <div className={styles.container}>
    </div>
  </div>
  )
```

I did not truly understand what curly braces meant when using it this way, but I looked into the css file to understand that they are actually evaluating the expression `styles.container`

Looking into this a bit further we can see in the css files that there is a method conveniently called 

``` css 
.container {
  padding: 0 2rem;
}
```

which gives that previous div all of its attributes.  Very neat.
