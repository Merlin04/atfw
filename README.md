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
