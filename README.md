# atfw - Keyboard firmware for the ATtiny85
atfw is ATtiny85 keyboard firmware. It allows you to input a dictionary assigning pins to keycodes, and will generate and upload code to the development board. atfw is tested to work with a Digispark board, but it will probably work with all ATtiny85/Micronucleus-based boards. 

## Usage

atfw uses a dictionary to input pin/keycode combinations. Here's an example that would make connecting pin 0 and GND press the letter A:

`"{'0': 'KEY_A'}"`

You can also have multiple pin/keycode combinations:

`"{'0': 'KEY_A', '1': 'KEY_B'}"`

You could then pass that to atfw:

`atfw "{'0': 'KEY_A', '1': 'KEY_B'}"`

atfw will prompt you to plug in your Digispark, and will automatically upload the generated firmware. 

# Keycodes

To make your life easier, you can refer to the keycodes by a simple name, but you can also use the number associated with the keycode.

```
MOD_CONTROL_LEFT    (1<<0)
MOD_SHIFT_LEFT      (1<<1)
MOD_ALT_LEFT        (1<<2)
MOD_GUI_LEFT        (1<<3)
MOD_CONTROL_RIGHT   (1<<4)
MOD_SHIFT_RIGHT     (1<<5)
MOD_ALT_RIGHT       (1<<6)
MOD_GUI_RIGHT       (1<<7)

KEY_A       4
KEY_B       5
KEY_C       6
KEY_D       7
KEY_E       8
KEY_F       9
KEY_G       10
KEY_H       11
KEY_I       12
KEY_J       13
KEY_K       14
KEY_L       15
KEY_M       16
KEY_N       17
KEY_O       18
KEY_P       19
KEY_Q       20
KEY_R       21
KEY_S       22
KEY_T       23
KEY_U       24
KEY_V       25
KEY_W       26
KEY_X       27
KEY_Y       28
KEY_Z       29
KEY_1       30
KEY_2       31
KEY_3       32
KEY_4       33
KEY_5       34
KEY_6       35
KEY_7       36
KEY_8       37
KEY_9       38
KEY_0       39

KEY_ENTER   40

KEY_SPACE   44

KEY_F1      58
KEY_F2      59
KEY_F3      60
KEY_F4      61
KEY_F5      62
KEY_F6      63
KEY_F7      64
KEY_F8      65
KEY_F9      66
KEY_F10     67
KEY_F11     68
KEY_F12     69

KEY_ARROW_LEFT 0x50
```

I've edited the library to add more keycodes, which are originally from the Adafruit Trinket Keyboard library:

```
KEYCODE_MOD_LEFT_CONTROL	0x01
KEYCODE_MOD_LEFT_SHIFT		0x02
KEYCODE_MOD_LEFT_ALT		0x04
KEYCODE_MOD_LEFT_GUI		0x08
KEYCODE_MOD_RIGHT_CONTROL	0x10
KEYCODE_MOD_RIGHT_SHIFT		0x20
KEYCODE_MOD_RIGHT_ALT		0x40
KEYCODE_MOD_RIGHT_GUI		0x80

KEYCODE_LEFT_CONTROL	0xE0
KEYCODE_LEFT_SHIFT		0xE1
KEYCODE_LEFT_ALT		0xE2
KEYCODE_LEFT_GUI		0xE3
KEYCODE_RIGHT_CONTROL	0xE4
KEYCODE_RIGHT_SHIFT		0xE5
KEYCODE_RIGHT_ALT		0xE6
KEYCODE_RIGHT_GUI		0xE7
KEYCODE_1				0x1E
KEYCODE_2				0x1F
KEYCODE_3				0x20
KEYCODE_4				0x21
KEYCODE_5				0x22
KEYCODE_6				0x23
KEYCODE_7				0x24
KEYCODE_8				0x25
KEYCODE_9				0x26
KEYCODE_0				0x27
KEYCODE_A				0x04
KEYCODE_B				0x05
KEYCODE_C				0x06
KEYCODE_D				0x07
KEYCODE_E				0x08
KEYCODE_F				0x09
KEYCODE_G				0x0A
KEYCODE_H				0x0B
KEYCODE_I				0x0C
KEYCODE_J				0x0D
KEYCODE_K				0x0E
KEYCODE_L				0x0F
KEYCODE_M				0x10
KEYCODE_N				0x11
KEYCODE_O				0x12
KEYCODE_P				0x13
KEYCODE_Q				0x14
KEYCODE_R				0x15
KEYCODE_S				0x16
KEYCODE_T				0x17
KEYCODE_U				0x18
KEYCODE_V				0x19
KEYCODE_W				0x1A
KEYCODE_X				0x1B
KEYCODE_Y				0x1C
KEYCODE_Z				0x1D
KEYCODE_COMMA			0x36
KEYCODE_PERIOD			0x37
KEYCODE_MINUS			0x2D
KEYCODE_EQUAL			0x2E
KEYCODE_BACKSLASH		0x31
KEYCODE_SQBRAK_LEFT		0x2F
KEYCODE_SQBRAK_RIGHT	0x30
KEYCODE_SLASH			0x38
KEYCODE_F1				0x3A
KEYCODE_F2				0x3B
KEYCODE_F3				0x3C
KEYCODE_F4				0x3D
KEYCODE_F5				0x3E
KEYCODE_F6				0x3F
KEYCODE_F7				0x40
KEYCODE_F8				0x41
KEYCODE_F9				0x42
KEYCODE_F10				0x43
KEYCODE_F11				0x44
KEYCODE_F12				0x45
KEYCODE_APP				0x65
KEYCODE_ENTER			0x28
KEYCODE_BACKSPACE		0x2A
KEYCODE_ESC				0x29
KEYCODE_TAB				0x2B
KEYCODE_SPACE			0x2C
KEYCODE_INSERT			0x49
KEYCODE_HOME			0x4A
KEYCODE_PAGE_UP			0x4B
KEYCODE_DELETE			0x4C
KEYCODE_END				0x4D
KEYCODE_PAGE_DOWN		0x4E
KEYCODE_PRINTSCREEN		0x46
KEYCODE_ARROW_RIGHT		0x4F
KEYCODE_ARROW_LEFT		0x50
KEYCODE_ARROW_DOWN		0x51
KEYCODE_ARROW_UP	    0x52
```

See usb.org's HID-usage-tables document, chapter 10 Keyboard/Keypad Page for more codes.

# Credits

atfw has several components from open source/free software projects:

 - github.com/arduino/arduino-builder (licensed under the GNU GPL v2, has not been modified)
 - Certain files from github.com/arduino/Arduino, and the projects it is based upon (licensed under the GNU GPL v2 and GNU LGPL v2)
 - Certain files from github.com/digistump/DigistumpArduino

In addition, I added some keycodes from github.com/adafruit/Adafruit-Trinket-USB (licensed under GNU LGPL v2). 
