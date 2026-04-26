# Project README

## Overview
This project is a simple raycasting engine written in C. It renders a 3D world from a first-person perspective and allows basic movement.

## Features
- Basic raycasting algorithm to render a 3D world.
- Player movement with WASD keys.
- Rendering of walls, floors, and the player.
- Debugging and profiling support via GCC's `-g` flag.

## Project Structure
```
<project>/
├── build/              # .exe files produced by Main.c
├── src/                # source code
│   ├── Main.c          # Entry point
│   └── *.h             # stand alone Header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── README.md           # This file
└── LICENSE
└── .gitignore
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools

## Build & Run
To build the project on Linux:

```sh
cd <project>
make -f Makefile.linux all
./build/Main
```

To build and run the project in debug mode on Windows:

```sh
cd <project>
make -f Makefile.windows dg
wine build/Main.exe
```

For web assembly, use Emscripten to compile it:

```sh
emcc -O0 -msimd128 -mavx2 -std=gnu17 src/*.c -o build/index.html
emrun --no_browser --port 8080 build/
```

The `Makefile` for each OS is responsible for compiling the source code into an executable or web assembly file.