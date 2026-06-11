# ATtinyBasic
Set of functions for the ATtiny85 with minimal program size

# Usage
- Download the files in `code/`
- Include whatever header you want to use in your project

# Full Example
```c++
// ---------- Required for TinySoftwareSerial.h ----------
#define USE_SOFTWARE_SERIAL 1
#define SOFT_TX_ONLY 1
#define ANALOG_COMP_DDR   DDRB
#define ANALOG_COMP_PORT  PORTB
#define ANALOG_COMP_PIN   PINB
#define ANALOG_COMP_AIN0_BIT  1 // PB0 = RX
#define ANALOG_COMP_AIN1_BIT  0 // PB1 = TX
// -------------------------------------------------------

#include "TinySoftwareSerial.h"
#include "ATTinyBasic.h"

int main() {
    _adcSetup();
    _pinMode(PB2, OUTPUT);
    Serial.begin(9600);

    while (1) {
        _digitalWrite(PB2, HIGH);
        _delay_ms(1000);
        _digitalWrite(PB2, LOW);
        _delay_ms(1000);
        Serial.println(_analogRead(PB3));
        _delay_ms(1000);
    }
}
```