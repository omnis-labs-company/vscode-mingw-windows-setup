# vscode-opencv-mingw-windows-guide
MinGW(MSYS2) + OpenCV + CPP + VS Code on Windows: Complete Setup & Configuration Guide
A step-by-step guide to setting up a modern C/C++ development environment on Windows using MinGW-w64 and Visual Studio Code.

This repository guides you through configuring a powerful and productive C/C++ development workflow on Windows, using MinGW-w64 environment as your development environment and Visual Studio Code as your editor and debugger.

## Prerequisites
Windows OS
Visual Studio Code
MinGW-w64
C/C++ Extension for VS Code
Installing MinGW-w64
Download the MinGW-w64 installer or from the official website.
Check below
https://www.mingw-w64.org/getting-started/msys2/

After downloading the installer, install MinGW-w64.
And then, open C:\msys64\mingw64.exe

Once opening the terminal, install packages like compilers, debuggers, and opencv 

```bash
pacman -S mingw-w64-x86_64-toolchain
pacman -S mingw-w64-x86_64-gdb
pacman -S mingw-w64-x86_64-opencv
```

Note the installation path (e.g., C:\msys64\mingw64\bin).
After installation, configure environment variables.
Open System Properties > Advanced > Environment Variables.
Edit the PATH system variable to include the MinGW bin directory (e.g., C:\msys64\mingw64\bin).


Open CMD and run:
```bash
   gcc --version
   g++ --version
```
to confirm successful installation.


## Setting Up Visual Studio Code
1. Install C/C++ extension for VS Code.
2. Create a project folder and open it in VS Code.

## VS Code Configuration Files
The sample files are attached in this repository.


## Troubleshooting & Tips
Check the path of your g++ compiler by entering "which g++" in mingw64.exe terminal.
Make sure "Path" is set before opening vs code.


## License
This project is licensed under the MIT License.
