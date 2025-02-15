# MattairTech MT-D21E (ATsamD21EXXA)

```
============================= MattairTech MT-D21E (ATsamD21EXXA) ========================
Other  COM    PWM   Analog  INT  Arduino*             Arduino*  INT   PWM     COM   Other
=========================================================================================
                                      -------------------
Xin32                                | A0            RST |                           BOOT
Xout32                               | A1            NC  |
DAC                   *            2 | A2            NC  |
REFA                  *            3 | A3            A31 | 31    *   TCC11   RX3   SWDIO*
REFB                  *      *     4 | A4            A30 | 30    *   TCC10   TX3   SWDCLK
                      *      *     5 | A5            NC  |
                      *            6 | A6            A28 | 28    *                   LED
VM                    *            7 | A7            A27 | 27    *                   BTNA
  SDA1/MISO1  TCC00   *     NMI    8 | A8            A23 | 23    *   TC41     SS
   SCL1/SS1   TCC01   *      *     9 | A9            A22 | 22    *   TC40     MISO
      TX1     TCC02   *           10 | A10           A19 | 19    *            SCK
      RX1     TCC03   *           11 | A11           A18 | 18    *            MOSI
   TX2/MOSI1   TC30          *    14 | A14           A17 | 17    *   TCC21    SCL/RX4
    RX2/SCK1   TC31               15 | A15           A16 | 16    *   TCC20    SDA/TX4
                                     | NC            NC  |
                                     | NC            NC  |
                                     | Vbus          3.3V|   * Button B available on 31.
USB D-       TC50                    | A24-  _____   Vcc |
USB D+       TC51                    | A25+ |     |  Vin |
                                     | Gnd  | USB |  Gnd |
                                      -------------------

* Most pins can be used for more than one function. The port pin number printed
  on the board is also used in Arduino (but without the 'A') for all of the supported
  functions (ie: digitalRead(), analogRead(), analogWrite(), attachInterrupt(), etc.).
* When USB CDC is enabled, Serial refers to SerialUSB, otherwise it refers to Serial1.
* Leave pin A30 floating (or use external pullup) during reset.
* DO NOT connect voltages higher than 3.3V!
* Tone available on TC5.
```

