## Introduction

This application uses the following project to generate a static lib for clang
https://github.com/bdurrani/libclang-static-build

This makes it easier to manage the build

## Sample flags for static libs

```
CC=@CMAKE_C_COMPILER@
CFLAGS=-I@MAKEFILE_LIBCLANG_INCLUDE@
LIBS=-L@MAKEFILE_LIBCLANG_LIBDIR@ -lclang_bundled -lstdc++ -lm -ldl -lpthread -lz
OBJ=clang_visitor.o

```
