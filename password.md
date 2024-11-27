# Password Generator Tutorial 
```template 
function passwordGen () { 
    password = []
    letters = "" 
    for (let i = 0; i <= wordList.length - 1; i++) { 
        if (wordList.length == 1) { 
            letters = convertToText(wordList.shift()) 
            password.push("" + letters.slice(0, 1).toUpperCase() + letters.slice(1).toLowerCase()) 
            password.push(convertToText(randint(0, 100))) 
        } else { 
            letters = convertToText(wordList.shift()) 
            password.push("" + letters.slice(0, 1).toUpperCase() + letters.slice(1).toLowerCase()) 
            letters = convertToText(wordList.pop()) 
            password.push("" + letters.slice(0, 1).toUpperCase() + letters.slice(1).toLowerCase()) 
            password.push(convertToText(randint(0, 100))) 
        } 
    } 
    password.push("!") 
    game.showLongText("Password: " + password.join(""), DialogLayout.Full) 
    return password 
} 

function makePassword () { 

} 
let wordList: string[] = []
let password: string[] = []
scene.setBackgroundColor(9) 
game.setDialogFrame(img` 
    .................................................................. 
    ....33.......33...........dddd............dddd............aaa..... 
    ...a533.....393....ddddddd1111d....ddddddd1111d....3333...a35a.... 
    ...a553aaa339993.dd1111dd111111dddd1111dd111111dd.39393aaa3553aa.. 
    ..a355555a3999993d11911111111111dd11911111111111d339993a555555553. 
    .a555555333399933119991111111111111999111111111113999993a55555533. 
    .a355555333393931111911111115511111191111111551111399933a3555533.. 
    .aa355555a1333311111111111115511111111111111551111339331a55555a... 
    ...a55355a1111111111111111111111111111111111111111133311a55335a... 
    ...a5aaaaa1111191111111111111111111111111111111111111111aaa33aa... 
    ...aa3311115511111111111111111111111111111111111119111111113333... 
    ..3339331115511111111111111111111111111111111111111111551133393... 
    ..39999331111111111111111111111111111111111111111111115511399993.. 
    ..339999311111111111111111111111111111111111111111111111113399993. 
    ..399993311111111111111111111111111111111111111111111111113999933. 
    ...339331191111111111111111111111111111111111111111111119113393... 
    ....3311111111111111111111111111111111111111111111111111111133.... 
    ...dd11111111111111111111111111111111111111111111111111111111dd... 
    ...d1111111111111111111111111111111111111111111111111111111111d... 
    ..d111111111111111111111111111111111111111111111111111111111911d.. 
    .d1111551111111111111111111111111111111111111111111111111119991d.. 
    .d1111551111111111111111111111111111111111111111111111111111911d.. 
    .d1111111111111111111111111111111111111111111111111111111111111d.. 
    .d111111111111111111111111111111111111111111111111111111111111dd.. 
    ..d11111111111111111111111111111111111111111111111111111111111dd.. 
    ..dd11111111111111111111111111111111111111111111111111111111111d.. 
    ..dd111111111111111111111111111111111111111111111111111111111111d. 
    ..d1111111111111111111111111111111111111111111111111111111111111d. 
    ..d1191111111111111111111111111111111111111111111111111111551111d. 
    ..d1999111111111111111111111111111111111111111111111111111551111d. 
    ..d119111111111111111111111111111111111111111111111111111111111d.. 
    ...d1111111111111111111111111111111111111111111111111111111111d... 
    ...dd11111111111111111111111111111111111111111111111111111111dd... 
    ...dd11111111111111111111111111111111111111111111111111111111dd... 
    ...d1111111111111111111111111111111111111111111111111111111111d... 
    ..d111111111111111111111111111111111111111111111111111111111911d.. 
    .d1111551111111111111111111111111111111111111111111111111119991d.. 
    .d1111551111111111111111111111111111111111111111111111111111911d.. 
    .d1111111111111111111111111111111111111111111111111111111111111d.. 
    .d111111111111111111111111111111111111111111111111111111111111dd.. 
    ..d11111111111111111111111111111111111111111111111111111111111dd.. 
    ..dd11111111111111111111111111111111111111111111111111111111111d.. 
    ..dd111111111111111111111111111111111111111111111111111111111111d. 
    ..d1111111111111111111111111111111111111111111111111111111111111d. 
    ..d1191111111111111111111111111111111111111111111111111111551111d. 
    ..d1999111111111111111111111111111111111111111111111111111551111d. 
    ..d119111111111111111111111111111111111111111111111111111111111d.. 
    ...d1111111111111111111111111111111111111111111111111111111111d... 
    ...dd11111111111111111111111111111111111111111111111111111111dd... 
    ....3311111111111111111111111111111111111111111111111111111133.... 
    ...393311911111111111111111111111111111111111111111111191133933... 
    .339999311111111111111111111111111111111111111111111111113399993.. 
    .399993311111111111111111111111111111111111111111111111113999933.. 
    ..39999311551111111111111111111111111111111111111111111113399993.. 
    ...3933311551111111111111111111111111111111111111111155111339333.. 
    ...3333111111119111111111111111111111111111111111111155111133aa... 
    ...aa33aaa1111111111111111111111111111111111111111911111aaaaa5a... 
    ...a53355a1133311111111111111111111111111111111111111111a55355a... 
    ...a55555a1339331111551111111111111155111111111111133331a555553aa. 
    ..3355553a339993111155111111191111115511111119111139393333555553a. 
    .33555555a399999311111111111999111111111111199911339993333555555a. 
    .355555555a399933d11111111111911dd11111111111911d3999993a555553a.. 
    ..aa3553aaa39393.dd111111dd1111dddd111111dd1111dd.399933aaa355a... 
    ....a53a...3333....d1111ddddddd....d1111ddddddd....393.....335a... 
    .....aaa............dddd............dddd...........33.......33.... 
    .................................................................. 
    `) 
game.showLongText("I am going to help you pick out a new password! Please answer these questions for me", DialogLayout.Full) 
makePassword() 
passwordGen() 
music.play(music.melodyPlayable(music.powerUp), music.PlaybackMode.UntilDone) 
game.reset() 
``` 

