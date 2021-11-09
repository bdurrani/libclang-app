## Sample flags for static libs

```
CC=@CMAKE_C_COMPILER@
CFLAGS=-I@MAKEFILE_LIBCLANG_INCLUDE@
LIBS=-L@MAKEFILE_LIBCLANG_LIBDIR@ -lclang_bundled -lstdc++ -lm -ldl -lpthread -lz
OBJ=clang_visitor.o

```
