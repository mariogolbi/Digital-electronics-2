# Lab 5: MARIO GOLBANO CORZO

[Link to my `Digital-electronics-2` GitHub repository](https://github.com/mariogolbi/Digital-electronics-2)


### 7-segment library

1. In your words, describe the difference between Common Cathode and Common Anode 7-segment display.
   * CC SSD: In this kind of display all cathodes of the LEDS are connected together. They are all connected to ground, so that in order to illuminta a concrete segment, power must be applied only to that segment.
   * CA SSD: For this displays, all the anodes are together connected to the same point, but in this case, they are all connected to the power source. In order to illuminate one LED, the other end of the segment must be connected to ground.

2. Code listing with syntax highlighting of two interrupt service routines (`TIMER1_OVF_vect`, `TIMER0_OVF_vect`) from counter application with at least two digits, ie. values from 00 to 59:

```c
/**********************************************************************
 * Function: Timer/Counter1 overflow interrupt
 * Purpose:  Increment counter value from 00 to 59.
 **********************************************************************/
ISR(TIMER1_OVF_vect)
{
    // WRITE YOUR CODE HERE

}
```

```c
/* Interrupt service routines ----------------------------------------*/
/**********************************************************************
 * Function: Timer/Counter1 overflow interrupt
 * Purpose:  Increment decimal counter value and display it on SSD.
 **********************************************************************/
ISR(TIMER1_OVF_vect)
{
    // WRITE YOUR CODE HERE
    static uint8_t val0 = 0;  // This line will only run the first time
    static uint8_t val1 = 0;
	
    val0++;
    if (val0 > 9){
        val0 = 0;
		val1++;
		
		if(val1>5){
			val1=0;
		}
	}
}

ISR(TIMER0_OVF_vect)
{
	static uint8_t pos = 0;
	
	pos++;
	if (pos>1){
		pos=0;
		SEG_update_shift_regs(val0,pos);
	}
	else{
		SEG_update_shift_regs(val1,pos);
	}
}
```

3. Flowchart figure for function `SEG_clk_2us()` which generates one clock period on `SEG_CLK` pin with a duration of 2&nbsp;us. The image can be drawn on a computer or by hand. Use clear descriptions of the individual steps of the algorithms.

   ![Flowchart lab5](https://github.com/mariogolbi/Digital-electronics-2/blob/main/Labs/images/Flowchart_lab5.png)


### Kitchen alarm

Consider a kitchen alarm with a 7-segment display, one LED and three push buttons: start, +1 minute, -1 minute. Use the +1/-1 minute buttons to increment/decrement the timer value. After pressing the Start button, the countdown starts. The countdown value is shown on the display in the form of mm.ss (minutes.seconds). At the end of the countdown, the LED will start blinking.

1. Scheme of kitchen alarm; do not forget the supply voltage. The image can be drawn on a computer or by hand. Always name all components and their values.

   ![kitchen timer](https://github.com/mariogolbi/Digital-electronics-2/blob/main/Labs/images/kitchen_timer.png)
