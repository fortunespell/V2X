# V2X (Currently working)

ESP-NOW is a wireless communication protocol developed by Espressif, the company behind the ESP32 microcontroller (MCU). Since the Arduino Nano ESP32 is equipped with that MCU it also supports the ESP-NOW protocol out of the box. It's designed for efficient and low-latency communication between devices, capable of sending up to 250 bytes.

ESP-NOW operates as a peer-to-peer (P2P) protocol, meaning it allows direct communication between two ESP8266 or ESP32 devices without the need for a central server or access point, e.g. a Wi-Fi® router. Each ESP device has a unique MAC address which is used to identify the receiving board.

ESP-NOW can be set up in different ways:

One-way communication: In one-way communication mode, one device (the sender) can send data to another device (the receiver) without expecting a response. This mode is often used for scenarios where one device provides data or commands to another device, such as remote sensor readings or control commands.

Two-way communication: In two-way communication mode, both devices can exchange data bidirectionally. This mode enables a back-and-forth exchange of information between the devices, allowing for more interactive and responsive communication. It's suitable for applications where devices need to send and receive data from each other, such as remote control systems or interactive IoT devices.

![image](https://github.com/user-attachments/assets/773015de-1b71-4acc-bfcc-d152372d24c4)

### Protocol Stack
ESP-NOW operates primarily at the data-link layer of the OSI model. In contrast to traditional networking protocols that involve multiple layers, ESP-NOW condenses the communication stack, streamlining the process. By reducing the protocol stack to a single layer, ESP-NOW eliminates the need for complex packet headers and unpackers on each layer. This simplicity results in quicker response times, reducing delays caused by packet loss in congested networks.


![image](https://github.com/user-attachments/assets/993b9bf7-5b77-4c0c-b7f0-5ff5bd3fef25)


## The IDEA 💡 

1. Creating some sort of awareness systems aroud a vehicle.
2. The nomenclature for V2V, V2I and V2H goes as :-

    * ESP A ---> Vehicle 1 (V1) 🚗
    * OBJECT ---> Vehicle 2 (V2) 🚌 
    * ESP B ---> Infrastructure 🚦 
    * ESP C ---> Household 🏡 

3. V2V => V1 has range detection via ultrasonic sensor which is used to detect if another vehicle or and object is very near to the V1 . On to the next thing, implementation of hard braking using a pressure sensor which will indicate the any hard braking which is most likely a case in accidents . Implementation of GPS sensor for live location of the vehicle. An Ai assistant can also be integrated for guidance of driver .

## Master edits (In Improvement phase)
1. LED Initialization: The LED_PIN is defined, and the pin mode is set to OUTPUT in the setup() function.
2. LED Blinking in onReceive Function: In the onReceive function of the ESP_NOW_Peer_Class, the LED is turned on, delayed for 500 milliseconds, and then turned off whenever a message is received.
3. Callback Registration: The register_new_master function registers new peers and sets the callback for receiving messages, where the LED blink will be triggered.


## Slave edits (In Improvement phase)

1. Modify the master code to read ultrasonic sensor values and send them via ESP-NOW.
2. Update the slave code to receive these values and trigger the buzzer accordingly.


## Connections 

### Master ESP32 Connections

1. Ultrasonic Sensor ---->	ESP32
2. VCC ---->	5V
3. GND ---->	GND
4. TRIG ---->	GPIO 5
5. ECHO ---->	GPIO 18


### Slave ESP32 Connections
1. Buzzer ---->	ESP32
2. VCC ---->	5V
3. GND ---->	GND
4. SIG ---->	GPIO 2




![image](https://github.com/user-attachments/assets/45f74089-218b-4a21-9764-7f41933ca114)
