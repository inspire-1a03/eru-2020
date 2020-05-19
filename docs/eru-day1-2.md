---
title: eru-day1-2
---

[BACK TO MAIN PAGE](index.md)

# ERU - Day 1 & 2 Worksheet
Worksheets for the first two days of Electronics for the Rest of Us.
<br>

# Part 1: Introduction (30 mins)

**Welcome to Electronics for the Rest of Us!**  

Thanks for being a part of this module. Over the next four days, we'll be working together to explore some fundamental concepts in electronics, programming, and version control--all while building some small but interesting devices! 

This module assumes no prior knowledge or experience with electronics or programming--we'll start simple and see how far we get!

This module will use a mix of asynchronous and synchronous activities, which will (hopefully) allow you to work at your own pace (and on your own schedule), while interacting with, supporting, and getting support from me and your peers. All of the materials for this module will be provided to you in both written and video formats--all of which will be presented on these webpages. For communication purposes, we'll use Microsoft Teams.  

## Learning Objectives
By the end of this module, you will be able to:  
- Explain the fundamental concepts and operational principles of simple circuits, sensors and actuators
- Apply fundamental principles to build simple circuits that interact with their surrounding environments
- Create and modify software code to control the device and create comments to document its functionality
- Apply your skills, knowledge and creativity in the process of creating an original electronic device
- Use Markdown to format text in a simple yet effective manner
- Create, edit, and version control files in a GitHub repository
- Use GitHub Pages to share your results on an openly-accessible webpage

