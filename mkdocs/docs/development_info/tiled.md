# Tiled

Saland uses tmx files for [Tiled](https://www.mapeditor.org/).

There are some requirements to how the files need to look in order for them to work.

## Implementation

The layer order is currently defined in `src/saland/model/World.cpp`

## Layers

### prefab_marking
Marks the prefabs. This is a collection of several tiles like a house.
Prefabs are copied to the map once placed, so updating the templete has no effect.
Any tile touched by a rectangle on the prefab_marking layer are considered protected and managed by the prefab system.

### mutableObjects
This layer contains the elements which the game itself uses to make the world consistent. Element on this layer can be removed or added by the engine.
Examples for this is: Trees, barrels etc.

Some elements (barrels, trees) blocks the player.

### object1
This layer contains some static objects.

Objects on this layer:

| Type | Condition | Effect |
| --- | --- | --- |
| Retangle | type = "protectedRegion" | Tells the engine to not allow the player to do any changes. The reqion is protected |

### overlay_1
A layer drawn above the player layer. Can be used for cieling bars or signposts.
This layer is currently ignored by the engine.

### prefab_overlay_1
Tiles on this layer are managed by the prefab system. Any tile on this layer should be protected by the prefab_marking-layer.

### blocking_overlay_1
Managed by the engine. The engine might put elements which belongs to the blocking layer.
This is used by some tiles which needs an extra layer to blend correctly.

### prefab_blocking_2
A blocking layer managed by the prefab system. Any tile on this layer should be protected by the prefab_marking-layer.


### blocking
This is the blocking layer. All tiles on this layer blocks the player.
The engine may change this layer.


### prefab_ground_1
A ground layer managed by the prefab system. Any tile on this layer should be protected by the prefab_marking-layer.


### ground_2
The layer below the ground blocking layer. Might be managed by the engine in the future

### ground_1
The lowest layer. The engine will not change this.