## Pins descriptions for the MattairTech MT-D21E
```
============================================================================================================================================
Arduino	| Silk	| Port	| Alternate Function	| Comments (! means not used with this peripheral assignment)
--------|-------|-------|-----------------------|-------------------------------------------------------------------------------------------
0	| A0	| PA00	| Xin32			| Xin32
1	| A1	| PA01	| Xout32		| Xout32
2	| A2	| PA02	|			| !EIC/EXTINT[2] ADC/AIN[0] PTC/Y[0] DAC/VOUT
3	| A3	| PA03	| REFA			| !EIC/EXTINT[3] REF/ADC/VREFA REF/DAC/VREFA ADC/AIN[1] PTC/Y[1]
4	| A4	| PA04	| REFB			| EIC/EXTINT[4] REF/ADC/VREFB ADC/AIN[4] AC/AIN[0] PTC/Y[2] !SERCOM0/PAD[0] !TCC0/WO[0]
5	| A5	| PA05	|			| EIC/EXTINT[5] ADC/AIN[5] AC/AIN[1] PTC/Y[3] !SERCOM0/PAD[1] !TCC0/WO[1]
6	| A6	| PA06	|			| !EIC/EXTINT[6] ADC/AIN[6] AC/AIN[2] PTC/Y[4] !SERCOM0/PAD[2] !TCC1/WO[0]
7	| A7	| PA07	| Voltage Divider	| !EIC/EXTINT[7] ADC/AIN[7] AC/AIN[3] PTC/Y[5] !SERCOM0/PAD[3] !TCC1/WO[1]
8	| A8	| PA08	| SDA1/MISO1		| EIC/NMI ADC/AIN[16] PTC/X[0] !SERCOM0/PAD[0] SERCOM2/PAD[0] TCC0/WO[0] !TCC1/WO[2]
9	| A9	| PA09	| SCL1/SS1		| EIC/EXTINT[9] ADC/AIN[17] PTC/X[1] !SERCOM0/PAD[1] SERCOM2/PAD[1] TCC0/WO[1] !TCC1/WO[3]
10	| A10	| PA10	| TX1			| !EIC/EXTINT[10] ADC/AIN[18] PTC/X[2] SERCOM0/PAD[2] !SERCOM2/PAD[2] !TCC1/WO[0] TCC0/WO[2]
11	| A11	| PA11	| RX1			| !EIC/EXTINT[11] ADC/AIN[19] PTC/X[3] SERCOM0/PAD[3] !SERCOM2/PAD[3] !TCC1/WO[1] TCC0/WO[3]
12	| ---	| ----	| NOT A PIN		| NOT A PIN
13	| ---	| ----	| NOT A PIN		| NOT A PIN
14	| A14	| PA14	| Xin, TX2/MOSI1	| EIC/EXTINT[14] SERCOM2/PAD[2] TC3/WO[0] !TCC0/WO[4] Xin, HOST_ENABLE
15	| A15	| PA15	| Xout, RX2/SCK1	| !EIC/EXTINT[15] SERCOM2/PAD[3] TC3/WO[1] !TCC0/WO[5] Xout
16	| A16	| PA16	| SDA/TX4 w/pullup	| EIC/EXTINT[0] PTC/X[4] SERCOM1/PAD[0] SERCOM3/PAD[0] TCC2/WO[0] !TCC0/WO[6]
17	| A17	| PA17	| SCL/RX4 w/pullup	| EIC/EXTINT[1] PTC/X[5] SERCOM1/PAD[1] SERCOM3/PAD[1] TCC2/WO[1] !TCC0/WO[7]
18	| A18	| PA18	| SPI			| EIC/EXTINT[2] PTC/X[6] !SERCOM1/PAD[2] SERCOM3/PAD[2] !TC3/WO[0] !TCC0/WO[2]
19	| A19	| PA19	| SCK			| EIC/EXTINT[3] PTC/X[7] !SERCOM1/PAD[3] SERCOM3/PAD[3] !TC3/WO[1] !TCC0/WO[3]
20	| ---	| ----	| NOT A PIN		| NOT A PIN
21	| ---	| ----	| NOT A PIN		| NOT A PIN
22	| A22	| PA22	| MISO			| EIC/EXTINT[6] PTC/X[10] SERCOM3/PAD[0] TC4/WO[0] !TCC0/WO[4]
23	| A23	| PA23	| SS			| EIC/EXTINT[7] PTC/X[11] SERCOM3/PAD[1] TC4/WO[1] !TCC0/WO[5]
24	| A24-	| PA24	| USB_NEGATIVE		| USB/DM TC5/WO[0]
25	| A25+	| PA25	| USB_POSITIVE		| USB/DP TC5/WO[1]
26	| ---	| ----	| NOT A PIN		| NOT A PIN
27	| A27	| PA27	| Button A		| EIC/EXTINT[15] Button A
28	| A28	| PA28	| LED			| EIC/EXTINT[8] LED
29	| ---	| ----	| NOT A PIN		| NOT A PIN
30	| A30	| PA30	| SWDCLK / TX3		| EIC/EXTINT[10] SERCOM1/PAD[2] TCC1/WO[0] SWD CLK, leave floating during boot
31	| A31	| PA31	| Button B / SWDIO / RX3| EIC/EXTINT[11] SERCOM1/PAD[3] TCC1/WO[1] Button B SWD IO
--	| RST	| ----	|			| Reset, BOOT (double tap bootloader entry)
============================================================================================================================================

* Most pins can be used for more than one function. The port pin number printed
  on the board is also used in Arduino (but without the 'A') for all of the supported
  functions (ie: digitalRead(), analogRead(), analogWrite(), attachInterrupt(), etc.).
* The following Arduino pin numbers are not mapped to a physical pin: 12, 13, 20, 21, 26, and 29.
* Pins 24 and 25 are by default in use by USB (USB_NEGATIVE and USB_POSITIVE).
* TC5(D21) is available on these pins otherwise. The tone library uses TC5.
* A0 and A1 are by default connected to the 32.768KHz crystal.
* Leave pin A30 floating (or use external pullup) during reset.
```


## Board Configuration Notes

* **Crystals**
  * Either the 32.768KHz crystal or the 16MHz crystal can be used. Be sure to set the correct solder jumpers.
  * The bootloader does not use an external crystal by default. Double-tap the reset button to enter manually.

* **LED (LED_BUILTIN)**
  * Bring the pin HIGH to turn the LED on.
  * The LED is enabled (solder jumper) by default.

* **Buttons (BUTTON_BUILTIN)**
  * Button A (BTNA) is connected to pin 27 by default (BUTTON_BUILTIN).
  * Button B (BTNB) is connected to the Reset pin by default, but can be connected to pin 31 via the solder jumper.
  * Pressing the button will bring the pin LOW. The pullup must be enabled first.
  * If the debouncing capacitor is connected, delay reading the pin at least 6ms after turning on the pullup.

* **GPIO** 
  * All pins (including analog) support INPUT, OUTPUT, INPUT_PULLUP, and INPUT_PULLDOWN.
  * Each pin can source or sink a maximum of 7 mA (when PER_ATTR_DRIVE_STRONG is set for the pin, enabled by default).
  * Internal pull-up and pull-down resistors of 20-60 Kohms (40Kohm typ., disconnected by default).

