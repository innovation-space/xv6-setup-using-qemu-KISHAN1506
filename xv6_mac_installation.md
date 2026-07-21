Getting xv6 up and running on a Mac is straightforward once you set up the right compiler and emulator. Since macOS cannot natively compile ELF binaries targeted for RISC-V or x86, we use Homebrew to install QEMU for hardware virtualization alongside a RISC-V cross-compiler toolchain.

To start, make sure you have Apple Command Line Tools and Homebrew installed on your Mac. Open your Terminal app and update Homebrew by running brew update so that all your package formulas are up to date. If you do not have Homebrew yet, you can easily install it by getting the setup command from brew.sh.

Next, you need to install QEMU and the RISC-V cross-compiler toolchain. In modern operating systems courses, xv6 uses the 64-bit RISC-V architecture. You can install both required tools using Homebrew by running the command brew install qemu riscv64-elf-gcc in your terminal. This will install QEMU along with the GNU GCC compiler targeted for RISC-V cross-compilation. You can verify the installation by running riscv64-elf-gcc --version and qemu-system-riscv64 --version.

Once the tools are installed, you need to get the source code of xv6. Open your terminal, navigate to the folder where you want to keep your project, and clone the official repository by running git clone https://github.com/mit-pdos/xv6-riscv.git. After cloning completes, move into the project directory by running cd xv6-riscv.

Inside the project folder, you can build and boot the operating system. Run the command make qemu in your terminal. The Makefile will automatically detect your installed RISC-V cross-compiler, compile the kernel along with the user applications, and boot xv6 inside QEMU directly in your terminal window. You will see the kernel boot messages followed by the shell prompt where you can run commands like ls or echo.

When you want to stop running xv6 and exit QEMU, press Ctrl+A and then press X on your keyboard. If you ever encounter an error saying the compiler command was not found when running make qemu, open the Makefile and ensure TOOLPREFIX is set to riscv64-elf- so that it matches the executable installed by Homebrew.
