# Embedded-Systems-internship-task-2
Embedded Systems Internship task 2 
// Define pin for controlling the relay

int relayPin = 7; // Relay connected to digital pin 7

// Variable to store incoming Bluetooth data

char bluetoothData;

void setup() {

 // Set the relay pin as output

 pinMode(relayPin, OUTPUT);

 // Turn relay OFF initially

 digitalWrite(relayPin, LOW);

 // Initialize serial communication (for Bluetooth)

 Serial.begin(9600);

}

void loop() {

 // Check if data is available to read from the Bluetooth module

 if (Serial.available()) {

 bluetoothData = Serial.read(); // Read the incoming data

 

 // Turn ON the bulb (activate relay) if data is '1'

 if (bluetoothData == '1') {

 digitalWrite(relayPin, HIGH); // Turn ON relay

 }

 // Turn OFF the bulb (deactivate relay) if data is '0'

 else if (bluetoothData == '0') {

 digitalWrite(relayPin, LOW); // Turn OFF relay
 }
 }
 }
