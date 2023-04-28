# Qt - CMake Scaffold

## Setup Build Environment
- Install the following tools:
    - `C/C++` compiler
    - `CMake`
    - `Conan` package manager

## Consume Qt as a package dependency
I prefer consuming Qt as a package dependency. It can be as built binaries or built from sources. There are several open source projects available that show how to setup qt and cmake together. However, I don't find those setups reproducible due to following reasons:
- Use of local environment variables
- Pointing local installations of Qt
- No directions for `cmake install` is avaiable.

## Build
### w/o conan & qt
```bash
# Configure
cmake . -B build -G "Visual Studio 16 2019" -DCMAKE_INSTALL_PREFIX=install 
# Build
cmake --build build --config Release
# install
cmake --install build --config Release
```
## Install

## Run
