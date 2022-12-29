## LEDs
#Leds #Polar #Diode

A type of diode (polar, one way) which only works if the current is flowing in the correction direction where the positive (longer) pin is connective to the positive output and the negative output (shorter grounder) pin to the ground

| LED | Voltage | Max Current | Rec Current
| - | - | - | - |
| Red | 1.9-2.2V | 20mA | 10mA|
| Green | 2.9-3.4V | 10mA | 5mA|
|Blue | 2.9-3.4V | 10mA | 5mA|

![[LEDs.png]]

LED can be set 0 or 1 for low and high
PWMLEDG can be set between 0 to 1 for variable brightness

![[Basic LED Button Setup.png]]
```python
#Example 1
from gpiozero import LED
from time import sleep

red = LED(17)

while True:
	red.on()
	sleep(1)
	red.off()
	sleep


#Example 2
from gpiozero import LED
from signal import pause

red = LED(17)

red.blink() #Takes (onTime, offTime) parameters

pause()
```

![[Basic LED Button Setup 2.png]]
```python
from gpiozero import LED, Button
from signal import pause

led = LED917
button = Button(2)

#Method 1
led.source = button

#Method 2 
button.when_pressed = led.on
button.when_released = led.off




pause()
```