A full course outline--including deliverables and evaluation criteria can be found on the [outline page](https://inspire-1a03.github.io/eru-2020/eru-outline.html).

## Introduction to the module

The following introductory slideshow will be presented by Jay during the opening class. It provides an overview of the module, its components, expectations, and deliverables. 

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vRGF9iiknpFD8UbYc0AZwdgcNO8SvpcMJ73Y5ASyecBScyvJuylV-xTP95J_hA42YNe1FkxRFMuXxhE/embed?start=false&loop=true&delayms=15000" frameborder="0" width="640" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<br>
[View slides in PDF format](eru-pres-intro.pdf)
<br>

### (OPTIONAL) Pre-recorded presentation
<iframe width="787" height="443" src="https://www.youtube.com/embed/53GxKjCGzK0" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>
<br>
## Intro to Arduinos, Sensors, and Actuators

Follow along with this short presentation of the types of electronic components we'll be using in this module. Feel free to unpack your kit and check out the components.

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vTmmHAFZtXujn8wWzg8aTdFP0gDFyNTXNqNNpOPwptnSYu_14RDOZCadPCjTX0ELT_yyDm-w6Qh6fWv/embed?start=false&loop=true&delayms=15000" frameborder="0" width="640" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<br>
[View slides in PDF format](eru-pres-arduinos.pdf)
<br>

### (OPTIONAL) Pre-recorded presentation
<iframe width="786" height="442" src="https://www.youtube.com/embed/P54mvrdjD0g" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>

# Part 2: Getting started with Arduinos (75 mins)
<br>

### (OPTIONAL) Exercise 1-7 explainer video 
You can use this video to supplement the instructions listed below for Exercises 1 through 7.
<iframe width="787" height="443" src="https://www.youtube.com/embed/M32NmtEWM4E" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## > Exercise 1: Physically connecting the Arduino to your computer
Now that you've unpacked your kit, it's time to plug in your Arduino and begin using it. 

#### Notes: 
- The Arduino can use the USB port to communicate with your computer, as well as draw power from is. Use the USB cable provided to connect the Arduino to your computer's USB port. If done correctly, the on-board LED labelled "**ON**" should light up. If this doesn't work, disconnect and attempt again. 
- Depending on what program was uploaded to your Arduino board last, you may or may not see the on-board LED labelled "**L**" light up or flash. Arduinos will run its uploaded program upon power-up, and will continue to do so until the *reset* button is pressed, the power is disconnected, or the board breaks. 
  - Note that the on-board LED labelled "**L**" is connected to digital input/output (IO) pin number 13; if the current program provides instructions for current to be provided to pin 13, it'll be reflected in the on-board LED (whether or not anything is connected to digital pin 13. 
  
### Task: Open the Arduino IDE; Connect to the Arduino board
Once your Arduino is physically connected to your computer, open up the Arduino IDE program. A new sketch window will appear. The sketch window contains a number of different areas, which are labelled below. You'll learn and use these functions throughout the module.

![Arduino IDE with parts labelled](images/arduino-ide.png "The Arduino IDE")

Depending on your operating system, your Arduino may or may not be connected via a serial port (which allows for communication between the computer and the Arduino). 
- You can check the status of your connection by clicking on >Tools>Port. 

A physically connected Arduino should appear in the Serial Ports list as **COMX (Arduino UNO)** as shown below:

![Arduino IDE with Ports window showing](images/arduino-port1.png "Arduino IDE Ports list -- Arduino not connected")

To establish the serial connection, click on the listed COM port that where the Arduino is connected. A check mark should appear beside the port when a connection has been made.
![Arduino IDE with Ports window showing](images/arduino-port2.png "Arduino IDE Ports list -- Arduino connected")
<br>
<br>

## > Exercise 2: Uploading and running a program
In this exercise, you are going to upload your first program to the Arduino. For this case, we'll use one of the example programs that come with the Arduino IDE.

### Your tasks
Open the built-in example called *Blink*
- Go to >File>Examples>0.1Basics> and click on **Blink**. This will open up a new sketch (what Arduino calls its programs) with the Blink program. 

![Arduino IDE showing the blink program](images/opening-blink.png "Opening blink in the Arduino IDE")

Upload "Blink" to the Arduino:
- Ensuring that the Arduino is connected (both physically and through the COM port), click the upload button. 
  - The status window should first indicate that it is *Compiling sketch*, and then indicate that it is *Uploading*.
- If the upload was successful, the status window will indicate *Done uploading*, and the info window will communicate the following (or similar):
```
Sketch uses 924 bytes (2%) of program storage space. Maximum is 32256 bytes.
Global variables use 9 bytes (0%) of dynamic memory, leaving 2039 bytes for local variables. Maximum is 2048 bytes.
```
#### Question: 
What is happening on your Arduino board 


- If an error occurs, the status window will provide a general error message, and the info window will give additional information on it (you may need to scroll to see it). 
  - If the error occurred when uploading (i.e. a connection couldn't be made between the computer and the Arduino), the status window will read: *An error occurred while uploading the sketch*. 
  - If the error occurred when compiling the code (i.e. there's something wrong with your code), the status window will provide an error message, and the problematic line will be highlighted in the sketch. 
<br>
<br>

## > Exercise 3: Understanding an Arduino sketch
The blink sketch provides a good opportunity to explore the three fundamental elements of an Arduino sketch. 

### Element 1: The commented preface
![Arduino blink sketch comments](images/blink-comment.png "Blink sketch comments")

The opening, grey-text section of the sketch is a block comment that contains human-readable information about the program. This section is ignored by the Arduino compiler, and its sole purpose is to provide humans (whether yourself or others) with more information on the code. Comments can be inserted into a sketch as a block using the ```/*``` and ```*/``` characters around the commented text, e.g:
```
/* 
All of this is 
a comment
*/
```

Comments are an important part of writing and maintaining computer code, as it's often much easier to understand what the code is doing when there is plain, human-readable text accompanying it. It's also important to record your changes over time. Additionally, you can use comments to temporarily remove certain lines of code that you don't want to be executed.

A good commented preface should contain some/all of the following information:
- What the code does.
- A description (or link to a diagram) of the circuit that it works alongside. 
- Links to any other information.
- Who created it, revised it, and when this was done.
- Information on licensing / rights on the code.


You'll also notice later in the sketch that comments are inserted on single lines (whether at the start or end) using the ```//``` characters: 
```
// This is a commented line
```

### Element 2: The setup function
![Arduino blink sketch setup function](images/blink-setup.png "Blink sketch setup function")

As mentioned in the comment above it, the setup function runs a single time when the board is turned on, reset, or when a new program is uploaded to it. The purpose of the setup function is to declare constants and run commands that configure the Arduino board to operate as desired in the following loop function. 

Note the general structure of a function used for the setup function (and other functions):

```
<returned_value> <name of function> (<input values>){
first command; //commands end with a semicolon
second command;
third command;
...
} // curly braces contain the commands at the top and bottom
```

In this case, there is no returned value (the term ```void``` is used to indicate this), the name of the function is *setup*, there are no input values (thus the empty parentheses), and there is only one command executed.

#### Q1: 
- In this example, the only command executed in the setup function is ```pinMode(LED_BUILTIN, OUTPUT);```. What does this line do? 

#### A1: 
- ```pinmode``` is a built-in function that allows you to determine whether a given digital pin should be *INPUT* (receives current) or *OUTPUT* (delivers current). 
- The first *argument* to the function, ```LED_BUILTIN``` is a built-in constant that refers to digital pin 13, which is connected to the built-in LED on the Arduino board (labelled **"L"**). Note that you could replace ```LED_BUILTIN``` with ```13``` and it would work just the same. 
- The second *argument*, ```OUTPUT```, indicates that digital pin 13 should be set to output current.

### Element 3: The loop function
![Arduino blink sketch loop function](images/blink-loop.png "Blink sketch loop function")

As also indicated in the preceding comment, the loop function will run repeatedly for as long as the Arduino board is powered and operational. The loop function uses the same form as described above, and contains four lines of executed commands. 

#### Q2:
- What instructions are each of these lines providing to the Arduino board?
<br>
<br>

## > Exercise 4: Modifying a sketch
#### Your tasks:
Modify the Blink code so that the onboard LED blinks at a different frequency. **Remember** to save your code and upload it to the Arduino after you've modified it.
- How fast can you make it blink? 
- Can you make it blink at always-differing intervals? 
When you've finished, save your sketch (using a relevant name) to your computer
- **TIP**: You will probably be prompted to save your sketch to a default folder called **Arduino** (or something similar). It's fine to save your sketches here or in some other directory--it's really your preference. BUT, be sure to be consistent with the working folder/directory that you use throughout this module. Otherwise, you may forget where things are. 
<br>
<br>

## > Exercise 5: Inserting an LED
If you recall from earlier, the on-board LED (indicated by ```LED_BUILTIN``` in the Arduino code) is also connected to digital pin 13 on your Arduino board. You can connect an LED to this pin in a circuit by connecting one leg to digital pin 13 and the other to the adjacent pin labelled **GND**.
- The **GND** is the *ground* connection of the circuit. Circuits require a higher- and lower-voltage connection to permit current to pass through it. The ground pin often serves this purpose. In this case, digital pin 13 serves as the higher-voltage connection, and current flows from pin 13, through the LED and toward GND. 
- Try connecting one of your standard (two-legged) LEDs. If it doesn't work, turn it around and connect it the other way. 

#### Question: 
- What happened? Did it work in both directions? 

#### Answer: 
- You probably noticed that it only worked in one direction. This is because an LED is a uni-directional device. Current must enter through the anode (connected to pin 13 in this case) and leave through the cathode (connected to GND in this case) for light to be generated. 
- The anode and cathode can usually be identified with a couple of visual queues: The anode has a longer leg, and the cathode has a flattened plastic bottom brim. 

![Image of LED](images/led.png "LED: Anode and Cathode")
<br>
<br>

## > Exercise 6: Reviewing our circuit
So, you may be asking yourself at this point: *"Is that the proper way to connect that LED?"*. This is an excellent question. To find the answer:
- Navigate to the [Arduino tutorial page for Blink](https://www.arduino.cc/en/Tutorial/Blink) (which is provided in the comments of the Blink code)
- Note the hardware required
- Scroll down to view the circuit diagram. **What's missing from our current circuit?**

Before we move forward, you'll need to understand how to identify the proper resistor to place into the circuit. 

### Resistors 
Resistors are important elements of circuits, as they control the flow of current through a circuit. This may be necessary to ensure that a connected device works properly, or to protect it from being damaged by current that is too high. The higher the resistance of a resistor, the more current is restricted through it. The unit of resistance is referred to as the ohm (symbol &#937). Resistors use colour codes to indicate their resistance value--these may be communicated using 4- 5- or 6-band systems. 

Here's a diagram demonstrating the 4- and 5-band systems: 
![Resistor color code chart](images/resistor-codes.png "Resistor Colour Code Chart")

And here's a further explanation of the examples: 
![Resistor color code chart](images/resistor-example.png "Resistor Colour Code Chart Explained")

#### Question 1
Use the colour code above to answer the following questions: 
- What colour code would be found on a 10 Kohm (10000 ohm) resistor using: 
  - Four bands?
  - Five bands?

#### Answer 1
Use [resisto.rs](http://resisto.rs/) to assess your answer (enter ```10K``` into the box). A resource like [resisto.rs](http://resisto.rs/) is useful when you have a desired resistance and want to know the colour code.

#### Question 2
Identify all of the 10 Kohm resistors in your kit
- ***Hint***: there may be a mix of 4- and 5-band codes used

#### Question 3
Use the colour code chart to identify the resistance of the other resistors in your kit (hint: the rest all have the same resistance and all use a 4-band colour code).
- ***Hint:*** Use a resistor colour code calculator like [this](https://www.digikey.ca/en/resources/conversion-calculators/conversion-calculator-resistor-color-code-4-band) to assess your answer. These kind of calculators are useful when you have a resistor in hand (i.e. you know the colour code), and need to know its resistance.
<br>
<br>

## > Exercise 7: Building a proper circuit
Now that you've properly identified the resistor you need for this circuit, how are you going to connect the pieces?
- You could attempt to twist the wires together, but you might break something and it won't be very reliable
- You could solder the pieces together, but we're just experimenting here. 
- **To connect this circuit, we're going to use a solderless breadboard**

### Solderless breadboard
The solderless breadboard allows you to create circuits quickly without the need for soldering connections together. 
- Metal strips run through the backside of the breadboard, which connect specific rows and columns together in a defined manner: 

![Solderless breadboard](images/breadboard.png "Solderless Breadboard")

Note in the example above that connections run horizontally across rows of 5 on the inner part of the breadboard, while connections run vertically down the outside columns. 

#### Your tasks:
Create the proper blink circuit using: 
- The solderless breadboard
- The LED from the first circuit
- An appropriate resistor
- Jumper cables to connect the breadboard to the Arduino pins.
When you've succeeded, save your sketch to your local working folder with an appropriate name.

#### Notes:
If you are unsure of how to connect items in your circuit:
- Review the solderless breadboard diagram. 
- Try to trace the flow of current through your circuit from digital pin 13 to GND. Is there an opportunity for the current to avoid flowing through the LED? 
- Remember that any two (or more) items inserted into a connected row are all connected to each other at the same time--if you have all of your wires and LED legs plugged into a single row, the current will divert around your LED and flow straight from pin 13 to GND. Turn your LED 90 degrees (so legs are in different rows) and try again to connect the circuit.
<br>
<br>

## > Exercise 8: Using a button
In this example, you'll use a button to turn your LED on (when pushed) and off (when not pushed).

### (OPTIONAL) Exercise 8 explainer video 
<iframe width="787" height="443" src="https://www.youtube.com/embed/EaIkORyZHMU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>

#### Notes 1:
1. This example uses the on-board LED at pin 13. If you'd like, leave your LED circuit wired into the breadboard from the Blink example--it'll light up when you push the button. 
2. **How the button works**: The opposing legs of a button are connected to each other internally. When the button is not pushed in, the two sets of legs are not connected to each other. When the button is pushed, a metal gate closes to connect the two legs together, allowing current to flow from left to right across the button
![Arduino Button](images/button.png "Arduino Button")

#### Your tasks: 
- Open the Button sketch from the Arduino IDE at >File>Examples>0.2Digital> and click on **Button**
- Navigate to the Arduino [Button tutorial page](https://www.arduino.cc/en/Tutorial/Button) to find the hardware requirements and circuit diagram.
- Take a close look at the code, and try to make sense of it.
- Complete the circuit wiring and upload the code to the Arduino.
- Verify that it works as desired. 
- Take a photo of your completed device in action (*you'll use this with your first reflection*).

#### Notes 2:
1. The 10K resistor serves as a pull-down resistor in this example, as it ensures that digital pin 2 is kept at LOW when the button is not pressed. Otherwise, the input may 'float', returning LOW and HIGH randomly, causing the LED to also blink randomly.  
2. This example declares both constants (values that won't change) and variables (values that may). 
  - The line ```const int buttonPin = 2;``` creates a constant (*const*) named *buttonPin* that is an integer (*int*, as opposed to other types--see [here](https://www.arduino.cc/en/Reference/VariableDeclaration) for more information), which has a value of 2. 
  - The line  ```int buttonState = 0;``` creates a variable named *buttonState* that is an integer with an initial value of 0.
3. In the line ```buttonState = digitalRead(buttonPin);```, the function *digitalRead* is used to read the state of the button on pin 2 (which is the value of buttonPin). The result (HIGH or LOW) is saved to the variable *buttonState*. 
4. An *if* statement is used to control the output on the ledPin (digital pin 13) depending on the value of *buttonState*.
  - An if statement takes the general form: 
```
if (condition1) {
  // do Thing A
}
else if (condition2) {
  // do Thing B
}
else {
  // do Thing C
}
```
See the [Arduino if-else reference guide](https://www.arduino.cc/reference/en/language/structure/control-structure/else/) for more information. 
<br>
<br>

# Part 3: Getting familiar with GitHub, Markdown, GitHub Pages (60 mins)
In this part, you'll learn about and gain experience with the other pieces of technology that will be used in this module: GitHub, Markdown, GitHub Pages. Used together, these tools will allow you to: 
- Document your work and store your code
- Keep track of version changes to your documents and code; restore previous versions, if necessary
- Create and publish a webpage that documents your work in this module with only a minimal amount of HTML knowledge. 

## Introduction
Follow along with the slideshow for an introduction to these tools, and an explanation of how we'll use them: 

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vS_OAbvhJsCaoWjW9PjGOIBpk0tO1Fi9vGMhiaKfHsC340OTUXjUbXyvMqtcVTgkT2COvU0gVpJTA3o/embed?start=false&loop=true&delayms=15000" frameborder="0" width="640" height="389" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>
<br>
[View slides in PDF format](eru-pres-arduinos.pdf)
<br>


### (OPTIONAL) Pre-recorded presentation
<iframe width="786" height="442" src="https://www.youtube.com/embed/bL38CO-g1qw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## > Exercise 9: Create your own GitHub repository
In the exercises to follow, you'll create a GitHub repository for the purposes of learning how to use GitHub, Markdown, and GitHub pages.

### (OPTIONAL) Examples 9-13 explainer video
<iframe width="786" height="442" src="https://www.youtube.com/embed/FjGR76Wl1xI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
<br>
<br>
#### Your tasks:
- From your GitHub main page, click on the green **New Repository** button. This is the repository (storage location) where the content of your website will be hosted. 
  - Provide a name for your repository. The name you enter will determine the URL of your repository.
    - i.e. ```https://github.com/<your-github-username>/<your-repo-name>```
	- e.g. ```https://github.com/jasonbrodeur/DASH-githubpages``` is a GitHub repository (*repo*, for short) that I've created in the past.
- Check the box to **Initialize this repository with a README**
- Click the **Create repository** button
- Your browser will now open to the top-level page of the repository. Your repository will contain one markdown file: **README.md**. 

#### Notes: 
- Your README file is a plan text file (same as a .txt file), but the **.md** extension is used so that GitHub recognizes that the file uses markdown inside. One of the nice features of markdown files is that they are readable by almost any applications, since they are plain text files.
<br>
<br>

## > Exercise 10: Create a folder and a text file within it
In this task, you'll create a folder that we'll need to initiate the webpage, and you'll learn how to create and edit files. 

#### Your tasks:
Create a folder named ```docs``` in the top level of the repository. This is where the webpage content will live. We also want to create a file in this folder called ```index.md```. This will be the home page for your website.
- In the top-level repository page, click **Create new file**
- In the **Name your file...** box, enter ```docs/index.md```. Click **Commit change**. You will now have a folder named ```docs``` in your repository with a file named ```index.md```.

#### Notes:
- To create a file, simply enter the desired name and file extension. 
- To create a folder, you need to add a trailing slash (/) to the name, and you need to [create a file within the folder](https://github.com/KirstieJane/STEMMRoleModels/wiki/Creating-new-folders-in-GitHub-repository-via-the-browser), since empty folders aren't saved. You can always delete this file later.
<br>
<br>

## > Exercise 11: Edit your text file

#### Your tasks:
- Click on the ```index.md``` file to open it in the file viewer page
  - On the file viewer page, click the edit button (pencil icon) to switch to editing mode
  - Add a bit of text to this file (anything is fine). 
  - When finished editing, scroll to the bottom of the page to the **Commit changes** box. 
  
#### Notes:
- The **Commit changes** box is used to record information about changes before you commit them. 
  - (optional) If interested, modify the comment from **Update index.md** to something more descriptive
  - (optional) Add a description, if desired
- Click the **Commit changes** box to finalize your commit. Your changes will be represented in the file. 
- If you'd like to better understand how GitHub keeps track of file changes and history, from the **index.md** file viewing page, explore the *Blame* and *History* buttons.
<br>
<br>

## > Exercise 12: Exploring repository features and settings; Configuring GitHub Pages
In this step, we'll explore some of the functionality available in a GitHub repository and show you how to get started with [GitHub Pages](https://help.github.com/en/github/working-with-github-pages/about-github-pages)

#### Your Tasks:
- Ensure that you've created the ```docs``` folder and the ```index.md``` file, as outlined in the previous step.
- From the top-level repository page (i.e. the one where you can see the ```docs``` folder and ```README.md``` file:
  - Explore the various Features (tabs) that are available within a repository
  - Open the Settings Tab. Explore the various Settings tabs.
- On the **Options** subpage (topmost side menu item), scroll down to the **GitHub Pages** section
  - For **Source**, select **master branch /docs folder** (note you could also pick the *master branch* option, but not for this example.)
  - Click **Choose a theme** to select a theme for your webpage
- Congratulations, your website is ready. The link will be provided in the GitHub Pages section.
  - You may initially receive a 404 error, but after a minute, your website will appear with the content from ```index.md```
Remember: By default, GitHub Pages expects at least one file in the ```docs``` folder named ```index.md```. This becomes the main (home) page for the webpage.
**Now, it's time to add some content!**
<br>
<br>

## > Exercise 13: Creating content with Markdown
One of the really nice things about GitHub and GitHub Pages is that you can use Markdown to format text on a webpage without the use (or knowledge!) of html code (though you can insert it if you need to!). This makes it really easy to create content. In this section, you'll learn a bit more about Markdown and how to use it to create formatted text. 

### What is Markdown? 
Borrowed shamelessly from Github's [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) page: 
> Markdown is a way to style text on the web. You control the display of the document; formatting words as bold or italic, adding images, and creating lists are just a few of the things we can do with Markdown. Mostly, Markdown is just regular text with a few non-alphabetic characters thrown in, like # or *.

Markdown uses simple notation to apply simple formatting rules. Since it's pretty much just plain text, it's transferrable and much simpler than marked-up text like HTML or even Word or Google documents. It's also very readable in its plain text format, which is nice. For much of the writing that you do for the web, Markdown is good enough. Github uses Markdown for its documents (this document was created in markdown), as does a variety of other web platforms (Reddit and Trello, as examples). 

#### Note:
While editing markdown files in the GitHub editor, use the **Preview changes** tab to see (mostly) how it will render on the web. Note that some content (like html code) won't render properly on GitHub, but will on your webpage. 

#### Your tasks: 
- Using the Github editor, open ```index.md``` for editing and add some content to it. If you would like to add a title to your page, add the following text at the top:

```
---
title: <enter your title here>
---
```

- Use the [Mastering Markdown guide](https://guides.github.com/features/mastering-markdown/) as a reference (or other guides on the web) to create a fictional document that contains most of the following elements: 
  - Headings of a number of different levels
  - bolded, italicized text 
  - insert an image from the web
  - (optional) insert an image that is hosted in your GitHub repository
  - An ordered list
  - A bulleted list
  - A link to another website 
  - A snippet of code
  - A table
  - And finally, an emoji! 
<br>
- When satisfied, commit your changes
- Refresh your website main page to see the updates (note that it may take a minute to update).

## (Optional) Doing more with GitHub pages
If you're interested in learning how to add multiple pages to a site and embedding content like slideshows and YouTube videos, work through the additional tasks on the [GitHub Pages Extra](eru-github-pages-extra.md) page.

For more information and references for Markdown, refer to:
- [Mastering Markdown](https://guides.github.com/features/mastering-markdown/) 
- [Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
- [Daring Fireball's Markdown Introduction](https://daringfireball.net/projects/markdown/)
<br>
<br>

# Part 4: Day 1 Wrap-Up (30 mins).
Now that you've been introduced to GitHub and markdown, it's time to create your first website with GitHub Pages, and add an image and text for your day 1 reflection. Refer to the module [outline page](eru-outline.md) for more information on evaluation criteria.

## Turn your module repository into a webpage 
- In your pre-module setup [instructions](eru-setup.md), you were instructed to use [this link](https://classroom.github.com/a/zuDd-h3v) to create a GitHub repository for this module. 
- Once this is completed, your repository will be created at a url of the form: ```https://github.com/inspire-1a03/intersession-2020/<your_github_username>```
  - Your repository comes pre-populated with a ```/docs``` folder with an ```index.md``` file inside of it. The **index.md** file is where you will create your project webpage. Some headings and comments have been added to this file to guide you through your deliverables.
- In your repository's top-level page, click on the *Settings* tab and scroll down 
  - On the **Options** sub-page (topmost side menu item), scroll down to the **GitHub Pages** section
  - For **Source**, select **master branch /docs folder**
  - Click **Choose a theme** to select a theme for your webpage
- The link will be provided in the GitHub Pages section. 
![Enabling GitHub Pages](images/github-pages.png "Enabling GitHub Pages")
<br>
- For easy reference, copy the URL to your webpage, and paste it into the description box in your top-level repository page by clicking *Edit* and pasting the URL into the *Website* box and clicking *Save*.
![Adding a website address to a repository](images/website-url-add.png "Adding a website address to a repository")

## Add your reflection text
- Beneath the **Day 1:Reflection** heading, provide a ~250 word reflection on your first day of the module, and discuss why you're interested in this module and what you hope to take away from it.

## Upload your photo to your module GitHub repository
- Upload your photo of the device created in the **Button** example, to the ```/docs/images/``` folder of your module repository. 
  - Navigate to the ```/docs/images``` folder and click the **Upload files** button. 
![Upload files button](images/image-upload.png "Uploading files to the images folder")
- Select the file and commit changes (directly to the ```master``` branch.

## Insert your uploaded photo into the markdown file
- Edit your ```index.md``` file to insert the image beneath your day 1 reflection text. When inserting the file, refer to its location in the ```/images``` folder. For example, if your uploaded image was named ```firstday.png``` your markdown code would look something like the following (though the description and title may be different): 
```
![A photo of an arduino circuit](images/firstday.png "Arduino Circuit from the Button Example")
```
<br>
<br>

# Part 5: Intermediate circuits (90 mins)
In the following examples, you'll build upon earlier work to create increasingly complex circuits that require unique code to work. 
<br>
<br>

## > Exercise 14: Using a potentiometer
In this example, you'll use a potentiometer (the blue turn dial) to control the brightness of your LED. 

### (OPTIONAL) Exercise 14 explainer video
<iframe width="787" height="443" src="https://www.youtube.com/embed/9GYFeAeXMxM" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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
<br>
<br>

## > Exercise 15: Potentiometer out, photoresistor in
In this example, we’re going to start with the code and wiring used in the previous example, but replace the potentiometer with a photoresistor. The point of this is to demonstrate how both components can be used as control devices by providing variable resistances. This exercise will require you to merge the existing wiring and code from the [AnalogInOutSerial](https://www.arduino.cc/en/Tutorial/AnalogInOutSerial) example, and merge in elements of the [AnalogInput](https://www.arduino.cc/en/Tutorial/AnalogInput) example (namely, the photoresistor example). 

### (OPTIONAL) Exercise 15 explainer video
<iframe width="787" height="443" src="https://www.youtube.com/embed/_R2eAaKamnA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Your tasks:
- Use >File>Save As... to save a copy of the AnalogInOutSerial code to a new sketch file in your local working directory. Name the sketch with something descriptive. Use this code as the basis for this example. Upload it to the Arduino.
- Remove the wiring for the potentiometer, and replace it with the wiring shown for the photoresistor on the [AnalogInput](https://www.arduino.cc/en/Tutorial/AnalogInput) information webpage. 
- Once you have wired it properly (using the Serial Monitor to confirm), experiment with changing light levels on the photoresistor (using a bright light / covering it with your finger, etc.). Observe the results in the Serial Console (i.e. the range of input values from the photoresistor and the corresponding output values for the LED). Do the values span close to the entire ranges for these devices (0 to 1023 for the photoresistor and 0 to 255 for the LED)? 
  - If not, modify the **map** function in your code so that the LED brightness ranges from off to full brightness. 

#### Notes
1. Be sure to save your changes and re-upload the program as you make changes!
2. Notice in this example that the **5V** and **GND** pins of the Arduino are connected to the outside 'rails' of the breadboard, and that these rails are used to connect to the device. Given that the rails are connected down an entire column, this approach can be helpful when you need to connect more devices to **5V** and **GND** pins than are available.
 
![AnalogInput Circuit Diagram](images/analog-input.png "AnalogInput Circuit Diagram")
<br>
<br>

## > Exercise 16: Connecting an RGB LED
Here, you'll be connecting an RGB LED to the Arduino, using a guide that has been provided by Adafruit--a company that provides a wide range of DIY electronics and tutorials. 

### (OPTIONAL) Exercise 16 explainer video
<iframe width="786" height="442" src="https://www.youtube.com/embed/JE47V8RYoUw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

#### Notes:
- An RGB LED contains three LEDs (red, green, and blue) integrated into a single casing. By controlling the brightness of each colour (using PWM), it's possible to create a wide variety of colours. Three of the LED legs correspond to one of these LEDs; depending on which time of RGB LED is being used (common anode vs common cathode), the fourth leg connects to either HIGH (5V) or LOW (GND):
  - For common anode RGB LEDs, the longest leg connects to HIGH (5V), and each of the shorter legs act as cathodes. 
  - For common cathode RGB LEDs, the longest leg connects to LOW (GND), and each of the shorter legs act as anodes.  

#### Your tasks:
**PLEASE ASSUME YOU ARE USING A COMMON ANODE RGB LED AND FOLLOW INSTRUCTIONS ACCORDINGLY**
- Create a new sketch. Delete all of the code so that you have a blank sketch
- Follow along with the instructions provided on the [Adafruit Learn webpage](https://learn.adafruit.com/adafruit-arduino-lesson-3-rgb-leds/breadboard-layout) to connect the RGB LED to the Arduino via the breadboard. 
  - **NOTE**: Use your 220 &#937 resistors in place of the 270 &#937 resistors asked for on the instruction page. The RGB LEDs are tolerant to the small difference in resistance. In a pinch, you can even run these for a while without any resistors.
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
<br>
<br>

## > Exercise 17: An RGB LED thermometer (AKA your final training task!)
In this example, your task is to use a thermistor to sense the temperature of your room (or your hand, or whatever), and have the RGB LED change its colour depending on the value. You'll need to merge the wiring and code from the previous example with those for a thermistor. In the steps below, we'll connect the thermistor first and then move code from the thermistor sketch into the RGB LED one. 

### (OPTIONAL) Exercise 17 explainer video
<iframe width="786" height="442" src="https://www.youtube.com/embed/Ge9ytNeKzXk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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
- Save your sketch to your working directory. 
<br>
<br>

## Part 6: Day 2 Wrap-up
Once you've completed your RBG LED thermometer: 
- Upload your saved sketch to the top-level directory of your GitHub repository. 
- Complete the **Day 2: Results** section in your project page (/docs/index.md) of your GitHub repository.
Refer to the module [outline page](eru-outline.md) for more information on evaluation criteria.


During the last hour of day 2, you'll be given an hour to chat with your breakout group peers to brainstorm ideas for your days 3 and 4 challenge: **The Great Arduino Make-Off**
- Review the instructions provided in your [Day 3 and 4 instruction page](eru-day3-4.md)
- Connect with your breakout group and discuss some ideas.

[BACK TO MAIN PAGE](index.md)
