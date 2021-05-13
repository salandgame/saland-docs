# Console

The console can be started in game by pressing `Shift+Esc`.


## Commands

### help
```
help [COMMAND]
```
This command will show all the possible commands.
It takes an optional parameter to show the help page for that command.

Example:
```
help config
```

### goto
```
goto X Y
```
Loads a given region and spawns the player in that region.

Useful if you want to go to a specific region and see how it plays.

Note that X and Y are signed integeres.

Example:
```
goto 5 -4
```


### quit
Quits the game

### reset_region
This command will delete the current region and restore it like you just entered it for the first time.

### tiled
This will write the current map to disc and try to launch `tiled` on it. Once tiled is closed the map will be reloaded.

If tiled is not found then the current map will simply be reloaded.