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

```powershell
conan install conanfile.txt -if .\conan_cmake\release --build=missing -pr .\conan\profiles\win_x64.txt -s build_type=Release
```

## Configure - Build
### w/o conan & qt
```bash
# Configure
cmake . -B build -G "Visual Studio 16 2019" -DCMAKE_INSTALL_PREFIX=install 
# Build
cmake --build build --config Release
```

### w conan & qt
```bash
# Configure
cmake . -B build -G "Visual Studio 16 2019" -DCMAKE_INSTALL_PREFIX=install 
# Build
cmake --build build --config Release
```
## Install
```bash
cmake --install build --config Release
```
## Run

## References
## Repos
- [euler0/mini-cmake-qt](https://github.com/euler0/mini-cmake-qt)
- [synacker/daggy](https://github.com/synacker/daggy)
- [eryar/occQt](https://github.com/eryar/occQt)
### General
- [Modern CMake for Qt Developers](https://www.youtube.com/watch?v=R-buLlBnvJY)
### Qt5
- [Build with CMake](https://doc.qt.io/qt-5/cmake-manual.html)
- [Using CMake with Qt5](https://www.kdab.com/using-cmake-with-qt-5/)
- [CMake: Finding Qt 5 the “Right Way”](https://www.kitware.com/cmake-finding-qt5-the-right-way/)
- [CMake and Qt](https://www.kdab.com/wp-content/uploads/stories/KDAB-whitepaper-CMake.pdf)
- [Migrating from QMake to CMake](https://www.youtube.com/watch?v=RVfRnuP2MME)

#### Deploy
- [Using CMake to build Qt 5.10 projects](https://jclay.github.io/dev-journal/cmake-qt5-10.html)

- [Windeployqt.cmake - gitlab](https://gitlab.inria.fr/adufay/SpectralViewer/blob/f7a9d531ecf4b54fc43cfca43f6106d0710dae1a/cmake/Windeployqt.cmake)

- [Integrating with CMake](https://riptutorial.com/qt/example/24133/integrating-with-cmake)

- [Stackoverflow 1](https://stackoverflow.com/questions/60854495/qt5-cmake-include-all-libraries-into-executable#:~:text=To%20solve%20this%20i%20would%20suggest%20using%20windeployqt.,it%20into%20%2Fcmake%20modules%20folder%20of%20your%20project%3A)

- [stackoverflow2](https://stackoverflow.com/questions/60854495/qt5-cmake-include-all-libraries-into-executable)

- [stackoverflow 3](https://stackoverflow.com/questions/41193584/deploy-all-qt-dependencies-when-building)

- [Installing qt libraries in linux](https://discourse.cmake.org/t/installing-qt-libraries-on-linux/1524/3)

- [Deploying Qt applications With DeployQt4](https://mikemcquaid.com/deploying-qt-applications-with-deployqt4/)

#### DeployQt file
- [DeployQt5.cmake - Sample1](https://github.com/OpenChemistry/avogadroapp/blob/master/cmake/DeployQt5.cmake)

- [DeployQt5.cmake - Sample2](https://cmake.org/pipermail/cmake/2013-August/055525.html)

- [DeployQt5.cmake - Sample3](https://phabricator.mitk.org/T18552?id=18552)