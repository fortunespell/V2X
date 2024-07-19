# V2X
## master edits
LED Initialization: The LED_PIN is defined, and the pin mode is set to OUTPUT in the setup() function.
LED Blinking in onReceive Function: In the onReceive function of the ESP_NOW_Peer_Class, the LED is turned on, delayed for 500 milliseconds, and then turned off whenever a message is received.
Callback Registration: The register_new_master function registers new peers and sets the callback for receiving messages, where the LED blink will be triggered.
## slave edits
Modify the master code to read ultrasonic sensor values and send them via ESP-NOW.
Update the slave code to receive these values and trigger the buzzer accordingly.
