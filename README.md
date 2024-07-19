# V2X


![image](https://github.com/user-attachments/assets/993b9bf7-5b77-4c0c-b7f0-5ff5bd3fef25)
![image](https://github.com/user-attachments/assets/773015de-1b71-4acc-bfcc-d152372d24c4)
## master edits
1. LED Initialization: The LED_PIN is defined, and the pin mode is set to OUTPUT in the setup() function.
2. LED Blinking in onReceive Function: In the onReceive function of the ESP_NOW_Peer_Class, the LED is turned on, delayed for 500 milliseconds, and then turned off whenever a message is received.
3. Callback Registration: The register_new_master function registers new peers and sets the callback for receiving messages, where the LED blink will be triggered.


## slave edits
1. Modify the master code to read ultrasonic sensor values and send them via ESP-NOW.
2. Update the slave code to receive these values and trigger the buzzer accordingly.



