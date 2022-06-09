# Data-Encoder-Crypter-Encoded-Aes-Hidden-Startup
![resim](https://user-images.githubusercontent.com/104153626/164758152-daed2e03-b8d3-4b82-8214-dac757e9a4f6.png)

## Features
* Bit 32/64 bit
* Error Message
* Select Injector
* Fake Mesaje
* Binder ("Run Once Run Startup")
* Loader Mode
* Notification
* Single Instance
* Anti WM
* Anti Submission
* Execution Delay
* Advanced Runtime
* Exclusion Windows Defender
* Memory Bombing
* Anti File Delete
* Change Timestamp
* Hardened Name
* Exclusion Region
* Crypters Killer
* Startup Hidden
* Assembly Clone 
* Certifcate
* Extensions hta/html/src/pif/com/exe
* .net Freamwork Version 2.5 / 3/0 / 4/0 / 4.5

## Results
![resim](https://user-images.githubusercontent.com/104153626/164761269-f0d7d7e5-5144-4467-ae42-c3da5cc59add.png)


## Info 
#1 Strings

    Having plain strings stored in the binary file or in memory can help reversering attempts to be much easier.
    If the program is targeted by string detection scans you had to change the strings everytime you get detected.

#2 Some crypters

    Decrypt the string on the current stack location. Even though in some situations the stack location is overwritten on returning from a function, especially when the decryption is called from the main function the decrypted string stays on the stack for the lifetime of the stack/program thus leaking it
    Do not work with both Usermode and Kernelmode
    Greater overhead
    Require compiler optimizations enabled
    Vulnerable against default bruteforcing

Why this crypter?

skCrypter works out of the box with both Usermode + Kernelmode and compiler optimizations on/off (tested with msvsc++19). The overhead is very low and the storage of the string is at a fixed address which is controlable at every time and clearable traceless(builtin function). The encryption is randomized at every compilation and protected against default bruteforcing.


## How To use
How to use:

Compile xtea.cpp to create xtea.exe. Drag & drop file you want to encrypt (put in crypter) on xtea.exe. This will encrypt the file.

Compile shellcode_generator.c to create shellcode_generator.exe. Drag & drop file (encrypted with xtea) on shellcode_generator.exe. This will create shellcode.h which contains the bytes of encrypted file.

Make sure that shellcode.h and runPE.h are in the same directory as file.cpp. Compile file.cpp to create file.exe. Running file.exe will decrypt and run file from the first step.

file.exe stores the (encrypted) bytes of an executable in itself, when you run it, it decrypts and runs in memory those bytes, by a method called runPE. It does not drop anything on the HD.

## Media
![resim](https://user-images.githubusercontent.com/104153626/164758164-80e470c3-f736-4fb5-8554-709e79cb9e63.png)
