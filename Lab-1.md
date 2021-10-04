# Lab 1: MARIO GOLBANO CORZO

[My Digital Electronics 2 Github Repository](https://github.com/mariogolbi/Digital-electronics-2)

### Blink example

1. What is the meaning of the following binary operators in C?
   * `|` This means OR
   * `&` This means AND
   * `^` This means XOR
   * `~` This is the complement (negation, NOR)
   * `<<` This operatos shifts the (binary) number as places as it is indicated to the left, adding a 0 to the right end of the number
   * `>>` This operatos shifts the (binary) number as places as it is indicated to the right, adding a 0 to the left end of the number

2. Complete truth table with operators: `|`, `&`, `^`, `~`

| **b** | **a** |**b or a** | **b and a** | **b xor a** | **not b** |
| :-: | :-: | :-: | :-: | :-: | :-: |
| 0 | 0 | 0 | 0 | 0 | 1 |
| 0 | 1 | 1 | 0 | 1 | 1 |
| 1 | 0 | 1 | 0 | 1 | 0 |
| 1 | 1 | 1 | 1 | 0 | 0 |


### Morse code

1. Listing of C code with syntax highlighting which repeats one "dot" and one "comma" (BTW, in Morse code it is letter `A`) on a LED:

```c
#define LED_GREEN   PB5 // AVR pin where green LED is connected
#define DELAY_INTER_LETTER 1200 // Delay between each word
#define DELAY_INTER_SYMBOL 250  // Delay between each symbol (dots and commas)
#define SHORT_DELAY 350  // Delay of the "dot"
#define LONG_DELAY 700  // Delay of the "comma"
#ifndef F_CPU           // Preprocessor directive allows for conditional
                        // compilation. The #ifndef means "if not defined".
# define F_CPU 16000000 // CPU frequency in Hz required for delay
#endif   

#include <util/delay.h> // Functions for busy-wait delay loops
#include <avr/io.h>     // AVR device-specific IO definitions

int main(void)
{
    // Set pin as output in Data Direction Register
    // DDRB = DDRB or 0010 0000
    DDRB = DDRB | (1<<LED_GREEN);

    // Set pin LOW in Data Register (LED off)
    // PORTB = PORTB and 1101 1111
    PORTB = PORTB & ~(1<<LED_GREEN);

    // Infinite loop
    while (1)
    {
        // Pause several milliseconds
        _delay_ms(DELAY_INTER_LETTER);  // Time in between

        // Invert LED in Data Register
        // PORTB = PORTB xor 0010 0000
        PORTB = PORTB ^ (1<<LED_GREEN);  // LED on 
        _delay_ms(SHORT_DELAY);          // Time of "dot"

        PORTB = PORTB & ~(1<<LED_GREEN); // LED off
        _delay_ms(DELAY_INTER_SYMBOL);   // Time inter-symbol

        PORTB = PORTB ^ (1<<LED_GREEN);  // LED on
        _delay_ms(LONG_DELAY);           // Time of "comma"

        PORTB = PORTB & ~(1<<LED_GREEN); // LED off, the loop restarts
    }

    // Will never reach this
    return 0;
}
```


2. Scheme of Morse code application, i.e. connection of AVR device, LED, resistor, and supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values!

   ![your figure]()
