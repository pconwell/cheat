# Aruino & VS Code 

## Install Arduino IDE

1. https://www.arduino.cc/en/main/software#download
2. Download appropriate version
3. (Linux) Extract (probably to home folder...)
4. cd into extracted folder
5. `$ chmod +x ./install.sh`
6. `$ sudo ./install.sh`
7. `$ ./arduino-linux-setup.sh $USER`
8. `$ sudo shutdown now -r`

## Install Arduino Plugin for VS Code

1. Open VS Code
2. Quick Open (Ctrl + P)
3. `ext install vsciot-vscode.vscode-arduino`

## Select your board type

1. Command Palette (Ctrl + Shift + P)
2. `change board type`
3. select your board

## Copy/Paste testing code into VS Code

> probably want to set up a new folder/project to be 'clean' about it

```
/*
  Blink without Delay

  Turns on and off a light emitting diode (LED) connected to a digital pin,
  without using the delay() function. This means that other code can run at the
  same time without being interrupted by the LED code.

  The circuit:
  - Use the onboard LED.
  - Note: Most Arduinos have an on-board LED you can control. On the UNO, MEGA
    and ZERO it is attached to digital pin 13, on MKR1000 on pin 6. LED_BUILTIN
    is set to the correct LED pin independent of which board is used.
    If you want to know what pin the on-board LED is connected to on your
    Arduino model, check the Technical Specs of your board at:
    https://www.arduino.cc/en/Main/Products

  created 2005
  by David A. Mellis
  modified 8 Feb 2010
  by Paul Stoffregen
  modified 11 Nov 2013
  by Scott Fitzgerald
  modified 9 Jan 2017
  by Arturo Guadalupi

  This example code is in the public domain.

  http://www.arduino.cc/en/Tutorial/BlinkWithoutDelay
*/

// constants won't change. Used here to set a pin number:
const int ledPin =  LED_BUILTIN;// the number of the LED pin

// Variables will change:
int ledState = LOW;             // ledState used to set the LED

// Generally, you should use "unsigned long" for variables that hold time
// The value will quickly become too large for an int to store
unsigned long previousMillis = 0;        // will store last time LED was updated

// constants won't change:
const long interval = 1000;           // interval at which to blink (milliseconds)

void setup() {
  // set the digital pin as output:
  pinMode(ledPin, OUTPUT);
}

void loop() {
  // here is where you'd put code that needs to be running all the time.

  // check to see if it's time to blink the LED; that is, if the difference
  // between the current time and last time you blinked the LED is bigger than
  // the interval at which you want to blink the LED.
  unsigned long currentMillis = millis();

  if (currentMillis - previousMillis >= interval) {
    // save the last time you blinked the LED
    previousMillis = currentMillis;

    // if the LED is off turn it on and vice-versa:
    if (ledState == LOW) {
      ledState = HIGH;
    } else {
      ledState = LOW;
    }

    // set the LED with the ledState of the variable:
    digitalWrite(ledPin, ledState);
  }
}
```

## Select Serial Port (If Needed)

Attempt to upload the script by `ctrl+alt+u` or clicking the `upload` button

> This seems to be autodetected? In my particular case it was `/dev/ttyACM0` which was the top option AND appeared to have already detected the attached board


# bugs here???



## Install additional libaries if needed

> If you run in to an error such as `java.lang.UnsatisfiedLinkError: /.../.../java/lib/i386/libawt_xawt.so: libXext.so.6: cannot open shared object file`

1. `$ apt-file search libXext.so.6`
2. `$ sudo apt install `
