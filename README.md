# Wifi_cloned
An implementation of NodeMCU's wifi hacking capabality.

This jammer is so tiny you can fit into pocket. and carry it anywhere. it can powered through your power bank or 3.7v lipo battery. You can select which wifi network you want to jamm and attck on it . But be sure this is just for education purpose do not use for wrong purposes.

The 802.11 WiFi protocol contains a so called deauthentication frame. It is used to disconnect clients safely from a wireless network.
Because these packets are unencrypted, you just need the mac address of the WiFi router and of the client device which you want to disconnect from the network. You don’t need to be in the network or know the password, it’s enough to be in its range.

You can perform multiple attacks on this device such as you can jam any particular wifi network or you can do beacon spam or random beacon spam. or you can simple deauth all. Lets start making it.

You can use this Mobile app to control this Wifi Jammer

http://geni.us/PQhB

## Get Your Equipments Ready
So to make this wifi jammer mainly you will need only one part esp8266.
![NodeMCU](https://github.com/Gaurav047/Wifi_cloned/blob/master/node.jpg)

you can buy this perticular version of esp8266 as this as a nodemcu firmware on it and it is easy to program without any programmer. This esp8266 has a build in programmer.
you can buy that here
1) ESP8266
http://geni.us/1LLaBJR
2) Battery (optional)
http://geni.us/okAOH

## Further Steps
Download the latest Arduino compiler from the Arduino website here
https://www.arduino.cc/en/Main/Software

1 Install Arduino and open it.
2 Go to File > Preferences
3 Add http://arduino.esp8266.com/stable/package_esp8266com_index.json

to the Additional Boards Manager URLs.

4 Go to Tools > Board > Boards Manager

5 Type in esp8266
6 Select version 2.0.0 and click on Install (must be version 2.0.0)
7 Go to File > Preferences

8 Open the folder path under More preferences can be edited directly in the file
don't forget to save!
9 Go to packages > esp8266 > hardware > esp8266 > 2.0.0 > tools > sdk > include
10 Open user_interface.h file with your favourite text editor or just wordpad.

11 Scroll down and before #endif add following lines: if you cant see correct copy it from the txt file included in the project files

    typedef void (**freedom_outside_cb__t)(uint8 status);
    int wifi_register_send_pkt_freedom_cb(freedom_outside_cb_t cb); void wifi_unregister_send_pkt_freedom__cb(void); int wifi_send_pkt_freedom(uint8 **buf, int len, bool sys_seq);


    don't forget to save!
    
 ## The Code 
   
 1 Download project files from here (Credit goes to the orginal creator spacehuhn)

    https://rebrand.ly/wifijammercode

2 Open Wifi Jammer > esp8266_deauther > esp8266_deauther.ino in Arduino

3 Select your ESP8266 board at Tools > Board. I used NodeMCU 0.9 but you can try NodeMCU 1.0 or Generic ESP8266 Module

4 Select your programmer at Tools > Programmer > ArduinoISP

5 Select the right port no at Tools > Port If no port shows up you may have to reinstall the drivers.

6 Upload!

### The Result

![Final Result](https://github.com/Gaurav047/Wifi_cloned/blob/master/final.jpg)

1 First power up your ESP8266
You can use your smartphone if you have a USB OTG cable. or micro usb cable with a power bank or usb wall adapter.

2 Now you can controll your jammer using any smartphone or PC just Connect to ESP8266 Module so
Scan for WiFi networks from your Mobile or PC or MAC and connect to AndroidAP . The password is killwifi . You can change this SSID and Password from the code you uploaded. Once connected, you can use this ANDROID app to control this Wifi Jammer https://rebrand.ly/wifijammer

OR you can open up your browser and go to 192.168.4.1

3 You can now scan for networks...
Note: While scanning the ESP8266 will shut down its access point, so you may have to go to your settings and reconnect to the WiFi network manually.

...and start different attacks.

4 Click on the attack tab
choose deauth all
boom everyone on the wifi should be disconnected now

you can try other attacks as well

