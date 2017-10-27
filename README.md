# Rewind viewer

[![MIT License](https://img.shields.io/github/license/kswaldemar/highloadcup2017.svg?style=flat-square)](./LICENSE)
[![C++ standard](https://img.shields.io/badge/C++-14-blue.svg?style=flat-square)](https://isocpp.org/)
[![OpenGL](https://img.shields.io/badge/OpenGL-3.3-green.svg?style=flat-square)](https://www.khronos.org/opengl/)
[![RAIC](https://img.shields.io/badge/Russian%20AI%20Cup-2017-yellow.svg?style=flat-square)](http://russianaicup.ru/)

Fast Russain AI Cup championship match viewer with rewinding support written in OpenGL

## Design
Viewer has several advantages in comparison of local-runner with drawing plugin:
 - All figures is drawn using your video adapter, so no more problems with slow drawing
 - Rewinding - ability to navigate between game tick
 - Pause navigation - zoom and navigate in any game state
 - Handy mouse navigation

Obvious drawbacks:
 - Viewer running as standalone application, it know nothing about local runner or your strategy, so you need manually 
send all data (like buildings, units etc.) and you can draw only data visible by your strategy
 - In theory high memory usage, because it need to store all drawing primitives for rewinding support

**Note**: Currently viewer reached 1.0 version and still in active development. 
You may find updated files and more primitives support (maybe potential fields, etc.) during championship.

## Build

Istall thirdparties:
 - [glfw library](http://www.glfw.org/), viewer need at least version 3.2
 - [glm library](https://glm.g-truc.net/0.9.8/index.html) please install version **0.9.8**, 
 because there breaking changes in newer releases
 
All other dependencies shipped together with project.

Clone repository and run:
```
mkdir build && cd build
cmake --CMAKE_BUILD_TYPE=Release ..
cmake --build .
```
*Note*: You need compiler with c++14 support.

## Launch
You need special client to be able send messages in viewer. See [example C++ client](https://github.com/kswaldemar/rewind-viewer/blob/master/clients/c%2B%2B/RewindClient.h) for information about json based message
protocol and implement one for your language of choice.
Also see [client examples for official local runner](https://github.com/JustAMan/russian-ai-cup-visual/tree/master/clients).

Then run viewer before strategy and it should start draw frames

## License
Project sources distibuted under [MIT license](https://github.com/kswaldemar/rewind-viewer/blob/master/LICENSE), thirdparties distributed under their own licences

## Credits
Project builded using many libraries
 - [glad](https://github.com/Dav1dde/glad) for loading OpenGL functions
 - [glm](https://glm.g-truc.net/0.9.8/index.html) math library for OpenGL
 - [glfw](http://www.glfw.org/) for creating window and crossplatform context handling
 - [ImGui](https://github.com/ocornut/imgui) for UI widgets inside application
 - [nlohmann json](https://github.com/nlohmann/json) for json operating
 - [csimplesocket](https://github.com/DFHack/clsocket) for network interaction
 - [stb_image](https://github.com/nothings/stb) for images processing
 
