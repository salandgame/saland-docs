# Libraries

Some of the dependencies and the justification for using them

## Dependencies

### SDL 2
[Homepage](https://www.libsdl.org/)

This is the fundation of all my C++ games. It cross compiles and is relatively easy to pack.
In contrast to other native C++ libraries like SFML, RAII is not included by default. However, while working with SFML I found that I ended up with my own RAII layer anyway.

### SDL2_gfx
[Homepage](https://sourceforge.net/projects/sdl2gfx/)

Easily mistaken for an actual part of SDL2. It is that conformaty which makes it attractive.

### PhysFS
[Homepage](https://icculus.org/physfs/)

This is the library used for abstracting the file system. The system is strongly inspired by the system used by Quake 3. It is also fantiastic for mod support.

### boost_program_options
[Homepage](https://www.boost.org/doc/libs/1_76_0/doc/html/program_options.html)

Used to parse program options from command line or config file. Primarily used because I like the format for `saland -h`. There are other libraries that does the same but I prefer the boost option if it is availeble. 

### boost (headers)
[Homepage](https://www.boost.org/)

For basic algorithms I turn to boost. Used tokenizer and predicate. It is big dependency in size but I find the number of dependencies to be more problematic than the size.

## Bundled

### Box2d
[Homepage](https://box2d.org/)

This is used for the physics. Using physics in a top down game gives a feeling of pushing things around that I like.
I include box2d as a bundled dependency. The reason is that Box2d does not guarentee compatibility between even versions. Even minor versions might break the API.

### b64
[Homepage](http://libb64.sourceforge.net/) [(Debian patches)](https://sources.debian.org/patches/libb64/1.2-5/)

Used for base64 encoding and decoding for the Tiled format. During development I got depended on some of the Debian changes. There is an unmerged patch on the SalesForce project and without that patch everything breaks horrible. Buffer overflows are a major problem in C and b64 is very prone to them without the patch.

### utf8cpp
[Homepage](https://github.com/nemtrif/utfcpp)

The nononse working version of UTF-8 for C++. The biggest problem with this library is that Linux distribution package it differently and MXE.cc does not pack it at all. Therefore the library is also bundled.

### rapidxml
[Homepage](http://rapidxml.sourceforge.net/)

Used by the homemade tiled-library. This is a header only.
I have experieced some version compatibility trouble while working with Cereal, so I embed a specific version.


### rapidjson
[Homepage](https://rapidjson.org/)

Used by the commen "sago" files shared with Block Attack - Rise of the Blocks. Bundled due to compatiblity concers found in Cereal.

### PlatformFolders
[Homepage](https://github.com/sago007/PlatformFolders)

My own library for handling access to Save games folders on different platforms.
While this was designed with backwards compatibility in mind. I always assumed that it would get embedded.

