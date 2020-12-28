# Tiled

Saland uses tmx files for Tiled.

There are some requirements to how the files need to look in order for them to work.

## Layers

### mutableObjects
This layer contains the elements which the game itself uses to make the world consistent. Element on this layer can be removed or added by the engine.
Examples for this is: Trees, barrels etc.

Some elements (barrels, trees) blocks the player.

### object1
This layer contains some static objects.

#### Retangles with type "protectedRegion"
Tells the engine to not allow the player to do any changes. The reqion is protected

### blocking_overlay_1
Managed by the engine. The engine might put elements which belongs to the blocking layer.

### overlay_1
A layer drawn above the player player layer. Can be used for cieling bars or signposts.

### blocking
This is the blocking layer. All tiles on this layer blocks the player.
The engine may change this layer.

### ground_2
The layer below the ground blocking layer. Might be managed by the engine in the future

### ground_1
The lowest layer. The engine will not change this.