* **Analog Inputs**
  * 10 pins can be configured as ADC analog inputs.
  * Each pin measures from ground to 3.3 volts by default.
  * Each pin provides 10 bits of resolution (1024 values) by default.
  * 12-bit resolution supported by using the analogReadResolution() function.
  * The upper end of the measurement range can be changed using the analogReference() function.
  * A reference voltage can be connected to REFA or REFB. In these cases, the capacitors should be enabled via the solder jumpers.

* **DAC**
  * One analog output is available on pin 2.
  * Provides a 10-bit voltage output with the analogWrite() function.

* **PWM**
  * 12 pins can be configured as PWM outputs.
  * Each pin provides 8 bits of resolution (256 values) by default.
  * 12-bit resolution supported by using the analogWriteResolution() function.

* **External Interrupts**
  * 14 pins can be configured with external interrupts.

* **SERCOM**
  * 4 SERCOM are available.
  * Up to 4 UART instances
  * Up to 2 SPI instances
  * Up to 2 WIRE (I2C) instances
  * The WIRE pullup resistors are enabled by default.



## PinDescription table format

### Note that in 1.6.18-beta-b1 a new compact table format was added.
The standard PinDescription table uses 12 bytes per pin. Define PIN_DESCRIPTION_TABLE_SIMPLE
to use a more compact format that uses only 4 bytes per pin (currently only available
for the D11 chips). In this case, the PinType, PinAttribute, and GCLKCCL columns are not used
(they are not required). Additionally, the SetPortPin() and SetExtIntADC() macros are used to
pack Port and Pin into the PortPin column, and ExtInt and ADCChannelNumber into the ExtIntADC
column. Note that external libraries that reference the PinDescription table directly (uncommon)
will no longer work. This define can be combined with the PIN_MAP_COMPACT define, which
is available in variant.h of the D11 variants. This can save from 10's to over 200 bytes.

### Note that a new column (GCLKCCL) was added for 1.6.8-beta-b0.
MATTAIRTECH_ARDUINO_SAMD_VARIANT_COMPLIANCE in variant.h is used to track versions.
If using board variant files with the old format, the new core will still read the
table the old way, losing any new features introduced by the new column. Additionally,
new definitions have been added for D51, L21, and C21 support.

### Each pin can have multiple functions.
The PinDescription table describes how each of the pins can be used by the Arduino
core. Each pin can have multiple functions (ie: ADC input, digital output, PWM,
communications, etc.), and the PinDescription table configures which functions can
be used for each pin. This table is mainly accessed by the pinPeripheral function in
wiring_private.c, which is used to attach a pin to a particular peripheral function.
The communications drivers (ie: SPI, I2C, and UART), analogRead(), analogWrite(),
analogReference(), attachInterrupt(), and pinMode() all call pinPeripheral() to
verify that the pin can perform the function requested, and to configure the pin for
that function. Most of the contents of pinMode() are now in pinPeripheral().

### Pin Mapping
There are different ways that pins can be mapped. Typically, there is no relation
between the arduino pin number used, and the actual port pin designator. Thus, the 
pcb must be printed with the arduino numbering, otherwise, if the port pin is printed,
a cross reference table is needed to find the arduino pin number. However, this results
in the least amount of space used by the table. Another method, used by default by the
MT-D21E and MT-D11, maps Arduino pin numbers to the actual port pin number (ie: Arduino
pin 28 = Port A28). This works well when there is only one port (or if the PORTB pins
are used for onboard functions and not broken out). PIO_NOT_A_PIN entries must be added
for pins that are used for other purposes or for pins that do not exist (especially the
D11), so some FLASH space may be wasted. For an example of both types, see variant.cpp
from the MT-D11 variant. The Xeno combines both methods, using the actual port pin 
designators from both PORTA and PORTB for arduino numbers 0-31 (ie: B1=1, A2=2), then
using arduino numbering only above 31. For 0-31 only one pin from PORTA or PORTB can be
used, leaving the other pin for some number above 31.

