# ESE519_Lab2_Setup_Windows
University of Pennsylvania, ESE 5190: Intro to Embedded Systems, Lab 2A

    Sizhe Ma
        masizhee@seas.upenn.edu
    Tested on:  Thinkpad X1, Windows 10 Pro, Intel(R) Core(TM) i7-8650U CPU @ 1.90GHz   2.11 GHz
## Setting Up for SDK on your Windows Machine for Raspberry Pi Pico.
In this lab, firstly we need to set up laptop/PC for RP2040 development using the official C/C++ SDK to compile and run example code on our board.

If you are using Windows machine, you can follow the following steps to completly set up the environment. the Raspberry Pi Pico [“getting started guide”](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf) includes the whole process of setups. See Section 9.2. Building on MS Windows or the steps below for the specific instruction.

**Even though Chapter2. The SDK also includes the instruction to download SDK and examples, it does not include the instruction for installing extra tools/path to the SDK/cmake setup. See 9.2 for the full instruction.**

## Install the extra tools
Since we use Windows OS, there are several extra tools/software we need to install first:
1. [Arm GNU Toolchain](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)
2.  [CMake](https://cmake.org/download/)
3.  [Build Tools for Visual Studio 2022](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022)
4.  [Python 3.10](https://www.python.org/downloads/windows/)
5.  [Git](https://git-scm.com/download/win)

### Arm GNU Toolchain
In the link above, we need to download the file with arm-none-eabi.exe
![fd07ccb07714f87de3da199ca893d39](https://user-images.githubusercontent.com/114200453/194982948-751baa37-4f7d-4ec8-8e62-43f4698f4724.png)

