
[![Arduino CI](https://github.com/RobTillaart/74HC154/workflows/Arduino%20CI/badge.svg)](https://github.com/marketplace/actions/arduino_ci)
[![Arduino-lint](https://github.com/RobTillaart/74HC154/actions/workflows/arduino-lint.yml/badge.svg)](https://github.com/RobTillaart/74HC154/actions/workflows/arduino-lint.yml)
[![JSON check](https://github.com/RobTillaart/74HC154/actions/workflows/jsoncheck.yml/badge.svg)](https://github.com/RobTillaart/74HC154/actions/workflows/jsoncheck.yml)
[![GitHub issues](https://img.shields.io/github/issues/RobTillaart/74HC154.svg)](https://github.com/RobTillaart/74HC154/issues)

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/RobTillaart/74HC154/blob/master/LICENSE)
[![GitHub release](https://img.shields.io/github/release/RobTillaart/74HC154.svg?maxAge=3600)](https://github.com/RobTillaart/74HC154/releases)
[![PlatformIO Registry](https://badges.registry.platformio.org/packages/robtillaart/library/74HC154.svg)](https://registry.platformio.org/libraries/robtillaart/74HC154)


# 74HC154

Arduino library for the 74HC154 4-to-16 line decoder/demultiplexer.


## Description

This library controls the 74HC154 4 to 6 line decoder. 
With 4 IO lines one can select one of 16 output lines. 


#### Related

- https://github.com/RobTillaart/74HC138  (3 to 8 selector)
- https://github.com/RobTillaart/74HC154  (4 to 16 selector)
- https://github.com/RobTillaart/HC4051  (1x8 mux)
- https://github.com/RobTillaart/HC4052  (2x4 mux)
- https://github.com/RobTillaart/HC4053  (3x2 mux)
- https://github.com/RobTillaart/HC4067  (1x16 mux)


## Interface

```cpp
#include "74HC154.h"
```

#### Constructor

- **74HC154(uint8_t pin0, uint8_t pin1, uint8_t pin2, uint8_t pin3, uint8_t pinEnable = 255)** 
set the 4 selection IO lines from pin numbers.
Optionally set the enable pin, connect to E1 or E2, see datasheet.
- **74HC154(uint8_t \* pins, uint8_t pinEnable = 255)** 
set the 4 selection IO lines from an array.
The pins array should have at least 4 elements.
Optionally set the enable pin, connect to E1, see datasheet.


#### Select line

- **bool setLine(uint8_t line)** set line 0 .. 15. Returns false if out of range.
- **uint8_t getLine()** returns 0 .. 15
- **void nextLine()** selects the next line, wraps back to 0 if needed.
- **void prevLine()** selects the previous line, wraps to 15 if needed.


#### Enable

Works only if enable line is set in constructor.

- **void enable()** enables output / selection.
- **void disable()** disables output / selection.
- **bool isEnabled()** checks if line is enabled.


## Future

#### Must

- improve documentation
- get hardware to test

#### Should


#### Could


#### Wont


## Support

If you appreciate my libraries, you can support the development and maintenance.
Improve the quality of the libraries by providing issues and Pull Requests, or
donate through PayPal or GitHub sponsors.

Thank you,


