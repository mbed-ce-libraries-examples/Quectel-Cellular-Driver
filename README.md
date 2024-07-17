# Quectel-Cellular-Driver library for MbedCE
Library for interfacing Quectel modems (BC95, BG96, EC2X, M26, UG96) under MbedCE.

## How to start
1. Create a new project according to [MbedCE instructions](https://github.com/mbed-ce/mbed-os/wiki)
2. Add this as submodule to your project via `git submodule add --depth 1 https://github.com/mbed-ce-libraries-examples/Quectel-Cellular-Driver Quectel-Cellular-Driver`
3. In the top level `CMakeList.txt` (in root of your project) should be add `add_subdirectory(Quectel-Cellular-Driver)` (under `add_subdirectory(mbed-os)`). For more check [this wiki page](https://github.com/mbed-ce/mbed-os/wiki/MbedOS-configuration#libraries-in-your-application)
4. In the top level `CMakeList.txt` also do not forget link library `mbed-cellular`
5. In `mbed_app.json5` file add requested driver component. For example
```
   "target.components_add": [
      "QUECTEL_UG96"
   ]
```
6. Make your code.
7. Build the project

## Example code
//TODO
```
```
## Description

### Status:
This library was tested (07/2024) with Nucleo-F446RE, VS-Code under Win11, GCC 11.3.1 and MbedCE library

