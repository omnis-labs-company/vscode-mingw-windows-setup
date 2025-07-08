# vscode-opencv-mingw-windows-guide

MinGW(MSYS2) + OpenCV + CPP + VS Code on Windows: Complete Setup & Configuration Guide
A step-by-step guide to setting up a modern C/C++ development environment on Windows using MinGW-w64 and Visual Studio Code.

This repository guides you through configuring a powerful and productive C/C++ development workflow on Windows, using MinGW-w64 environment as your development environment and Visual Studio Code as your editor and debugger.

Prerequisites
Windows OS
Visual Studio Code
MinGW-w64
C/C++ Extension for VS Code
Installing MinGW-w64
Download the MinGW-w64 installer or from the official website.
Install MinGW-w64.
Typical architecture: x86_64.
Note the installation path (e.g., C:\mingw-w64\mingw64\bin).
Configuring Environment Variables
Open System Properties > Advanced > Environment Variables.
Edit the PATH system variable to include the MinGW bin directory (e.g., C:\mingw-w64\mingw64\bin).




Open CMD and run:

sh


Copy code
   gcc --version
   g++ --version
   ```
   to confirm successful installation.

---

## Setting Up Visual Studio Code

1. Install [C/C++ extension for VS Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools).
2. Create a project folder and open it in VS Code.

---

## VS Code Configuration Files

Create a `.vscode` folder in your project root for configuration files.

### `tasks.json`: Build Automation

json
{
“version”: “2.0.0”,
“tasks”: [
{
“label”: “build active file”,
“type”: “shell”,
“command”: “g++”,
“args”: [
"-g",
"${file}",
"-o",
"${fileDirname}/${fileBasenameNoExtension}.exe"
],
“group”: {
“kind”: “build”,
“isDefault”: true
}
}
]
}


### launch.json: Debug Configuration


json


Copy code
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "C/C++: gcc build and debug active file",
      "type": "cppdbg",
      "request": "launch",
      "program": "${fileDirname}/${fileBasenameNoExtension}.exe",
      "args": [],
      "stopAtEntry": false,
      "cwd": "${fileDirname}",
      "environment": [],
      "externalConsole": true,
      "MIMode": "gdb",
      "miDebuggerPath": "C:/mingw-w64/mingw64/bin/gdb.exe", // Update this to your actual path
      "setupCommands": [
        {
          "description": "Enable pretty-printing for gdb",
          "text": "-enable-pretty-printing",
          "ignoreFailures": true
        }
      ]
    }
  ]
}

Building and Debugging Sample Code
Create a simple main.cpp:
#include <iostream>
int main() {
    std::cout << "Hello, VS Code + MinGW!" << std::endl;
    return 0;
}
Press Ctrl+Shift+B to build.
Press F5 to debug.
Troubleshooting & Tips
If VS Code can’t find headers, configure includePath in .vscode/c_cpp_properties.json.
Make sure miDebuggerPath matches your gdb.exe absolute path.
Use the integrated terminal for running and testing executables.
References
MinGW-w64 Official Site
VS Code C/C++ Docs
MinGW-w64 Downloads
License
This project is licensed under the MIT License.

If you want the exact file structure (folders/files example) or want to add “badges,” sample issues/prs, or markdown tips for contributors, let me know!
Would you also like c_cpp_properties.json or any other specific sample content included?
