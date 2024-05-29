# 64-bit Operating System Kernel
This repository contains a 64-bit operating system kernel developed from scratch. The kernel is multiboot2-compliant and features low-level functionality such as stack setup, long mode enablement, paging, and high-level features like text printing.

## Features

- Multiboot2 compliance
- 64-bit long mode support
- Custom bootloader and linker script
- Basic paging setup
- Text printing functionality

## Prerequisites

- Docker
- QEMU (for testing and running the kernel)

## Building the Kernel

1. Build the Docker environment: ```docker build buildenv -t {name here} ```
2. Enter the build environment: docker run --rm -it -v "$(pwd)":/root/env {name here}
3. Build the kernel:  ```make build-x86_64```

## Running the Kernel

To run the kernel using QEMU, execute the following command: ```qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso```

## Project Structure

- `buildenv/`: Contains the Dockerfile for setting up the build environment.
- `src/`: Contains the kernel source code.
  - `impl/`: Contains the implementation files.
    - `kernel/`: Contains the kernel-specific code.
    - `x86_64/`: Contains the x86_64 architecture-specific code.
  - `intf/`: Contains the interface files (header files).
- `targets/`: Contains the target-specific files and configurations.
  - `x86_64/`: Contains the x86_64 target files.
- `Makefile`: The build configuration file.

## Source
This project was able to be created following this OS series: https://github.com/davidcallanan/os-series
