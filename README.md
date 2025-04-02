# Use Pistache

## Instructions

**I am using `Ubuntu 24.04.2 LTS`**

We need two things:

- CMake
- g++ compiler

### CMake

Update:

```terminal
sudo apt update
```

Install:

```terminal
sudo apt install cmake
```

Verify:

```terminal
cmake --version
```

### C++ compiler

The following command should give us a c++ compiler:

```terminal
sudo apt install build-essential
```

Now check:

```txt
g++ --version
```

## Pistache

```txt
# Add pistache repo
sudo add-apt-repository ppa:pistache+team/stable

# update
sudo apt update

# download pistache binary and headers
# download pkg-config required by cmake
sudo apt install libpistache-dev pkg-config

# make build dir
mkdir build

# go to build dir
cd build

# tell cmake where is the CMakeLists.txt (i think)
cmake ..

# build with cmake
cmake --build .

# run the binary
./use-pistache
```

On code changes, run these two:

```txt
# build with cmake
cmake --build .

# run the binary
./use-pistache
```

### If curious

Here is how you can find statically and dynamically built library downloaded via `sudo apt install libpistache-dev`. Here are also the headers. CMake is used to find the headers and library, link it, and allow our cpp files to include the headers.

```txt
# Find header files
find /usr/include -name "*pistache*"

# Find library files
find /usr/lib -name "*pistache*"
```

## More resources

If you are interested, i played around with c++ and OpenGL. You only really need to see the part how i use `CMake` and `vcpkg`.

https://github.com/srele96/sk-engine/tree/main
