# ATtinyBasic
Set of functions for the ATtiny85 with minimal program size

# Usage
- Download ATtinyBasic.cpp and ATtinybasic.h
- Include the ATtinyBasic.h header file in your project

# Examples
```c++
// Pin Mode
_pinMode(0, OUTPUT);

// Digital Write
_digitalWrite(0, HIGH);

// Analog Read
_adcSetup();
int val = _analogRead(1);
```