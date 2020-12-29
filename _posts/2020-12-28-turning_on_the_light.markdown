---
layout: post
title:  "Turning on the Light"
date:   2020-12-28 17:50:40 -0500
---
Now that you have successfully connected to the NodeMCU and executed a Python statement, you are ready
to interface with the hardware on the NodeMCU.

MicroPython provides a module (a module is a set of tools that you can use to perform various tasks) to
interface with the hardware of the NodeMCU preinstalled. This module is called `machine`.

To turn on the LED (or light) that is on the NodeMCU board, enter the following commands:

```
from machine import Pin
p2 = Pin(2, Pin.OUT)
p2.on()
```

You can then turn the light off by entering the following command:
```
p2.off()
```

You can play around at this point, turning the LED on and off by using `p2.on()` and `p2.off()`.

## Some Explanation

You might be wondering at this point, what the lines in our script actually mean. Let's take a look:
`from machine import Pin` tells Python that you want to use the part of the `machine` library named
`Pin`. `Pin` is what is known as a `class`. The details of this aren't important right now. What you
need to do is that the `Pin` class is used to interact with the physical pins on the chip that is on
the NodeMCU board.

`p2 = Pin(2, Pin.OUT)` initializes pin 2 of the NodeMCU as an output. The `2` specifies pin 2, and
the `Pin.OUT` specifies that we want to initialize the pin to be an `output`. The `p2` part defines
something that is called a `variable`. You can think of a `variable` as a placeholder that you can
use to store information. Here, in our variable, we are storing a link to pin 2.

`p2.on()` tells pin 2 to turn on. You might have noticed that turning the pin on actually turns the
LED off, and turning the pin off actually turns the LED on.