# Water Blaster Security Project

## Overview

This project is part of the CMU Security Expert Course, with the goal of making a device that controls a water blaster secure. The project involves implementing various security measures to ensure the safe and reliable operation of the device.

## Team

**Team #2: S.H.I.E.L.D.**

### Members
- **Jin Woo Kim** (deenu0224@gmail.com)
- **Jang Hyun Ko** (rheels87@gmail.com)
- **Yoon Se Han** (yoon312@gmail.com)
- **Nam Il Lee** (lni148686@gmail.com)
- **Ji Hyun Jang** (zzhyuny@gmail.com)
- **Hoon Min Lee** (jennyleelg2004@gmail.com)

## Objectives

1. Secure the control mechanism of the water blaster.
2. Implement authentication and authorization measures.
3. Ensure data integrity and confidentiality.
4. Conduct thorough security testing and validation.

## Server Build and Execution Instructions

### 1. Build
1. Navigate to the `DemoCannon` folder.
2. Run the following command to build the project:
    ```sh
    $ ./build.sh
    ```

### 2. Create and Install Cryptographic Keys
1. Connect to the server via SSH.
2. Navigate to the directory where the `DemoCannon` program is located.
3. Run the following commands to create two keys:
    ```sh
    $ dd if=/dev/urandom of=./enc_key bs=1 count=32
    $ dd if=/dev/urandom of=./hmac_key bs=1 count=32
    ```

### 3. Execution
Run the following command to start the program:
    ```sh
    $ ./run.sh
    ```

## Application Build and Execution Instructions

### OpenSSL Library

1. Download OpenSSL:
    - First, download the precompiled OpenSSL libraries suitable for your project's architecture (32-bit or 64-bit) from the official [OpenSSL website](https://slproweb.com/products/Win32OpenSSL.html) or another trusted source.

2. Prepare OpenSSL Directory:
    - Create a directory in your project structure where OpenSSL libraries and headers will reside. For example, `C:\OpenSSL` or `C:\Libraries\OpenSSL`.

3. Include OpenSSL Headers:
    - Open your Visual Studio solution.
    - Right-click on your project in Solution Explorer and select Properties.
    - Navigate to Configuration Properties > C/C++ > General.
    - Add the path to the OpenSSL `include` directory in Additional Include Directories. For example, if your OpenSSL headers are in `C:\OpenSSL\include`, add `C:\OpenSSL\include` to the list.

4. Link OpenSSL Libraries:
    - Still in the project properties window, navigate to Configuration Properties > Linker > General.
    - Add the path to the OpenSSL `lib` directory in Additional Library Directories. For instance, if your OpenSSL libraries are in `C:\OpenSSL\lib`, add `C:\OpenSSL\lib` to the list.

5. Specify OpenSSL Libraries:
    - Under Configuration Properties > Linker > Input, add the required OpenSSL libraries to Additional Dependencies. Depending on your project needs, you might need to link against libraries like `libcrypto.lib` and `libssl.lib`.

### Credential Manager Library

1. Open Your Project:
    - Open your solution in Visual Studio 2022.

2. Access Project Properties:
    - Right-click on your project in the Solution Explorer.
    - Select Properties.

3. Navigate to Linker Settings:
    - In the Project Properties window, go to Configuration Properties > Linker > Input.

4. Add Additional Dependencies:    
    - In the Additional Dependencies field, add `Advapi32.lib`.

### Compile Option
- **C++**: 
    ```sh
    /permissive- /ifcOutput "x64\Release\" /GS /GL /W3 /Gy /Zc:wchar_t /I"..\..\..\opencv\build\include" /I"..\..\Common" /I"C:\Program Files (x86)\Windows Kits\10\Include\\shared" /I"C:\Program Files (x86)\Windows Kits\10\Include\\um" /Zi /Gm- /Od /sdl /Fd"x64\Release\vc143.pdb" /Zc:inline /fp:precise /D "NDEBUG" /D "_WINDOWS" /D "WIN32" /D "OPENSSL_NO_ASM" /D "_UNICODE" /D "UNICODE" /errorReport:prompt /WX- /Zc:forScope /Gd /Oi /MD /FC /Fa"x64\Release\" /EHsc /nologo /Fo"x64\Release\" /Fp"x64\Release\LgClientDisplay.pch" /diagnostics:column
    ```

- **Link**:
    ```sh
    /OUT:"{PROJECT_PATH}\x64\Release\LgClientDisplay.exe" /MANIFEST /LTCG:incremental /NXCOMPAT /PDB:"{PROJECT_PATH}\x64\Release\LgClientDisplay.pdb" /DYNAMICBASE "libssl.lib" "libcrypto.lib" "Crypt32.lib" "kernel32.lib" "user32.lib" "gdi32.lib" "winspool.lib" "comdlg32.lib" "advapi32.lib" "shell32.lib" "ole32.lib" "oleaut32.lib" "uuid.lib" "odbc32.lib" "odbccp32.lib" /DEBUG /MACHINE:X64 /OPT:REF /PGD:"{PROJECT_PATH}\x64\Release\LgClientDisplay.pgd" /SUBSYSTEM:WINDOWS /MANIFESTUAC:"level='asInvoker' uiAccess='false'" /ManifestFile:"x64\Release\LgClientDisplay.exe.intermediate.manifest" /LTCGOUT:"x64\Release\LgClientDisplay.iobj" /OPT:ICF /ERRORREPORT:PROMPT /ILK:"x64\Release\LgClientDisplay.ilk" /NOLOGO /LIBPATH:"{OPENSSL_PATH}\lib" /TLBID:1
    ```
