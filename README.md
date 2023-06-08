# IOT project
# Home Automation using Arduino Uno and Voice Assistant App

This project provides a step-by-step guide on how to create a home automation system using Arduino Uno, a Voice Assistant App, and an HC-05 Bluetooth module. The system allows you to control various appliances and devices in your home using voice commands via a mobile app.

## Components Required

- Arduino Uno

- HC-05 Bluetooth module

- Jumper wires

- LEDs (for demonstration)

- Resistors (for LEDs)

- Relay module (for controlling appliances)

- Breadboard (optional)

- Android or iOS device with Bluetooth capabilities

- Voice Assistant App (such as Google Assistant or Siri)

## Circuit Connections

1. Connect the VCC pin of the HC-05 module to the 5V pin of Arduino Uno.

2. Connect the GND pin of the HC-05 module to the GND pin of Arduino Uno.

3. Connect the TX pin of the HC-05 module to the RX pin (pin 0) of Arduino Uno.

4. Connect the RX pin of the HC-05 module to the TX pin (pin 1) of Arduino Uno.

## Arduino Code

Upload the following Arduino code to the Arduino Uno:

```cpp

#include <SoftwareSerial.h>

SoftwareSerial bluetooth(0, 1); // RX, TX pins for HC-05 module

void setup() {

  Serial.begin(9600);

  bluetooth.begin(9600);

}

void loop() {

  if (bluetooth.available()) {

    char command = bluetooth.read();

    executeCommand(command);

  }

}

void executeCommand(char command) {

  switch (command) {

    case '1':

      // Code to turn on an appliance or perform an action

      break;

    case '2':

      // Code to turn off an appliance or perform an action

      break;

    default:

      break;

  }

}

```

## Voice Assistant App Configuration

1. Install a Voice Assistant App on your Android or iOS device (e.g., Google Assistant or Siri).

2. Connect the HC-05 module to your mobile device via Bluetooth. Refer to the HC-05 module's documentation for instructions on pairing with your mobile device.

3. Open the Voice Assistant App and configure it to listen for your voice commands.

## Controlling Appliances

1. Connect the relay module to the Arduino Uno to control the appliances. Refer to the relay module's documentation for wiring instructions.

2. Modify the `executeCommand()` function in the Arduino code to control the relay module and, consequently, the connected appliances. You can use digital pins of the Arduino to control the relay module (e.g., `digitalWrite(relayPin, HIGH)` to turn on the relay, `digitalWrite(relayPin, LOW)` to turn it off).

## Usage

1. Ensure that the Arduino Uno is powered on and connected to the Voice Assistant App via the HC-05 Bluetooth module.

2. Use the Voice Assistant App to send voice commands to the Arduino Uno by speaking into your mobile device.

3. The Arduino code will receive the commands and execute the corresponding actions, such as turning on or off appliances connected to the relay module.

## Note

- This Readme provides a general overview of the project. Additional configuration and customization may be required based on your specific requirements.

- Ensure proper safety precautions when working with electrical appliances and connections.

- Refer to the documentation and examples provided by the Arduino Uno, HC-05 module, relay module, and Voice Assistant App for more detailed information.

Happy home automation!
