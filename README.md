# Amazon FreeRTOS HelloWorld Apps for ESP32 on Windows

Minimum settings to build your own application on Amazon FreeRTOS.

## Requirements

- Windows10
- Python3
- Git

## Step
### Get repository
Get repository and submodules.

```cmd
git clone --recursive https://github.com/yomon8/amazon-freertos-hello-world-win-esp32.git
```

or

```cmd
git clone https://github.com/yomon8/amazon-freertos-hello-world-win-esp32.git
cd amazon-freertos-hello-world-win-esp32
git submodule update --init --recursive
```

### Install ESP-IDF `V4.2`

Install ESP-IDF,

```cmd
echo v4.2 > amazon-freertos\vendors\espressif\esp-idf\version.txt
amazon-freertos\vendors\espressif\esp-idf\install.bat
```

Setup ESP-IDF environment,

```cmd
amazon-freertos\vendors\espressif\esp-idf\export.bat
```

Check path,

```cmd
> where cmake
C:\Users\your.user.name\.espressif\tools\cmake\3.13.4\bin\cmake.exe
```


### Generate Build Files
To generate the hello world application build files with CMake,

```cmd
cmake -S . -B build -DCMAKE_TOOLCHAIN_FILE=amazon-freertos\tools\cmake\toolchains\xtensa-esp32.cmake -GNinja
```

### Build and Falsh to ESP32
Set serial port and flash application,
```cmd
set ESPPORT=COM6
cmake --build build --target flash
```

### Monitor
To monitor the output,

```cmd
set ESPPORT=COM6
idf.py monitor
```

Output example,

```
Start
HelloWorld! 0
HelloWorld! 1
HelloWorld! 2
HelloWorld! 3
HelloWorld! 4
HelloWorld! 5
HelloWorld! 6
HelloWorld! 7
HelloWorld! 8
HelloWorld! 9
Restart
...
```
