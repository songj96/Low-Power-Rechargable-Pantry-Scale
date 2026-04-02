# Low-Power-Rechargable-Pantry-Scale
The Amazon Dash Smart Shelf was a scale designed to reorder items when supplies were low. Like many of Amazons products, this item was sold at a loss in order to achieve many of Amazon's other goals like collecting user data or indirectly increasing sales on their website. 

I bought these scales (around $20) which contained high quality load cells wired in a Wheatstone Bridge (a kind of electrical circuit). I took out the electronics inside of the scale, and added my own. The parts list is as follows: 

- 1 22kohm resistor
- 1 47kohm resistor
- 1 ESP8266 Microcontroller
- 1 HX711 load cell amplifier
- 1 2-pin JST Female Connector
- 1 2-pin JST Male Connector
- 1 3000mAh Lipo battery
- 2 10uF capacitors
- 1 Adafruit Lipo Charger

![Scale Picture Guide](https://github.com/user-attachments/assets/3057e421-bb14-4c25-84d7-3a47ad015de1)

The battery leads should be connected to the lipo charger. The lipo charger's output should be wired to the microcontroller and HX711 board. ESPHome firmware can be flashed onto the board. Afterward, the .yaml file can be used to configure the board. It can then communicate over MQTT. 

The stocksensor/ota topic is used to command the board to remain awake for any reason (usually to perform a software update).

These scales were connected to HomeAssistant, but they can be used in other contexts.

These scales only have to run for a few seconds every hour. It is possible to configure the run duration and sleep duration within the .yaml files. With the current settings and a 3000mAh lipo battery, they run for around 10-14 days on a single charge.

Today, it is likely better to use low-power bluetooth, but at the time, this worked well enough.
