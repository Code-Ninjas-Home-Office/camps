# Summer Game Jam Tutorial

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    ninja.setVelocity(0, -70)
    controller.moveSprite(ninja, 0, 0)
    music.play(music.melodyPlayable(music.knock), music.PlaybackMode.UntilDone)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
    resetPlayers()
    music.play(music.melodyPlayable(music.jumpUp), music.PlaybackMode.UntilDone)
})
info.onCountdownEnd(function () {
    music.play(music.melodyPlayable(music.buzzer), music.PlaybackMode.UntilDone)
    game.gameOver(true)
})
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
    resetPlayers()
    info.changeScoreby(1)
    music.play(music.melodyPlayable(music.zapped), music.PlaybackMode.UntilDone)
})
function resetPlayers () {
    ninja.setPosition(80, 100)
    controller.moveSprite(ninja, 50, 0)
    fruit.setVelocity(100, 0)
    fruit.setPosition(80, 25)
    fruit.setBounceOnWall(true)
}
let fruit: Sprite = null
let ninja: Sprite = null
ninja = sprites.create(assets.image`goalie`, SpriteKind.Player)
fruit = sprites.create(assets.image`fruit`, SpriteKind.Enemy)
game.showLongText("", DialogLayout.Bottom)
resetPlayers()
let end = sprites.create(assets.image`end`, SpriteKind.Player)
end.y = 0
info.setScore(0)
info.startCountdown(30)
```

```template
function resetPlayers () {
    ninja.setPosition(80, 100)
    ninja.setVelocity(0, 0)
    controller.moveSprite(ninja, 50, 0)
    fruit.setVelocity(100, 0)
    fruit.setPosition(80, 25)
    fruit.setBounceOnWall(true)
}
let ninja = sprites.create(img``, SpriteKind.Player)
let fruit = sprites.create(img``, SpriteKind.Enemy)
```
```assetjson
{
  "README.md": " ",
  "assets.json": "",
  "images.g.jres": "{\n    \"image2\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAPDwAAAAAAAPAAAADwDwAA//8A8A8AAPC//Q///w/w//8R//////////H/////////2/////8A///x/////////xH///////C//Q///w/wAP//APAPAAAAAAAAAPAPAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"goalie\"\n    },\n    \"lCaw=oU\": {\n        \"data\": \"hwQQABAAAAAAAADu7u7uDgAA7iIiIu7OAOAiREQk4s4ALkJFIiLuwgAuRCIiIiLOAC4kIkIi4s6AKGJmJiIkzGbod3cmIiLOYIZ3ZyJC4gwAZncmQuLuDABgZyIiIu4MAHZ3Zy7izgBgZ2h35+4MAIAIhnZ3zAAAAACAYGYGAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"Fruit\"\n    },\n    \"(yH_qWoYHaruUh5S8Z6{\": {\n        \"data\": \"hwSgAAUAAAAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEAEREBABERAQAREQEA\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"displayName\": \"end\"\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myImages\"\n    }\n}",
  "images.g.ts": "// Auto-generated code. Do not edit.\nnamespace myImages {\n\n    helpers._registerFactory(\"image\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"image2\":\n            case \"goalie\":return img`\n. . . . . f f f f f . . . . . . \n. . . . f f f f f f f . . . . . \n. f . f f f f f f f f f . . . . \n. . f f b f f f f f b f . . . . \n. f . f d 1 1 b 1 1 d f . . . . \n. . . f f 1 f d f 1 f f . . . . \n. . . . f f f f f f f . . . . . \n. . . . . f f f f f . . . . . . \n. . . . f f f f f f f . . . . . \n. . . f f f f f f f f f . . . . \n. . . f f f f f f f f f . . . . \n. . f . f f f f f f f . f . . . \n. . f . f f f f f f f . f . . . \n. . . . . f f f f f . . . . . . \n. . . . . f f . f f . . . . . . \n. . . . f f f . f f f . . . . . \n`;\n            case \"lCaw=oU\":\n            case \"Fruit\":return img`\n. . . . . . . 6 . . . . . . . . \n. . . . . . 8 6 6 . . . 6 8 . . \n. . . e e e 8 8 6 6 . 6 7 8 . . \n. . e 2 2 2 2 e 8 6 6 7 6 . . . \n. e 2 2 4 4 2 7 7 7 7 7 8 6 . . \n. e 2 4 4 2 6 7 7 7 6 7 6 8 8 . \ne 2 4 5 2 2 6 7 7 6 2 7 7 6 . . \ne 2 4 4 2 2 6 7 6 2 2 6 7 7 6 . \ne 2 4 2 2 2 6 6 2 2 2 e 7 7 6 . \ne 2 4 2 2 4 2 2 2 4 2 2 e 7 6 . \ne 2 4 2 2 2 2 2 2 2 2 2 e c 6 . \ne 2 2 2 2 2 2 2 4 e 2 e e c . . \ne e 2 e 2 2 4 2 2 e e e c . . . \ne e e e 2 e 2 2 e e e c . . . . \ne e e 2 e e c e c c c . . . . . \n. c c c c c c c . . . . . . . . \n`;\n            case \"(yH_qWoYHaruUh5S8Z6{\":\n            case \"end\":return img`\n1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111\n1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111\n1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111\n1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111\n1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111\n`;\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"animation\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n    helpers._registerFactory(\"song\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n",
  "main.blocks": "<xml xmlns=\"https://developers.google.com/blockly/xml\"><variables><variable type=\"KIND_SpriteKind\" id=\"G`1sFT`xGSRWFxXwQ;IF\">Player</variable><variable type=\"KIND_SpriteKind\" id=\"a-)6-d=2=VMbw]EDf)K:\">Projectile</variable><variable type=\"KIND_SpriteKind\" id=\"j$;4SDJ$Q{/$ARL6?z.y\">Food</variable><variable type=\"KIND_SpriteKind\" id=\"/lIMn6e0c]eRILNQ3W,Q\">Enemy</variable><variable id=\"v.MivLa,o+.vzswCi?h!\">ninja</variable><variable id=\"MjlcD*V;2ZIzx4{_,qzI\">fruit</variable><variable id=\"].PC#=%MoH#VUUOgq6g6\">mySprite</variable><variable id=\"#euykc-2)aGP}QkppV.m\">end</variable></variables><block type=\"pxt-on-start\" x=\"0\" y=\"0\"><statement name=\"HANDLER\"><block type=\"variables_set\"><field name=\"VAR\" id=\"v.MivLa,o+.vzswCi?h!\">ninja</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`goalie`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.image2\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"MjlcD*V;2ZIzx4{_,qzI\">fruit</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`Fruit`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.lCaw=oU\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Enemy</field></shadow></value></block></value><next><block type=\"variables_set\"><field name=\"VAR\" id=\"#euykc-2)aGP}QkppV.m\">end</field><value name=\"VALUE\"><shadow type=\"math_number\"><field name=\"NUM\">0</field></shadow><block type=\"spritescreate\"><value name=\"img\"><shadow type=\"screen_image_picker\"><field name=\"img\">assets.image`end`</field><data>{\"commentRefs\":[],\"fieldData\":{\"img\":\"myImages.(yH_qWoYHaruUh5S8Z6{\"}}</data></shadow></value><value name=\"kind\"><shadow type=\"spritekind\"><field name=\"MEMBER\">Player</field></shadow></value></block></value></block></next></block></next></block></statement></block></xml>",
  "main.ts": "let ninja = sprites.create(assets.image`goalie`, SpriteKind.Player)\nlet fruit = sprites.create(assets.image`Fruit`, SpriteKind.Enemy)\nlet end = sprites.create(assets.image`end`, SpriteKind.Player)\n",
  "pxt.json": "{\n    \"name\": \"Summer Game jam assets\",\n    \"description\": \"\",\n    \"dependencies\": {\n        \"device\": \"*\",\n        \"core\": \"*\"\n    },\n    \"files\": [\n        \"main.blocks\",\n        \"main.ts\",\n        \"README.md\",\n        \"assets.json\",\n        \"tilemap.g.jres\",\n        \"tilemap.g.ts\",\n        \"images.g.jres\",\n        \"images.g.ts\",\n        \"pxt.json\"\n    ],\n    \"targetVersions\": {\n        \"branch\": \"v1.12.53\",\n        \"tag\": \"v1.12.53\",\n        \"commits\": \"https://github.com/microsoft/pxt-arcade/commits/68ac01b09ebda8b6baba806d4b60e80553848600\",\n        \"target\": \"1.12.53\",\n        \"pxt\": \"8.5.63\"\n    },\n    \"preferredEditor\": \"blocksprj\"\n}\n",
  "tilemap.g.jres": "{\n    \"transparency16\": {\n        \"data\": \"hwQQABAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA==\",\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"tilemapTile\": true\n    },\n    \"*\": {\n        \"mimeType\": \"image/x-mkcd-f4\",\n        \"dataEncoding\": \"base64\",\n        \"namespace\": \"myTiles\"\n    }\n}",
  "tilemap.g.ts": "// Auto-generated code. Do not edit.\nnamespace myTiles {\n    //% fixedInstance jres blockIdentity=images._tile\n    export const transparency16 = image.ofBuffer(hex``);\n\n    helpers._registerFactory(\"tile\", function(name: string) {\n        switch(helpers.stringTrim(name)) {\n            case \"transparency16\":return transparency16;\n        }\n        return null;\n    })\n\n}\n// Auto-generated code. Do not edit.\n"
}
```

## Code Ninjas Game Building Session @showdialog
**Summer Game Jam!**
---
Welcome to Code Ninjas! Follow along with a Code Sensei to code your own game!

![project gif](https://github.com/Code-Ninjas-Home-Office/workshops/blob/master/images/FruitGame.gif?raw=true, "Summer Game Jam project")
![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

## Welcome
--- 

**Answer:** 

❓ Have you ever coded before?

❓ Have you ever used MakeCode Arcade?

Today you will be coding in MakeCode Arcade! Take a look and you'll notice there is already some code on screen - the code doesn't do anything yet, but we'll be using it soon to make a cool game.

--- 

**MakeCode Overview:** 

Your ``||text:Code Sensei||`` will now explain MakeCode Arcade's interface! 

![Ninja](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/NinjaDisplaying.png?raw=true "Explain Interface") 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

## Set the background image

Add a Summer styled image as the background!

- :tree: In the Toolbox, open ``||scene:Scene||`` then drag the ``||scene:set background image||`` block into the ``||loops:on start||`` container above the code already in it.
- :mouse pointer: Click the gray square, then select a **Summer themed** image from **The Gallery**.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## The Game Window 

As you add code to your project, look at the Game Window on the **lower right** of your screen to see it update! 

![Game Window](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/GameWindow.png?raw=true "Game Window") 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

## Set the sprite images

Add the sprite images for the ninja and fruit!

A **sprite** is an object in a game's program.

- :mouse pointer: Click the gray square in the ``||variables(sprites):set ninja to||`` code block, then select the **ninja** image from **My Assets**.
- :mouse pointer: Click the gray square in the ``||variables(sprites):set fruit to||`` code block, then select a **fruit** image from **My Assets**.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Set the sprite movement

Move the ninja with the left and right arrow keys!

- :function: Click **Advanced**. Open ``||functions:Functions||`` then drag a ``||functions:call resetPlayers||`` block into the bottom of the ``||loops:on start||``.
- :keyboard: Test out your game! Use the **left** and **right arrows** or **A** and **D** to move the ball up and down. 

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Reset the fruit

Reset the fruit back to the top of the screen after it overlaps with the player.

- :paper plane: Open ``||sprites:Sprites||`` and drag out a ``||sprites:on sprite overlaps||`` container into the coding area.
- :function: Click **Advanced**. Open ``||functions:Functions||`` then drag a ``||functions:call resetPlayers||`` block into the ``||sprites:on sprite overlaps||`` container.
- :headphones: Open ``||music:Music||`` and drag out a ``||music:play sound||`` block under ``||functions:call resetPlayers||``. Click ▼ to select the sound ``||music:zapped||`` so it plays when the sprites overlap.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
sprites.onOverlap(SpriteKind.Player, SpriteKind.Enemy, function (sprite, otherSprite) {
})
```

## Try to grab the fruit

Use the A button or space key to run towards the fruit.

- :game controller: Open ``||controller:Controller||`` to drag out the entire ``||controller:on A button pressed||`` container into the coding area.
- :headphones: Open ``||music:Music||`` and drag out a ``||music:play sound||`` block into the ``||controller:on A button pressed||`` container. Click ▼ to select the sound ``||music:knock||`` so it plays when the player moves towards the fruit.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
sprites.ninjas.setVelocity(0, -70)
controller.A.onEvent(ControllerButtonEvent.Pressed, function () { 
    ninja.setVelocity(0, -70)
    controller.moveSprite(ninja, 0, 0) 
}) 
let ninja: Sprite = null 
``` 

## Add the end of the screen

Add a sprite to the top of the project that will help you reset the player if you miss.

- :paper plane: Open ``||sprites:Sprites||`` and drag out ``||variables(sprites):set end to||`` into the ``||loops:on start||`` container below the other code.
- :mouse pointer: Click the gray square in the ``||variables(sprites):set end to||`` code block, then select the **end** image from **My Assets**.
- :paper plane: Open ``||sprites:Sprites||`` again and drag out ``||sprites:set end y to (0)||`` into the ``||loops:on start||`` container below ``||variables(sprites):set end to||``.


![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
let end = sprites.create(img``, SpriteKind.Player)
end.y = 0
```

## Hit the end of the screen!

Use another overlap container to make your character reset and the fruit reset when you reach the end of the screen!

- :paper plane: Open ``||sprites:Sprites||`` and drag out another ``||sprites:on sprite overlaps||`` container into the coding area.
- :tree: Open ``||scene:Scene||`` and drag out a ``||scene:start screen effect||`` block into to ``||sprites:overlap||`` container.
- :function: Click **Advanced**. Open ``||functions:Functions||`` then drag a ``||functions:call resetPlayers||`` block under ``||scene:start screen effect||``.
- :headphones: Open ``||music:Music||`` and drag out a ``||music:play sound||`` block under ``||functions:call resetPlayers||``. Click ▼ to select the sound ``||music:jump up||`` so it plays when the sprites overlap.

*Run towards the end of the screen and see what happens!*

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
sprites.onOverlap(SpriteKind.Player, SpriteKind.Player, function (sprite, otherSprite) {
})
effects.confetti.startScreenEffect(1000)
```

## Keep track of how many fruits you catch!

Use MakeCode Arcade's built-in scoring system to keep track of your fruits caught!

- :id card: Open ``||info:Info||`` and drag out ``||info:set score to 0||`` into the ``||loops:on start||`` container below the other code.
- :id card: Open ``||info:Info||`` again and drag out ``||info:change score by 1||`` into the ``||sprites:Player overlaps Enemy||`` container from earlier.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Set the game timer!

Use MakeCode Arcade's built-in timer to end the game after 30 seconds of play!

- :id card: Open ``||info:Info||`` and drag out ``||info:start countdown 30s||`` into the ``||loops:on start||`` container below the other code.
- :id card: Open ``||info:Info||`` again and drag out ``||info:on countdown end||`` into the coding area.
- :headphones: Open ``||music:Music||`` and drag out ``||music:play sound||`` into the ``||info:on countdown end||`` container. Click ▼ to select the sound ``||music:buzzer||`` so it plays when the countdown ends.
- :circle: Open ``||game:Game||`` and drag out ``||game:game over||`` into the ``||info:on countdown end||`` container below the other code.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 

```blockconfig.local
info.startCountdown(30)
```

## Add game directions!

Tell the player how to play your game!

- :circle: Open ``||game:Game||`` and drag out ``||game:show long text||`` into the ``||loops:on start||`` container below the other code.
- :keyboard: Click the white bubble to type in text that will be displayed in a dialog box on screen at the start of the game.
- :circle: Use as many ``||game:show long text||`` blocks as needed to display your game's instructions.

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 


## Customizations!

### ``||variables:C||`` ``||controller:u||`` ``||loops:s||`` ``||animation:t||`` ``||logic:o||`` ``||sprites:m||`` ``||music:i||`` ``||math:z||`` ``||scene:e||`` 

The tutorial is finished, but now it's time to customize your game!

---

Here are a few things to try:

- :paper plane: Add more fruit! Create additional **Enemy** sprites that will add more variety to the game!
- :paint brush: Change scenery! Edit the background image so the ninja catch fruit in a brand new location!
- :id card: Change the timer and score! Edit the score and timer **parameters** to change the length of the game and how many points scored with each fruit!
- :headphones: Change the sounds and music! Edit the sounds played when the ninja attempts to grab a fruit, a fruit is grabbed, and when you miss the fruit!

When you are finished, click **Done** then follow your Code Sensei's guidance to create a shareable link that will let you play your game at home!

![Logo](https://github.com/Code-Ninjas-Home-Office/game-building-session-tutorials-2024/blob/master/images/CN-Logo.png?raw=true "CN Logo") 
