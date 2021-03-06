# heater-controller
A project to controll a domestic heating system with central heating and DHW


The heating system at home was initially controlled with simple relays that where commanded by thermostats. This had the problem that the integrated circulating pump would be on even the thermostats where off and so the actuators (that cut the flow of water to the circuit) where off. This is a picture of the heating room before:


<p align="center">
  <img width="460" src="/images/image1.jpg">
</p>





The controller is mounted on a DIN box and integrated in the electric panel.

The controller has:
* 6 optoisolated  digital outputs for connecting external relays
* 6 pull-down inputs
* I2C interface
* DS3231 RTC
* Atmega 2560 MCU

The result is this PCB:


<p align="center">
  <img width="300" src="/images/image2.png">
</p>
<p align="center">
  <img width="300" src="/images/image3.png">
</p>

The analog temperature indicators were replaced by 1-wire sensors. To acomodate these sensors on the existing housing a 3D piece was needed to avoid the sensor being loose. This is a preview of the model:

<p align="center">
  <img width="460" src="/images/image4.png">
</p>
And this is the result when mounted with the sensor:
<p align="center">
  <img width="460" src="/images/image8.jpg">
</p>

Finally, this is the photo of the finished model. Apart from the main PCB an auxiliary board has been created to acomodate the screen, the buttons and the programming interface (via FTDI connector). Through the screen you can control the status of the DHW supply (temperature and programmed state). It also gives information on the temperature of the DHW tank and the water temperature of the primary circuit (these are the sensors that are mounted with the 3D piece).
<p align="center">
  <img width="460" src="/images/image6.jpg">
</p>
<p align="center">
  <img width="460" src="/images/image5.jpg">
</p>


The controller recieves the inputs from the thermostat on the dinning room (it's a normally open contact), the DHW tank temperature and the fireplace located on the dinning room (this is precisely the purpose of the green pump: To circulate the water from the fireplace into the main system) and the actuates on the ouputs which are connected to DIN relays. This gives the safest scenario since only the relays controll AC mains, the whole PCB works with low voltage DC (between 5V and 12V).

Here is a photo of the screen's controller:
<p align="center">
  <img width="460" src="/images/image7.jpg">
</p>



The programming was made using the Arduino IDE (See code folder)
The 3d model of the wire holder and the screen cover were made using Fusion360
The schematic and PCB files were made using EasyEDA software: https://easyeda.com/603mbastida/caleino-v4

