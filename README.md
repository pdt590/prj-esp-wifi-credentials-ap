# esp8266-wifi-credentials-webserver-eeproom

Esp8266 Wifi credentials provisioning using webserver

## References

- ESP8266WebServer-EEPROOM.ino
  - [ESP8266 Manual Wifi Configuration with EEPROM without Hard-Code](https://how2electronics.com/esp8266-manual-wifi-configuration-without-hard-code-with-eeprom)
  - [Arduino/libraries/DNSServer/examples/CaptivePortalAdvanced](https://github.com/esp8266/Arduino/tree/master/libraries/DNSServer/examples/CaptivePortalAdvanced)
  - [chriscook8/esp-arduino-apboot](https://github.com/chriscook8/esp-arduino-apboot)

- ESP8266WebServer-SPIFFS.ino
  - [ESP8266 Storing Wi-Fi Settings In Flash Auto-Switch AP](https://github.com/acrobotic/Ai_Tips_ESP8266/blob/master/wifi_modes_switch/wifi_modes_switch.ino)
    - https://youtu.be/lyoBWH92svk 

- WiFiManager.ino
  - [WiFiManager with ESP8266](https://randomnerdtutorials.com/wifimanager-with-esp8266-autoconnect-custom-parameter-and-manage-your-ssid-and-password/)
  - [tzapu/WiFiManager](https://github.com/tzapu/WiFiManager)
  - How WiFiManager Works
    - When your ESP starts up, it sets it up in Station mode and tries to connect to a previously saved Access Point
    - if this is unsuccessful (or no previous network saved) it moves the ESP into Access Point mode and spins up a DNS and WebServer (default ip 192.168.4.1)
    - using any wifi enabled device with a browser (computer, phone, tablet) connect to the newly created Access Point
    - because of the Captive Portal and the DNS server you will either get a 'Join to network' type of popup or get any domain you try to access redirected to the configuration portal
    - choose one of the access points scanned, enter password, click save
    - ESP will try to connect. If successful, it relinquishes control back to your app. If not, reconnect to AP and reconfigure.
    - There are options to change this behavior or manually start the configportal and webportal independantly as well as run them in non blocking mode.