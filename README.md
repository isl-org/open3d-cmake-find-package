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
installation path with `CMAKE_INSTALL_PREFIX` and the number of parallel jobs
to speed up compilation.

On Ubuntu/macOS:

```bash
git clone --recursive https://github.com/intel-isl/Open3D.git
cd Open3D
mkdir build
cd build
cmake -DBUILD_SHARED_LIBS=ON -DCMAKE_INSTALL_PREFIX=${HOME}/open3d_install ..
make install -j 12
cd ../..
```

On Windows:

```batch
git clone --recursive https://github.com/intel-isl/Open3D.git
cd Open3D
mkdir build
cd build
cmake -DBUILD_SHARED_LIBS=ON -DCMAKE_INSTALL_PREFIX=C:\open3d_install ..
cmake --build . --config Release --parallel 12 --target install
cd ..\..
```

Note: `-DBUILD_SHARED_LIBS=ON` is recommended if `-DBUILD_CUDA_MODULE=ON`.

## Step 2: Use Open3D in this example project

On Ubuntu/macOS:

```bash
git clone https://github.com/intel-isl/open3d-cmake-find-package.git
cd open3d-cmake-find-package
mkdir build
cd build
cmake -DOpen3D_ROOT=${HOME}/open3d_install ..
make -j 12
./Draw
```

On Windows:

```batch
git clone https://github.com/intel-isl/open3d-cmake-find-package.git
cd open3d-cmake-find-package
mkdir build
cmake -DOpen3D_ROOT=C:\open3d_install ..
cmake --build . --config Release --parallel 12
Release\Draw
```
