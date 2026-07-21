1. Open your Terminal application on your Mac.

2. Update Homebrew to ensure all your package references are up to date by running:
   brew update

3. Install QEMU and the RISC-V cross-compiler toolchain by running:
   brew install qemu riscv64-elf-gcc

4. Verify that the compiler was installed properly by running:
   riscv64-elf-gcc --version

5. Clone the official MIT xv6-riscv repository by running:
   git clone https://github.com/mit-pdos/xv6-riscv.git

6. Move into the cloned xv6 directory by running:
   cd xv6-riscv

7. Build and run xv6 inside QEMU by running:
   make qemu

8. To exit QEMU and return to your Mac terminal, press Ctrl+A and then press X.
