---
layout: post
title:  "Networking"
date:   2020-12-28 17:55:40 -0500
---
One of the unique things about the NodeMCU module is that it has WiFi built-in. This means that
you can connect to it wirelessly without any additional hardware. However, in order to do this,
you need to tell it how to connect to your WiFi network. Fortunately, this is really easy to do.

To complete this step, you will need to know the SSID of the network you want to connect to, and
the password for the network.

Once you have this information, enter the following Python commands:
```
import network
wlan = network.WLAN(network.STA_IF)
wlan.active(True)
wlan.connect('<SSID>', '<password>')
```

`network` is another module and `WLAN` is a class that is used to control the network configuration
on the NodeMCU. These statements initialize the WiFi on the NodeMCU.

If you have entered the SSID and password for your WiFi network, correctly, the following statement
should display the result `True` as shown:

```
>>> wlan.isconnected()
True
```

If it does not, wait some time and try again. If you've waited a couple of minutes and it still returns
False, then ensure you have entered the SSID and the password correctly.

Once the NodeMCU has successfully connected to your WiFi network, you need to determine its `IP address`.
You can do this with the following command:

```
>>> wlan.ifconfig()
(‘192.168.1.230’, ‘255.255.255.0’, ‘192.168.1.1’, ‘192.168.1.1’)
```
In the output shown, the IP address for the board is the first set of numbers shown: `192.168.1.230`.
You will need this address in order to connect to your NodeMCU board over your network.

Once you have determined the IP address for the board, you can connect to it using something called
`WebREPL`. To do this, open up [http://micropython.org/webrepl/](http://micropython.org/webrepl/) in
your browser.

When you open this site, you will see a page that looks as shown below:
![Python Interpreter](/NodeMCU/assets/webrepl.png)

Replace the `192.168.4.1` with the IP address that you determined above. Make sure you don't remove the
`ws://` prefix or the `:8266/`. The connection to your board will not work properly without it. Once you
have entered this, click on `Connect`. You will then be prompted for a password. Enter the password that
was included in the kit. Once you have entered the password correctly, you should see the following:

```
Welcome to MicroPython!
Password:
WebREPL connected
>>>
```

You might recognize the `>>>` from before. This is the same Python prompt from before. You can enter the
same script from the previous lesson and turn the light on and off:
```
from machine import Pin
p2 = Pin(2, Pin.OUT)
p2.on()
p2.off()
```
