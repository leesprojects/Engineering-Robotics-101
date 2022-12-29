#GPIO-Mapping

General Purpose Input-Output Board
![[GPIO Numbering Relationship.png]]

The GPIO (logic) pins allow input and output 3.3V levels

#GPIO-Electrical-Mapping
![[GPIO Electrical Mapping.png]]

[GPIOZero](https://gpiozero.readthedocs.io/en/stable/) Library for Python

```python
from gpiozero import LED, Button, MotionSensor, LightSensor, OutputDevice
from signal import pause
from time import sleep
```

![[Pasted image 20221228172159.png]]
E.g. 
```python
#All these LED references are to GPIO17
>>> led = LED(17) #GPIO BroadCom (BCM) layout (USE THIS MAPPING)
>>> led = LED("GPIO17") #Exact board name
>>> led = LED("BCM17")
>>> led = LED("BOARD11") #11th slot on the physical mapping
>>> led = LED("WPI0") #WingPi Reference
>>> led = LED("J8:11") #Exact position on the breadboard
```


## LEDs
```python
from gpiozero import LED
from time import sleep

red = LED(17) 

while True:
    red.on()
    sleep(1)
    red.off()
    sleep(1)
```

```python
from gpiozero import PWMLED
from time import sleep

led = PWMLED(17)

while True:
    led.value = 0  # off
    sleep(1)
    led.value = 0.5  # half brightness
    sleep(1)
    led.value = 1  # full brightness
    sleep(1)
```