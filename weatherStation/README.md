# SOLAR TRACKING WEATHER STATION

### Team members

* Member 1: Arjanit Ismajli
* Member 2: Francisco Abelardo García Avilés
* Member 3: Gonzalo Docal Saiz
* Member 4: Mario Golbano Corzo

[Link to this file in your GitHub repository](https://github.com/mariogolbi/Digital-electronics-2/tree/main/weatherStation)

### Table of contents

* [Project objectives](#objectives)
* [Hardware description](#hardware)
* [Libraries description](#libs)
* [Video/Animation](#circ)
* [Flowchart](#flowchart)
* [Main application](#main)
* [Video](#video)
* [References](#references)

<a name="objectives"></a>

## Project objectives
The aim of this project is to design a solar-tracking weather station. This way, the temperature, humidity and light intensity will be measured and shown in the display device. Also the weather station has 2 motors (axis X and Y) in order to move the station according to the light. This way the station can move in order to get as much light as possible. This can be very useful for solar panels, looking for the maximum light intensity. For this last purpose, our cade is very easy to change according to he light needs of the implementing system. 

![Circuit in the Lab](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/images/arduino.jpeg)

<a name="hardware"></a>

## Hardware description
We used the following components:
1. Arduino Uno + breadboard: 8-bit microcrontroller based on AVR.
2. Sensors:
 * DHT12 humidity and temperature sensor
 * Light intensity sensor: As we did not have one in the Lab, we designed a voltage divisor with a _photoresistor_ with another _resistor of 1 KOhm_, so that the voltage at the output would change according to the light intensity.
3. Others:
 * [LCD keypad shield](#objectives)
 * 2 x [SG-90 micro servo](#objectives): It can only turn 90° in either direction for a total of 180° movement, depending on the signal that reaches it.



<a name="libs"></a>
## Libraries description
These are the different libraries we used, all of them from the Course Labs:
* [uart.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/uart.h)
* [twi.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/twi.h)
* [timer.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/timer.h)
* [lcd_definitons.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/lcd_definitions.h)
* [lcd.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/lcd.h)
* [gpio.h](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/weatherStation/weatherStation/gpio.h)

<a name="circ"></a>
 ## Video/Animation
Here we can see the animation of the project. It shows how the project should work, moving the axis motors accoirding to he light intensity, as we can see through the LCD. This LCD also shows the temperature and humidity.

![Animated simulation](https://github.com/mariogolbi/Digital-electronics-2/blob/main/weatherStation/images/animation.gif)

We see how the X axis is turned to the left for values of light intensity less than 300, oriented straigth forward for values from 300 to 600 and turned to the left for a light intensity higher than 600. As for the Y axis, it just does 2 movements: up (when light intensity is less than 500) and down (when this value is higher than 500). The second motos (Y-axis) is should be positioned vertically, not as it is shown in the animation.
 
[Here](https://github.com/mariogolbi/Digital-electronics-2/tree/main/weatherStation/weatherStation_simu) is the link to the folder with the simulation diagram document (in Simulide), as well as all the files of the code and the simulation file (.HEX)

<a name="flowchart"></a>

 ## Flowchart
 Flowchart of main function:
 
 ![Flowchart Main](https://user-images.githubusercontent.com/91128841/145999916-b52b00a9-62be-406b-8112-80eaec97f4b3.jpeg)

Flowchart of ISR-Timer/Counter1

 ![ISR(TIMER1_OVF_vect)](https://user-images.githubusercontent.com/91128841/145999831-e19390e6-b583-47c8-913d-96369482885e.jpeg)
 
 Flowchart of ISR-ADconverter
 ![ISR (ADC_vect)](https://user-images.githubusercontent.com/91128841/145999863-2d8f4215-1411-48d1-a17e-2fc0a0b1bd03.jpeg)
 

<a name="main"></a>
## Main application
Here is the link to the main.c document we used fot the project.
[main.c](https://github.com/Arjanit21/Digital-electronics-2/blob/main/Project/weatherStation/weatherStation/weatherStation/main.c)

<a name="video"></a>

## Video
Here is a little video-explication of how the actual circuit worked in the Lab with our code:
[Video-explication](https://www.youtube.com/watch?v=dNLS92pq2vg&ab_channel=arjanitismajli)


<a name="references"></a>

## References
* [sg90_datasheet.pdf](http://www.ee.ic.ac.uk/pcheung/teaching/DE1_EE/stores/sg90_datasheet.pdf)
* [ATmega328P_Datasheet.pdf](https://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-7810-Automotive-Microcontrollers-ATmega328P_Datasheet.pdf)
* [LCD_KeyPad_Shield_For_Arduino](https://wiki.dfrobot.com/LCD_KeyPad_Shield_For_Arduino_SKU__DFR0009)
* [Libraries](https://github.com/tomas-fryza/Digital-electronics-2/tree/master/Labs)
* [Photoresistor](https://create.arduino.cc/projecthub/MisterBotBreak/how-to-use-a-photoresistor-46c5eb)
* [Variable Pulse width control servo position](https://www.jameco.com/Jameco/workshop/Howitworks/how-servo-motors-work.html)

