# Spatialite
This is a soft fork of [SpatiaLite](https://www.gaia-gis.it/fossil/libspatialite/index) and very much work in progress ⚠️. This adds modern CMake build support. Please do not open any feature issues. MR are welcome.

### Source Changes
- Fix UTF-8 encoding of `epsg_inlined_21.c` and `epsg_inlined_25.c`
- Fix include of `lwn_network.h` using system include style

### Installation
This requires the following software installed:
- CMake 3.23+ 
- Ninja 1.10+
- vcpkg
Currently the vcpkg path is hardcodec to `C:` in the `CMakePresets.json`, but this can easily be changed:
```
"CMAKE_TOOLCHAIN_FILE": "C:/vcpkg/scripts/buildsystems/vcpkg.cmake"
```
Install the dependencies:
```
vcpkg install sqlite3 libxml2 libiconv geos freexl librttopo
```

### Development & Compilation
Any modern IDE with `CMakePresets.json` is recommended like QtCreator, VSCode or Visual Studio 2022. Simply install the dependencies, open the preset and hit compile.

### License
SpatiaLite is licensed under the MPL tri-license terms; you are free to choose the best-fit license between:
