## HALL Preamp/Analog axis calibrator

##### Opamp based preamp for analog inputs in joystick applications
---
This little project was designed to overcome many range issues when using traditional 300 degree potentiometers or Hall sensors as rotational angle to voltage converters. The idea was to create a device that will perform an axis calibration, usually done in digital domain, but before sampling the signal in the ADC, still in analog domain, using it's advantageous infinite resolution. In addition some further signal conditioning is also performed.

##### Features:

the main function of this device is to:
- Buffer the analog output signal coming from a potentiometer or another rotary angle to voltage converter like ie. Hall sensors.
- Filter out the high band noise and limit the bandwidth to an usable range only, protect the input against voltage spikes.
- Match the output voltage range of the source (pot/hall sensor) with the input range of the ADC, thus making the most of the available ADC resolution.
- Linearize the hall sensor output signal response by amplyfing it's most linear region to the full scale ADC input range.
---
##### Operation:

The board allows to adjust the gain of the **positive** and **negative** part of the control signal **individually** using the trimpots. The offset (zero) is adjusted using the 3rd available trimpot.

![alt text][pic1]

##### Calibration process:

An an example let's calibrate the X axis of a flight stick, assuming the analog inputs have a range of 0-5V DC and a pot or a hall sensor is used as the singal source.
Connect the joystick to the PC and use your favorite test software (ie. VKB joy tester, DIview) to observe the axis value.


1. Make sure the pot or the Hall sensor is installed in a way that the output is close to the middle value (2.5V) when the stick is in zero position. This can be done by adjusting the sensor's body position.
2. Using the **ZERO** trimpot precisely adjust the zero value.
3. The next step will be to adjust the gains for positive and negative halves of the signal range to match the full swing of the ADC input. Depending on the potentiometer connections or the magnet polarity it might happen the positive and the negative gain controlls will be swapped, ie. the max value will be set with the Negative gain trimpot and the min value with the Positive Gain one.   
4. Move the stick to the **maximum** position. Check which **Gain** trimpot controls the output value. Adjust the Gain until the signal comes as close to the maximum value as possible.
5. Move the stick to the **minimum** value and using the other Gain trimpot adjust the output signal to be close to zero.
6. Release the stick, the output signal should come back to zero. Recheck max and min positions. Repeat the above steps if any further adjustment is required.

---
##### Side note:

Although the opamps used in the circuit are a rail-to-rail ones, due to their internal construction, there will be still a few mV to few tens of mV difference between the output voltage range and the power rails (0-5V). The difference is relatively small and can be easily calibrated out on the PC side.

---
Boards can be ordered directly from OSH Park:

<a href="https://www.oshpark.com/shared_projects/9rI7Z7aX"><img src="https://www.oshpark.com/assets/badge-5b7ec47045b78aef6eb9d83b3bac6b1920de805e9a0c227658eac6e19a045b9c.png" alt="Order from OSH Park"></img></a>

![alt text][pic2]

![alt text][pic3]

![alt text][pic4]

![alt text][pic5]
------
(c) 01.2017 by Piotr Zapart
www.hexeguitar.com

License:
Creative Commons - Attribution - ShareAlike 3.0
[http://creativecommons.org/licenses/by-sa/3.0/](http://creativecommons.org/licenses/by-sa/3.0/)

[pic1]: pics/HappPre_operation.png "HALLPre operation"
[pic2]: pics/hpre1.jpg "HallPreamp"
[pic3]: pics/hpre2.jpg "HallPreamp"
[pic4]: pics/hpre3.jpg "HallPreamp"
[pic5]: pics/hpre4.jpg "HallPreamp"
