---
title: eru-day2
---

[BACK TO MAIN PAGE](index.md)

# ERU - Day 2 Worksheet

## Part 1: Intermediate circuits (90 mins)
## Exercise 9: Using a potentiometer
In this example, you'll use a potentiometer (dial) to control the brightness of your LED. 

#### Your tasks:
- Open the AnalogInOutSerial sketch from the Arduino IDE at >File>Examples>03.Analog> and click on **AnalogInOutSerial**
- Navigate to the Arduino [AnalogInOutSerial tutorial page](https://www.arduino.cc/en/Tutorial/AnalogInOutSerial) to find the hardware requirements and circuit diagram. **Note** that you'll need to connect your circuit using the solderless breadboard.
- Once you've connected your circuit and successfully uploaded your code, open up the serial monitor on the top-right of the IDE. 
- Adjust (turn) the potentiometer and observe the changes to the LED, as well as the output in the Serial Monitor.

#### Notes
1. In this example, the LED is connected to digital pin 9, which is one of six **pulse width modulation (PWM)** digital pins on the Arduino (denoted with a **"~"** symbol on the board). PWM allows a digital output (which is either LOW = OFF or HIGH = ON) to simulate an analog signal (which can assume any value between LOW and HIGH). The command ```analogWrite``` is used instead of *digitalWrite* in this case, since we're writing an analog value to pin 9.
![Analog vs. Digital Signals](images/analog-digital.png "Analog vs. Digital Signals")
2. The map function is very useful for scaling the range of one variable to another range. In this example, the analog signal (from the potentiometer) ranges between 0 and 1023, while the acceptable output range for the LED is 0 to 255. The map function proportionally scales the potentiometer value to a usable value for the LED. 
3. In this example, you've used the Serial Console to establish and carry out serial communication between the Arduino and the computer. The setup function line ```Serial.begin(9600);``` establishes the connection, and the input argument (9600) in this case, determines the rate of information transfer, also known as the *baud* rate (9600 kilobits per second in this case). Clicking the drop-down on the bottom-right of the Serial Console displays the different baud rates that can be used. Note that the baud rate stated in the code needs to match that set in the Serial Console to receive intelligible output.
4. In some cases (or at least on my Windows 10 laptop), the Serial Console won't appear on the screen when you click it. If this happens, you should be able to fix it by maximizing it in the explorer bar.
![Maximizing the serial console](images/fix-serial-monitor.png "Maximizing the serial console")


## Exercise 10: Potentiometer out, photoresistor in
In this example, we’re going to start with the code and wiring used in the previous example, but replace the potentiometer with a photoresistor. The point of this is to demonstrate how both components can be used as control devices by providing variable resistances. This exercise will require you to merge the existing wiring and code from the [AnalogInOutSerial](https://www.arduino.cc/en/Tutorial/AnalogInOutSerial) example, and merge in elements of the [AnalogInput](https://www.arduino.cc/en/Tutorial/AnalogInput) example (namely, the photoresistor example). 

#### Your tasks:
- Use >File>Save As... to save a copy of the AnalogInOutSerial code to a new sketch file in your local working directory. Name the sketch with something descriptive. Use this code as the basis for this example. Upload it to the Arduino.
- Remove the wiring for the potentiometer, and replace it with the wiring shown for the photoresistor on the [AnalogInput](https://www.arduino.cc/en/Tutorial/AnalogInput) information webpage. 
- Once you have wired it properly (using the Serial Monitor to confirm), experiment with changing light levels on the photoresistor (using a bright light / covering it with your finger, etc.). Observe the results in the Serial Console (i.e. the range of input values from the photoresistor and the corresponding output values for the LED). Do the values span close to the entire ranges for these devices (0 to 1023 for the photoresistor and 0 to 255 for the LED)? 
  - If not, modify the **map** function in your code so that the LED brightness ranges from off to full brightness. 

#### Notes
1. Be sure to save your changes and re-upload the program as you make changes!
2. Notice in this example that the **5V** and **GND** pins of the Arduino are connected to the outside 'rails' of the breadboard, and that these rails are used to connect to the device. Given that the rails are connected down an entire column, this approach can be helpful when you need to connect more devices to **5V** and **GND** pins than are available.
 
![AnalogInput Circuit Diagram](images/analog-input.png "AnalogInput Circuit Diagram")

## Exercise 11: Connecting an RGB LED
Here, you'll be connecting an RGB LED to the Arduino, using a guide that has been provided by Adafruit--a company that provides a wide range of DIY electronics and tutorials. 

#### Notes:
- An RGB LED contains three LEDs (red, green, and blue) integrated into a single casing. By controlling the brightness of each colour (using PWM), it's possible to create a wide variety of colours. Three of the LED legs correspond to one of these LEDs; depending on which time of RGB LED is being used (common anode vs common cathode), the fourth leg connects to either HIGH (5V) or LOW (GND):
  - For common anode RGB LEDs, the longest leg connects to HIGH (5V), and each of the shorter legs act as cathodes. 
  - For common cathode RGB LEDs, the longest leg connects to LOW (GND), and each of the shorter legs act as anodes.  

#### Your tasks:
**PLEASE ASSUME YOU ARE USING A COMMON ANODE RGB LED AND FOLLOW INSTRUCTIONS ACCORDINGLY**
- Create a new sketch. Delete all of the code so that you have a blank sketch
- Follow along with the instructions provided on the [Adafruit Learn webpage](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds/breadboard-layout) to connect the RGB LED to the Arduino via the breadboard.   
- Use the *Copy Code* button to copy the code provided on the [Arduino Sketch page](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds/arduino-sketch) to the clipboard and paste it into your sketch. Straight copying and pasting from the webpage may cause some stray html characters to end up in your sketch and cause it to fail when compiling. Save the sketch with an appropriate filename.
  - Read through the code and try to understand how it works.
- As per the instructions, be sure to connect the longest leg to 5V power, and uncomment the line ```\\#define COMMON_ANODE``` by removing the ``\\`` characters to leave ```#define COMMON_ANODE```.
- Once the circuit has been wired properly, the code has been uploaded and the RGB LED is working, review the order of colours with what is detailed in the sketch. 

#### If the order of colours does not match what is expected
- Double-check your wiring. Make sure that the proper LED pins are connected to the proper Arduino pins.
- Ensure that you've uncommented the ```#define COMMON_ANODE``` line and uploaded the most recent version to the Arduino
- If these steps don't address the issue, investigate if you have a common cathode RGB LED by: 
  - Wiring the longest leg to **GND** instead of **5V**
  - Re-commenting the ```#define COMMON_ANODE``` so that it appears as ```//#define COMMON_ANODE```

## Exercise 12: An RGB LED thermometer (AKA your final training task!)
In this example, your task is to use a thermistor to sense the temperature of your room (or your hand, or whatever), and have the RGB LED change its colour depending on the value. You'll need to merge the wiring and code from the previous example with those for a thermistor. In the steps below, we'll connect the thermistor first and then move code from the thermistor sketch into the RGB LED one. 

#### Your tasks:
- Keep your RGB LED wired as it was in the previous example.
- Open a new sketch and remove all of the default code. Keep the sketch from the last example handy, as well. You'll need it.
- Go to [this Thermistor example webpage](https://playground.arduino.cc/ComponentLib/Thermistor2/)
  - Wire the thermistor into the breadboard according to what's outlined under the **Thermistor Test Schematic** heading. Note that this schematic looks a little different than you're used to. It may take a few minutes to figure out what's being described.
    - **NOTE**: that in this example, you have to connect more than one component to **5V**, but there is only one **5V** pin available. Use jumpers to connect the **5V** and **GND** pins of the Arduino to the two separate rails, and then connect the RGB LED and thermistor to the appropriate rail using jumpers.
  - Copy the code provided beneath the **The Elaborate Code (cleaned up a bit)** heading and paste it into your blank sketch (be sure not to copy over any text outside of the code box). Review the code and attempt to understand how it works.
    - Notice that this sketch uses an additional function (called *Thermistor*), which takes the raw current reading, converts it to temperature in Celsius, and returns the value as a floating point number. This function is called within the loop function. 
- Save your sketch and upload it to the Arduino
- If the upload works, open up your Serial Monitor to inspect the temperatures being returned to the screen. **NOTE** that the baud rate needs to be changed in the Serial Console window to 115200, in order to correspond with the rate set in the setup function (```Serial.begin(115200);```).
  - Test the thermistor at different temperatures by touching it with your warmed-up hand, an ice pack, etc. Confirm that temperature changes in an expected manner. 
- Once you're confident that your thermistor is working, your task is to merge the relevant code from the thermistor example into the previous RGB LED code. 
  - Be sure to move pieces into the proper locations of the RGB LED script
    - lines before the setup function should be moved to above the setup function in the RGB LED script.
	- lines from the setup function should be moved into the setup function in the RGB LED script.
    - lines from the loop function should be moved into the loop function in the RGB LED script.
  - Note that you want only one setup and loop function in the final script.
- Next, you will want to replace the original content from the RGB LED loop function with code that will change the LED colour based on the value of temperature. There are likely many ways to accomplish this, but the most straightforward way is probably to use an [if/elseif/else](https://www.arduino.cc/reference/en/language/structure/control-structure/else/) statement. 

<br>

## Finishing up
Once you've completed your RBG LED thermometer: 
- Save your sketch and upload it to your GitHub repository. 
- Complete the **Day 2: Results** section in your project page (/docs/index.md) of your GitHub repository.

# Part 2: The Great Arduino Make-Off






[BACK TO MAIN PAGE](index.md)











































