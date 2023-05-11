# ESPHome-Three-speed-fan
ESPHome three speed fan adaptation

These are the files needed for my ESPHome three speed fan project.
The project was to take a three speed pedestal fan and adapt it to be ´smart´ with control via Home Assistant.
The fan is a typical pedestal fan with the three speeds being set by where the power is applied on the coil.

For more details of how to wire things up etc, see the project on Instructables, here:
https://www.instructables.com/ESPHome-Three-Speed-Smart-Pedestal-Fan/

The GPIOs on the ESP8266 should be wired thus:
- GPIO1 should be connected to the manual button (the other side of the button to GND)
- GPIO5 should be connected to the low speed relay (whichever relay is connected to the low speed fan wire)
- GPIO4 should be connected to the medium speed relay (whichever relay is connected to the middle speed fan wire)
- GPIO14 should be connected to the high speed relay (whichever relay you connect to the highest speed fan wire)
- 5VDC/VCC and GND on the ESP8266 should also be connected to the relay control board to power it.

The three relays should all have the mains neutral wire on the COM and each of the fan speed wires on their respective NC terminals.

The mains live wire should also still go to the direct wire (the one that didn´t go through the original switching gear) of the fan along with the power converter board.

The YAML file here can be uploaded directly to the ESP8266 via ESPHome/Home Assistant, just change the WIFI details and names to suit.  This will create a fan device in HA that can then be controlled via the relevant cards or automations using speeds and off.
