# Find Pre-Installed Open3D Package in CMake

This is one of the two CMake examples showing how to use Open3D in your CMake
project:

* [Find Pre-Installed Open3D Package in CMake](https://github.com/intel-isl/open3d-cmake-find-package)
* [Use Open3D as a CMake External Project](https://github.com/intel-isl/open3d-cmake-external-project)

For more details, check out the [Open3D repo](https://github.com/intel-isl/Open3D) and
[Open3D docs](http://www.open3d.org/docs/release/cpp_project.html).

## Step 1: Compile and install Open3D

Follow the [Open3D compilation guide](http://www.open3d.org/docs/release/compilation.html),
compile and install Open3D in your preferred location. You can specify the
installation path with `CMAKE_INSTALL_PREFIX`. E.g.

On Ubuntu/MacOS:

```bash
git clone --recursive https://github.com/intel-isl/Open3D.git
cd Open3D
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=${HOME}/open3d_install ..
cd ../..
```

On Windows:

```batch
git clone --recursive https://github.com/intel-isl/Open3D.git
cd Open3D
mkdir build
cd build
cmake -G "Visual Studio 16 2019 Win64" -A x64 -DCMAKE_INSTALL_PREFIX=C:\open3d_install ..
cmake --build . --config Release --target install
cd ..\..
```

## Step 2: Use Open3D in this example project

On Ubuntu/MacOS:

```bash
git clone https://github.com/intel-isl/open3d-cmake-find-package.git
cd open3d-cmake-find-package
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=${HOME}/open3d_install ..
./Draw
```

On Windows:

```batch
git clone https://github.com/intel-isl/open3d-cmake-find-package.git
cd open3d-cmake-find-package
mkdir build
cmake -G "Visual Studio 16 2019 Win64" -A x64 -DCMAKE_PREFIX_PATH=C:\open3d_install  ..
cmake --build . --config Release
Release\Draw
```
