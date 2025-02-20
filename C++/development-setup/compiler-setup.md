# How to setup visual studio code for C++ (per operating system)
My chosen C++ compilation method is the clang compiler. Keep in mind that I am a software engineer that doesn't work in compiler developing. The reason that I say this is because I am not usually concerned with squeezing every last bit of performance out of my system. Rather, I'd like to develop products that work and develop them fast. If you are a performance freak, the standard compiler for use is gcc. This is just what works best for me.

Across all systems, I will be using the clang compiler in my development environment for the following reasons:

- clang has better and more informative error messages than gcc.
- clang has better integration with tools. i.e. I can create a format file to format all my code.
- clang uses the LLVM backend which allows for more flexible and reliable code generation.


- ### [WindowsOS](#windowsos-1)
- ### MacOS
- ### Linux 

## WindowsOS
For this tutorial you may refer to the youtube video attached [here](https://www.youtube.com/watch?v=5OSO8IRlyXc&ab_channel=SetupTech%21) or continue through the steps as normal to get your compiler setup. This tutorial works on Windows 10 and 11 operating systems.

1) Go to https://www.msys2.org/

2) Download the installer while not changing anything about its installation location.

3) Once installed, open the MYSYS UCRT64 environment.

4) Run the following commands one at a time and back to back. Say yes to installing all:

```
pacman -S mingw-w64-x86_64-clang
pacman -S mingw-w64-x86_64-clang-tools-extra
```

5) Now launch the file explorer and go to the installation location of mysys and find the mingw64 bin folder. The path should look like this if you never changed the installation location:

```
C:\msys64\mingw64\bin
```

6) Head over to "view advanced system settings" and click on Environment Variables...

7) Under "System Variables," click on the "Path" variable, click "New" on windows 11 or just add a ";" and paste the path from step 5.

8) open CMD and type "clang++" to see if the system recognizes the command.

9) Open/[install](https://code.visualstudio.com/docs/setup/windows#_install-vs-code-on-windows) visual studio code.

10) Under Extensions, install the following extensions:

- [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner).
- [clangd](https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd)
- [C/C++](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)

11) Go to the Code Runner extension and access the extension settings

12) Type " save" and enable "Save All Files Before Run."

13) Type " exe" and under "Code-runner: Executor Map," click "Edit in settings.json,"

14) Look for c and cpp and change wherever you see "gcc" with "clang" for C and "clang++" for C++. Save the file.
- The executor map allows us to see which commands are being used to run our projects. That is why we change the commands for C/C++.

15) Type " terminal" and then enable "Code-runner: Run In Terminal." 
- This will send code output to the terminal instead of the "Output" window.

16) Restart VS Code and create a simple hello world program to verify that settings are working.