# Rapid Roll Game

A classic "Rapid Roll" arcade-style game written in C/C++ using the **iGraphics** library (a lightweight OpenGL/GLUT-based 2D graphics wrapper for Windows). The player controls a falling character that must keep landing on a series of moving platforms to avoid falling off-screen or being crushed at the top, while the score increases over time.

## Features

- 2D sprite-based gameplay built on the iGraphics rendering library
- Main menu, level selection, language selection, and high-score screens (rendered from bundled BMP assets)
- Lives/health system with on-screen life and score symbols
- Animated character sprites (numbered frame BMPs such as `0.bmp`–`9.bmp`, `F0.bmp`–`F9.bmp`)
- Persistent high score stored in `high.txt`
- Several demo/experimental sketches (`PictureDemo*.cpp`) showing image loading, animation, and transparency

## Tech Stack

- **Language:** C / C++
- **Graphics:** iGraphics (`iGraphics.h`) over OpenGL + GLUT
- **Image loading:** custom BMP loader (`bmpLoader.c`)
- **Build system:** Code::Blocks project (`MyIGraphics.cbp`)
- **Assets:** `.bmp` image files for sprites, menus, and UI

## Project Structure

```
Rapid Roll/
├── iMain.cpp                  # Main entry point and iGraphics callbacks (iDraw, iMouse, iKeyboard, ...)
├── iGraphics.h                # iGraphics library header
├── bmpLoader.c                # BMP image loading helper
├── PictureDemo*.cpp           # Image / animation / transparency demos
├── MyIGraphics.cbp            # Code::Blocks project file
├── high.txt                   # Stored high score
├── *.bmp                      # Sprites, menus, score and life graphics
├── RequiredFiles/             # Supporting library/runtime files
├── bin/ , obj/                # Build output directories
└── others/                    # Misc. files
```

## Build & Run

This is a Windows project built with **Code::Blocks** and the iGraphics/GLUT toolchain:

1. Install [Code::Blocks](http://www.codeblocks.org/) with a configured GCC/MinGW compiler.
2. Open `Rapid Roll/MyIGraphics.cbp` in Code::Blocks.
3. Make sure the GLUT/iGraphics dependencies in `RequiredFiles/` are available to the compiler/linker.
4. Build and run the project from the IDE.

Run the game with the working directory set to the `Rapid Roll` folder so that the BMP assets and `high.txt` are found.

## Controls

Input is handled through the iGraphics callbacks in `iMain.cpp` (`iKeyboard`, `iSpecialKeyboard`, `iMouse`). Pressing `q` exits the game.

## Notes

This project was built as a learning exercise with the iGraphics library and includes a number of experimental demo source files alongside the main game.
