# cpp-example

Simple C++ example used for oe-selftests.

## cmake

```sh
cmake -B build -DCMAKE_INSTALL_PREFIX:PATH=$PWD/install/usr
cmake --build build -t install
cmake --build build -t test
```

## meson

```sh
meson setup builddir
cd builddir
meson compile
meson test
```
