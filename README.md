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
In the link above, we need to download the file ended with arm-none-eabi.exe
![fd07ccb07714f87de3da199ca893d39](https://user-images.githubusercontent.com/114200453/194982948-751baa37-4f7d-4ec8-8e62-43f4698f4724.png)

After downloading the .exe file, we select English/English language, click "next" to continue, click "I Agree" to agree the license and finally click "install" to install the software.

![f2c81c694915c0ca119040e12583b10](https://user-images.githubusercontent.com/114200453/194983422-3ff10b19-edc4-4a2b-96a5-89b8803f970f.png)
![ce039d3a561a96bc014d043a681d396](https://user-images.githubusercontent.com/114200453/194983429-5da56cd3-156b-4027-a27e-6b52770380b8.png)
![339b2dfbabbaa50e2521b363ca76296](https://user-images.githubusercontent.com/114200453/194983437-c9488672-c3d8-47af-9667-a3779103abd3.png)

**After installing the Toolchain, remember to check "Add path to environment variable" before finishing installing. If not, our  Developer Command Prompt will not detect arm none when we setup cmake. (I will mention it later in Command Line setup section)**

![9f8d1286abf4010098b317939c050a3](https://user-images.githubusercontent.com/114200453/194983804-2c319082-6190-4b18-a137-d847568cd72a.png)

### Cmake
In the link above, we need to download the file with windows-x86_64.msi

![f570647ccc2924d32067e050b9ccb9d](https://user-images.githubusercontent.com/114200453/194984027-3a9828f0-9d76-4168-8c95-d568453f5eea.png)

After downloading the .exe file, we click "next" to continue, check "I accept the terems in the Licence Agreement" to agree the license, check "Add CMakee to the system PATH for all users" and "next", then finally install the software.

![4f0f2bd01882c7a9d2543f03736a7f4](https://user-images.githubusercontent.com/114200453/194984317-af739a71-af3d-499f-933c-8001ced50c00.png)
![f420e4bfd1f3e5189b81937bf8afe30](https://user-images.githubusercontent.com/114200453/194984324-f3dab0d6-d829-4d0f-9ce1-cd46d46261ac.png)

### Visual Studio 2022
**For the Developer Command Prompt installation, notice that we need to download "Visual Studio 2022" instead of "VS Code"**

We need to go down to the bottom and download "Build Tools for Visual Studio 2022"
![416c4ee5e636d3c00545193ead8fe14](https://user-images.githubusercontent.com/114200453/194984785-36a86cd8-3087-4bb6-a882-46907ff27d19.png)

Make sure you select "Desktop development with C++" and check options on the right in "Optional" list as shown below.
 
![image](https://user-images.githubusercontent.com/114200453/194984469-c6549e6f-ef89-4e76-9552-3765dfdaede6.png)

### Python 3.10

For the Python installing, make sure you download Latest Python 3 Release - Python 3.10.7, then click "Install Now."

![bde3a6dbd2f12cd13f8ad3b9f088c48](https://user-images.githubusercontent.com/114200453/194985602-004777ef-2dbe-4edd-b1a8-01113b24986a.png)

### Git
In the link above, we need to click "64-bit Git for Windows Setup."

![be0c4d1aa2229f7394d8a65359ebb76](https://user-images.githubusercontent.com/114200453/194985864-79fdfd14-c6c2-437b-be86-7f51de9a0c56.png)

After downloading Git-2.38.0-64-bit.exe, we follow the instruction and download Git.

When installing Git, make sure we select "Notepad as Git's default editor", "Git from the command line as well as third-party software", "Checkout as is, commit as-is", "Use Windows' default console window" and finally "Enable experimental support for pseudo consoles".

![47a822e3b3018882710b02dcd743440](https://user-images.githubusercontent.com/114200453/194987212-bc8ba545-32f5-415a-922e-3201771e083e.png)
![ceb4988d31e885cdc37f0a0b21b0723](https://user-images.githubusercontent.com/114200453/194987222-40db2d9e-6d22-42f3-803f-2a7765a07c0e.png)
![56e69c88bdb4ac2b2df14d2eb0b2166](https://user-images.githubusercontent.com/114200453/194987228-8a1d84d3-b2f9-485b-b919-7ebb4b97428d.png)
![9182c7264331e672c10a191ca84c0fa](https://user-images.githubusercontent.com/114200453/194987234-1b46f418-3645-4a6f-a9d1-06b7bdc49524.png)
![206bba905640d706724f1286ff407d1](https://user-images.githubusercontent.com/114200453/194987245-f54b17c7-218e-4f83-9c01-836f37f9d5be.png)
![358b46be31e36657b9089443b94fdd2](https://user-images.githubusercontent.com/114200453/194987252-17f65083-869a-4803-a4a4-b9767c3f6d93.png)
![add46317c73ae65bead7400302f8779](https://user-images.githubusercontent.com/114200453/194987266-06367cc3-d465-4244-b96c-1e86208dd8cf.png)
![a7b2cf7d08b383121e3a6b737266ce1](https://user-images.githubusercontent.com/114200453/194987275-e77a8470-75bd-4b9b-97eb-29f4347ca4c8.png)
![0cbaba707b8806ca179ba9c8159dc34](https://user-images.githubusercontent.com/114200453/194987287-1ac08e6b-b52e-4fac-a46d-3d692a82203c.png)

**Congrats! You have installed all extra tools. Then you can install C SDK in Developer Command Prompt**

## Getting SDK and examples
In this section, we will download SDK and examples through Developer Command Prompt. The Raspberry Pi Pico [“getting started guide”](https://datasheets.raspberrypi.com/pico/getting-started-with-pico.pdf), section 9.2.2 includes extremely helpful guide for this part. It is very easy for you to follow each steps and get SDK.

![cdcbc1bc7e45ee6efcc15181131135b](https://user-images.githubusercontent.com/114200453/194988163-9a89c9fa-b2b3-4440-86a9-afaadab34b99.png)

*If you mistakenly downloaded VS code and followed the instruction in Chapter 2 to download SDK and examples, you can skip this part and jump to the section "Building "Hello World" from the Command Line." But before you follow the next section, I highly recommend you to download and use Visual Studio 2022 instead of VS code terminal. Using developer Command Prompt in Visual Studio 2022 is easier for you to set the path to the SDK and build files for the "hello_usb.c" in next step.*

**The started guide does not include the guide to create files named pico and Downloads, here is the instruction:**

```
C:\Users> mkdir pico
C:\Users> cd pico
C:\Users\pico> mkdir Downloads
C:\Users\pico> cd Downloads
```

Then you can follow the guide to get the SDK and examples

## Building "Hello World" From the Command Line
Then you can set the path to the SDK as follows in a Developer Command Prompt window:
```
C:\Users\pico\Downloads> setx PICO_SDK_PATH "..\..\pico-sdk"
```
After entering this command line, the command window will prompt a hint information which indicating that the setup for the environment variable is completed. **Now you need to remember to close your current Command Prompt Window and and open a second Developer Command Prompt window where this environment variable will now be set correctly before proceeding.**

Then enter the command lines below:
'''
C:\Users\pico\Downloads> cd pico-examples
C:\Users\pico\Downloads\pico-examples> mkdir build
C:\Users\pico\Downloads\pico-examples> cd build
C:\Users\pico\Downloads\pico-examples\build> cmake -G "NMake Makefiles" ..
C:\Users\pico\Downloads\pico-examples\build> nmake
'''

After entering "cmake -G "NMake Makefiles" ..", if the command window prompt a hint information which indicating that there is an error "cannot find arm none". There are several reasons:

1. you did not close your current Command Prompt Window and and open a second Developer Command Prompt after setting a path
2. you did not check "Add path to environment variable" before finishing installing Toolchain. If not, our  Developer Command Prompt will not detect arm none when we setup cmake.
3. I initially used VS code terminal and it did not work. If you also use VS code terminal, try to download and use Developer Command Prompt in Visual Studio 2022.

If 









