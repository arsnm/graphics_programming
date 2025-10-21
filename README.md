# Graphics Programming
> by arsnm

This repo is a sandbox to learn and to experience the joy of doing graphics programming.
I don't know what this repo will contain, all I can say is that it is not really meant to be accessible
to anyone but me (even though I chose to make it public). Expect nothing from it, no warranty whatsoever,
everything is licensed under [The Unlicense](https://unlicense.org), feel free to look at everything, or
to take anything from it if you dare to do so.


## Projects/Roadmap
> Not at all definitive

- [ ] Discovering graphics programming basic through OpenGL
- [ ] ...TBD
- [ ] FINAL OBJECTIVE ?????? (apparently its hard) : having a basic understanding of how Vulkan API works.

## BUILD/INSTALL

To compile any of the program in this, there's a few things to do.
This setup is appropriate for a **text editor + make setup**.

The programs on this repo are intended to run on **OpenGL 3.3** (eventually higher),
and use the *core-profile* of the API.

The library used to create windows and rendering things on the screen
is [GLFW](https://glfw.org). To run the programs you need to download
glfw (either prebuilt-binaries, or the [source code](https://github.com/glfw/glfw/releases/download/3.4/glfw-3.4.zip) and compiling it 
(the latter is recommended)).

### Glad setup

To link OpenGL functions declaration with there actual implementations, one
could choose to do it manually, or to use (as intended in this repo) to use the GLAD()
open source library. Then, just add the `glad.c` file to the root folder of any program,
and don't forget to include the `glad/include` directory to your favorite's compiler include
path.

### Clangd support

If you want to use the *clangd* language server, you can ask CMake to create a compile_commands.json,
in order to have the right links/definitions to the librairies used :

```sh
cmake -DCMAKE_EXPORT_COMPILE_COMMANDS=ON .
```

## Ressources

This repository contains a lot of programs inspired/taught by the [LearnOpenGL Online Book](https://learopengl.com),
do not hesitate to have a look at the book, and to eventually support the author Joey de Vries.

> [!WARNING]
> Even though the repo itself is under [The Unlicense](./LICENSE), since a lot of code is from the [LearnOpenGL Online Book](https://learopengl.com),
> I'm not the owner of all the copyrights on this repository. Thus make sure to comply with the book's license before taking anything
> from it.