**See [WVariant.h](https://github.com/mattairtech/ArduinoCore-samd/tree/master/cores/arduino/WVariant.h) for the definitions used in the table.**

### Port
This is the port (ie: PORTA). Not used with PIN_DESCRIPTION_TABLE_SIMPLE.

### Pin
This is the pin (bit) within the port. Valid values are 0-31. Not used with
PIN_DESCRIPTION_TABLE_SIMPLE.

### SetPortPin()
When PIN_DESCRIPTION_TABLE_SIMPLE is defined, Port and Pin are combined into one column
using the SetPortPin() packing macro: SetPortPin(PORTA, 2). If the pin is not usable,
use SetPortPin(NOT_A_PORT, 0).

### PinType
This indicates what peripheral function the pin can be attached to. In most cases,
this is PIO_MULTI, which means that the pin can be anything listed in the PinAttribute
field. It can also be set to a specific peripheral. In this case, any attempt to
configure the pin (using pinPeripheral or pinMode) as anything else will fail (and
pinPeripheral will return -1). This can be used to prevent accidental re-configuration
of a pin that is configured for only one function (ie: USB D- and D+ pins). If a pin
is not used or does not exist, PIO_NOT_A_PIN must be entered in this field. See
WVariant.h for valid entries. These entries are also used as a parameter to
pinPeripheral() with the exception of PIO_NOT_A_PIN and PIO_MULTI. The pinMode function
now calls pinPeripheral() with the desired mode. Note that this field is not used to
select between the different peripherals possible with each of the SERCOM and TIMER
functions. PeripheralAttribute is now used for this. When PIN_DESCRIPTION_TABLE_SIMPLE
is defined, PinType is not used (the pin is treated as PIO_MULTI).

### PeripheralAttribute
This is an 8-bit bitfield used for various peripheral configuration. It is primarily
used to select between the different peripherals possible with each of the SERCOM and
TIMER functions. TIMER pins are individual, while SERCOM uses a group of two to four
pins. This group of pins can span both peripherals. For example, pin 19 (SPI1 SCK) on
the MT-D21E uses PER_ATTR_SERCOM_ALT while pin 22 (SPI1 MISO) uses PER_ATTR_SERCOM_STD.
Both TIMER and SERCOM can exist for each pin. This bitfield is also used to set the
pin drive strength and the input buffer configuration (ie: totem-pole, open-drain,
buskeeper, etc.). Starting with 1.6.8, the ADC instance on the D51 and C21 (there are
two) is also selected here. Note that the D51 adds a third timer attribute and
requires consultation of the datasheet IOSET tables. See WVariant.h for valid entries.

### PinAttribute
This is a 32-bit bitfield used to list all of the valid peripheral functions that a
pin can attach to. This includes GPIO functions like PIN_ATTR_OUTPUT. Certain
attributes are shorthand for a combination of other attributes. PIN_ATTR_DIGITAL
includes all of the GPIO functions, while PIN_ATTR_TIMER includes both
PIN_ATTR_TIMER_PWM and PIN_ATTR_TIMER_CAPTURE (capture is not used yet).
PIN_ATTR_ANALOG is an alias to PIN_ATTR_ANALOG_ADC. This bitfield is useful for
limiting a pin to only input related functions or output functions. This allows a pin
to have a more flexible configuration, while restricting the direction (ie: to avoid
contention). See WVariant.h for valid entries. Not used with PIN_DESCRIPTION_TABLE_SIMPLE.

### TCChannel
This is the TC/TCC channel (if any) assigned to the pin. Some TC channels are available
on multiple pins. In general, only one pin should be configured in the pinDescription
table per TC channel. Starting with 1.6.8, the timer type is now encoded in this column
to support the D51, L21 and C21, which use TC numbers starting at 0 (rather than 3 as on
the D21). See WVariant.h for valid entries.

### ADCChannelNumber
This is the ADC channel (if any) assigned to the pin. The D51 and C21 each have two ADC
instances, which are selected in the PeripheralAttribute column. See WVariant.h for
valid entries. Not used with PIN_DESCRIPTION_TABLE_SIMPLE.

### ExtInt
This is the interrupt (if any) assigned to the pin. Some interrupt numbers are
available on multiple pins. In general, only one pin should be configured in the
pinDescription table per interrupt number. Thus, for example, if an interrupt was
needed on pin 2, EXTERNAL_INT_2 can be moved from pin 18. See WVariant.h for valid
entries. Not used with PIN_DESCRIPTION_TABLE_SIMPLE.

### SetExtIntADC()
When PIN_DESCRIPTION_TABLE_SIMPLE is defined, ExtInt and ADCChannelNumber are combined
into one column using the SetExtIntADC() packing macro: SetExtIntADC(EXTERNAL_INT_4,
ADC_Channel2). If the pin is not usable, use SetExtIntADC(EXTERNAL_INT_NONE, No_ADC_Channel).

### GCLKCCL
This column was added in 1.6.8-beta-b0. It is not yet used. It will eventually support
the Analog Comparators (AC), the Configurable Custom Logic (CCL) peripherals of the D51,
L21 and C21, and the GCLK outputs (inputs) of all of the MCUs. Not used with
PIN_DESCRIPTION_TABLE_SIMPLE.
