# Sprites

The sprites are located in data/sprites/*.sprite

They are json files which looks like this:
```
{

"item_food_potato" : {
        "texture" : "food",
        "topx" : 0,
        "topy" : 0,
        "height" : 32,
        "width" : 32,
        "originx" : 16,
        "originy" : 16
}

}
```
In this case:

| name | meaning | type |
| --- | --- | --- |
| item_food_potato | This is the name of the sprite | Object representing the sprite |
| texture | The texture refering. "food" means "data/textures/food.png" | string |
| topx | The topx cooridinate of the top-left cornor of the sprite in the texture | int |
| topy | The topy cooridinate of the top-left cornor of the sprite in the texture | int |
| height | Height of the sprite | int |
| width | Width of a frame in the sprite | int |
| originx | There the engine starts drawing. Defaults to 0 | float |
| originy | There the engine starts drawing. Defaults to 0 | float |
