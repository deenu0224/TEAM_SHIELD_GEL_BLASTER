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
