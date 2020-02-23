# Ubiquiti Unifi Switch problems, issues, rambling and hopefully repair 

## US 16 POE 150W 
One of the more usual failures according to the Forums, the PSU had gone Bang. 
Since i don't like anything above like 60V, i just bought a new 200W meanwell powersupply and hacked that into the switch.
The mains connector just had to have two pins swapped and it is working great ever since. 

With the only exception of the first eight ports. 
### Dead Ports
The interesting behaviour on those ports is that they still work, kinda. 
PoE, PoE+ and even the Link detection and speed work. 
The controller gets to know that there is a device pluged in, what MAC it has and its vendor.

The device pluged in just does not get an ip. 

i have jet failed to find a good testsubjet, and just when i wanted to test it with a server of mine, the ipmi decided to crap out and not work anymore. 
Great! 

Older testing i still remember vaguely was even more intersting. 
A UAC LOCO or so, was pingable from my workstation but not the switch itself, and stopped being pingle after a moment. 
The behavior was kinda repeatable. 

#### Suspicion
I hope it is something replaceable, but i worry its not the large inductor filter thingys, so that would only leave a few smal diodes and the switch ASIC. 

Probably something dead inside like a vlan config, routing or what ever that prohibits traffic from those interfaces on Layer 3.
Possibly from to many changes to the config. 
I have heard that switche in schools for learning their config don't live that long comparibly. 

Config whise, all ports are set to the same group "lan" and no vlans are configured. So i can't see a configuration issue on my side. 

## US 24 POE What ever 
constantly reboots. 
Someone else tried their luck already. Beside soldering around on the POE addon board, there was a missing fuse on the underside of the single main Switch ASIC.
0 Ohm short to GND behind that fuse, so that ASIC is gone. 

## Edgeswitch 48 Lite
No lights at all.
The console prints uboot memtest Errors. 
Tried replacing the ddr3 module with no luck. 
Still the same failing memory test. 

Some people somewhere on the web assume bad "solder balls" in the BGA, but i kinda have my doubts.

Never the less, my quick hotair isn't enough to reflow those large BGAs so ima gona have to get the propper equiment for that someday. 
