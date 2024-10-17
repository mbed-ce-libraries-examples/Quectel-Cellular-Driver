# Quectel-Cellular-Driver library for MbedCE
Library for interfacing Quectel modems (BC95, BG96, EC2X, M26, UG96, EG915) under MbedCE.

## How to start
1. Create a new project according to [MbedCE instructions](https://github.com/mbed-ce/mbed-os/wiki)
2. Add this as submodule to your project via `git submodule add --depth 1 https://github.com/mbed-ce-libraries-examples/Quectel-Cellular-Driver Quectel-Cellular-Driver`
3. In the top level `CMakeLists.txt` (in root of your project) should be add `add_subdirectory(Quectel-Cellular-Driver)` (under `add_subdirectory(mbed-os)`). For more check [this wiki page](https://github.com/mbed-ce/mbed-os/wiki/MbedOS-configuration#libraries-in-your-application)
4. In the top level `CMakeLists.txt`, link the library for the modem you want to your application.  For example:
```
target_link_libraries(MyApp quectel-ec2x)
```
5. To configure the driver, define a callback like the below in your main file:

```cpp
#include "QUECTEL_EC2X.h"

CellularDevice *CellularDevice::get_default_instance()
{
    static BufferedSerial serial(<your serial tx pin>,
                                 <your serial rx pin>,
                                 <serial baudrate>);

    // Optional, if your hardware supports flow control, set the flag below to match
    serial.set_flow_control(SerialBase::RTSCTS, <your RTS pin>, <your CTS pin>);
    
    static QUECTEL_EC2X device(&serial,
                               <modem PWR pin.  Optional, can be NC>,
                               <modem PWR/RST polarity.  true = PWR and RST disable device when high, false = PWR and RST disable device when low.>
                               <modem RST pin.  Required.>
                               <modem flow control, Optional);
    return &device;
}
```

7. Build the project

## Example code
//TODO
```
```
## Description

### Status:
This library was tested (07/2024) with Nucleo-F446RE, VS-Code under Win11, GCC 11.3.1 and MbedCE library