```blockconfig.global
let wordList = 0
```

## Password Generator Tutorial @showdialog
Today you will be making a password generator!
You will code an array of words that will generate a strong password you can remember and use! 

![screen image](https://github.com/Code-Ninjas-Home-Office/camps/blob/master/images/password%20generator%20image.png?raw=true "screen image")

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

## Step 1 

Scroll down in your workspace until you see a ``||function:makePassword||`` function. 

This is where we will be putting all of our code. Once you found it go ahead and move onto the next step. 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks 
function makePassword () { 

} 
``` 

## Step 2 

Good job finding it! Now we need a place to store all the words that will go in our password. 

- Open ``||variables:Variables||`` and drag out a ``||variables: set wordList to||`` block and drag it into the ``||function:makePassword||`` function. 
- Click on **Advanced** then open ``||arrays:Arrays||`` and drag out the ``||arrays:empty array||`` block and place it inside of the ``||variables:set wordList to||`` block. 

We want to set this to be an empty array so we can later fill it with all the words we want to put into our password. 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks 
function makePassword () { 
   wordList = [] 
} 

let wordList: string[] = []
``` 

## Step 3 

Nice work. Now we need words to put into our ``||variables:wordList||``. 

- Open ``||variables:Variables||`` and click on ``||variables:Make a variable...||`` 
- Name the new variable ``||variables:color||`` and Click ``||loops:OK||`` 
- Open ``||variables:Variables||`` and drag out a ``||variables:set color to||`` block and place it below the code in the ``||function:makePassword||`` function 

This will be the first word we will add to our password.  

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks 
function makePassword () { 
   wordList = [] 
   color = 0 
} 

let wordList: string[] = []
``` 
## Step 4 

Ok now we need a way to type in any color we want.  

- Open ``||game:Game||`` and drag out an ``||game:askForString||`` block and drag it into the ``||variables:set color to||`` block.  
- In the ``||game:askForString("")||`` type in ``||game:Give me a color:||`` 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks 
function makePassword () { 
   wordList = [] 
   color = game.askForString("Give me a color") 
} 

let wordList: string[] = []
``` 
## Step 5 

Next we need to put the ``||game:user input||`` inside of our ``||variables:wordList||``. 

- Open ``||arrays:Arrays||`` and drag out a ``||arrays:list add value to end||`` block and place it below the code at the ``||function:makePassword||`` function 
- Click on ``||variables:list||`` and change it to ``||variables:wordList||`` 
- Open ``||variables:Variables||`` and drag out a ``||variable:color||`` variable and place it inside of the empty block 

This will add the color you type into wordList.  

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks
function makePassword () { 
    wordList = [] 
    color = game.askForString("Give me a color:") 
    wordList.push(color) 
} 

let wordList: string[] = []
```
## Step 6 
Test out your code so far.  

- Run the generator and click A.  
- Type in a color and see what password is generated. 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

## Step 7 

Looks good except we should add more words to the wordList to make a strong password.  

Go back and repeat Steps 3 - 6 but instead of adding a color variable, use:  

- ``||variables:animals||`` 
- ``||variables:adjectives||`` 
- ``||variables:food||`` 

This will create a longer and stronger password! 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials/blob/master/images/CN-Logo.png?raw=true "CN Logo")

```blocks 
function makePassword () { 
    wordList = [] 
    let color = game.askForString("Give me a color:") 
    wordList.push(color) 
    let animal = game.askForString("Give me an animal:") 
    wordList.push(animal) 
    let adjective = game.askForString("Give me an adjective:") 
    wordList.push(adjective) 
    let food = game.askForString("Give me a food:") 
    wordList.push(food) 
} 

let wordList: string[] = []
``` 
