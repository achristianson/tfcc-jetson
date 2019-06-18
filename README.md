# tfcc-jetson
Build `tensorflow_cc` for NVIDIA® Jetson™ systems

## Requirements

Most requirements (CUDA, etc.) are already installed with the standard Jetson
image. Additional requirements are checked & installed if necessary by the
build script:

- `cmake`
- `curl`
- `tensorflow_cc`
  - `bazel`
    - `openjdk-8-jdk-headless`
  - `NCCL`

## Building

***IMPORTANT*** A lot of RAM is required to build `tensorflow_cc`. On the
Jetson Nano (4GB RAM), it is recommended to have **at least** 8GB of swap
enabled on the system. Swap should be on a different device than the root
filesystem, otherwise compilation will be even slower.

### Enabling swap on a USB flash drive:

As `root`:

```sh
mkswap /dev/<YOUR DEVICE>
swapon /dev/<YOUR DEVICE>
```

### To build, run:

```sh
git clone --recurse-submodules https://github.com/achristianson/tfcc-jetson.git
cd tfcc-jetson
./build # This will build AND install tensorflow_cc
```

Expect `tensorflow_cc` compilation to take a day or so.
