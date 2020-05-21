---
title: arduino-troubleshooting
---
# Arduino Troubleshooting
Problem: Arduino board won't connect to the computer via the COM port, or you receive the error message: ```avrdude: stk500_recv(): programmer is not responding```. 


## Diagnostic
Courtesy [this resource](https://arduino.stackexchange.com/questions/13292/have-i-bricked-my-arduino-uno-problems-with-uploading-to-board)

1. When you plug it in, check that:
- LED **ON** light comes on
- The "L" LED should flash quickly 3 times. The "on" and "off" times are 50 ms each, the three flashes should be over within about 1/3 of a second (also happens after a reset).
2. When you try to upload a program, check that: 
- The "L" LED should flash 3 times. This is because the main chip is being reset by a command from the uploading process.
- The "Rx" LED should flash quickly. This is the instructions from the uploading process trying to activate the bootloader.
  - If only the "Rx" LED flashes, it could be because of a problem with the bootloader, or the main processor chip (Atmega328P)
- The "Tx" LED should flash quickly. This is the processor acknowledging the uploaded data.
- If all lights flash, check that proper board is selected in >Tools>Board>
- If Tx and Rx LEDs do not flash, check that the proper COM port is selected.
- ** If your board fails those tests, proceed below:**

## Do a loopback test
Follow the instructions listed in the **Do a loopback test** section of [this resource](https://arduino.stackexchange.com/questions/13292/have-i-bricked-my-arduino-uno-problems-with-uploading-to-board)
- ** If your board fails those tests, proceed below:**


## Check that the Arduino and Driver are properly installed
- Open up Windows control panel. Search for and select "Device Manager"
- Go to **Ports (COM & LPT)**
  - Ensure that Arduino Uno (COMX) is shown
    - Double-click the device and ensure that the Device Status says " This device is working properly."
    - Check the **Driver** tab to ensure that a driver has been installed.

- ** If your board fails those tests, proceed below:**
	
## Re-install the Arduino software 

## Straightforward stuff
- Try a new USB port
- Try a different USB cable
- Try a different computer

## Some weird stuff that shouldn't work
Courtesy [this thread](https://arduino.stackexchange.com/questions/18988/avrdude-stk500-recv-programmer-is-not-responding-avrdude-stk500-getsync)
- pressing the restart button after the program is compiled, then, upload it.
- Restart the Arduino while the Arduino is uploading the program.

