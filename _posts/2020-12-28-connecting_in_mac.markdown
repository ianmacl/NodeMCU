---
layout: post
title:  "Connecting to the NodeMCU on Mac OS X"
date:   2020-12-28 17:45:40 -0500
---
Now that the NodeMCU board has been connected to the computer, you are ready to connect to it and run your first
Python script on it.

To do so, you'll need to install software on your computer to connect to board. How this is done depends on whether
you are using an Apple computer or a Windows computer. If you are using an Apple computer, you should open up the App
Store and search for 'serialtools'. Install the program that is found in the search, and when it has finished
installing, open it.
![SerialTools](/NodeMCU/assets/serialtools.png)

Once you have opened the SerialTools program, you should see a dropdown option at the top left of the window named
`Serial Port`. Click on the dropdown, and select the option that starts with `usbserial`. On my computer, the option
is `usbserial-0001`. Then, select the dropdown named `Baud Rate` and select the option `115200`.

Once you have selected these options, click `Connect`. When you do this, you should see some text appear in the window,
and at the bottom, you should see the following:

```
MicroPython v1.13 on 2020-09-11; ESP module with ESP8266
Type “help()” for more information.
>>>
```

The `>>>` characters are the Python prompt, running on the NodeMCU. At this prompt, you can enter Python statements
and they will be executed.

For example, if you enter `print("Hello, World!")`, the statement will be executed immediately and the results will
returned:

```
MicroPython v1.13 on 2020-09-11; ESP module with ESP8266
Type “help()” for more information.
>>> print(“Hello, World!”)
Hello, World!
>>>
```
