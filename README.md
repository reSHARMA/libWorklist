<h1 align="center">
  <br>
  <a href="#"><img src="https://i.ibb.co/NZcjPLx/1fdb3719-b793-4e48-8c66-aeee9b9c43be-200x200.png" alt="libWorklist" width="200"></a>
  <br>
  libWorklist
  <br>
</h1>

<h4 align="center">Worklist for LLVM Instructions</h4>


## Table of Contents

- [Getting Started](#getting-started)
  - [Building from source](#build-from-source)
  - [Using with opt](#using-with-opt)
- [Initializing the worklist](#initializing-the-worklist)

## Getting Started
libWorklist handles initialization and manipulation of a queue of LLVM instructions. 

### Building from source
```sh
$ git clone this_repository.git
$ cd this_repository
$ mkdir build; cd build
$ cmake .. && make
$ make install
```
### Using with opt
* Path to shared libary and headers should be searchable by the compiler
* In your LLVM IR pass:
  * Include the header file, ```Worklist/Worklist.h```
  * Use namespace ```WorklistUtil```
* Load libWorklist.so before your pass's shared library
  * ``` opt -load /usr/local/lib/libWorklist.so -load yourPass.so ... ```

## Initializing the worklist
The worklist can be initialized by a Module, Function, Basicblock and Instruction. 
```cpp
// M is a pointer to LLVM Module
WorklistUtil::Worklist W(M);
```
