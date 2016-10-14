Demiduino
=========

Hardware
--------

Demiduino is an open source
hardware circuit board designed to
introduce people to electronics
prototyping and the Arduino
platform.

The PCB design is inspired by an
Arduino, but divided in both
dimensions by 2.4. This makes it
smaller than an SD card and less
than 1 square inch in total.

There are only about a dozen
components, and they are all
through-hole mounted so that the
circuit can be assembled by
somebody who has had no previous
experience with soldering.

The microcontroller is a socketed
ATtiny85, so that replacing it or
leaving it in another circuit is
practical.

Power is provided by a USB mini
port or lithium battery cell with a
standard connector, and is
regulated by a 3 volt regulator.
This enables compatibiltiy with
many sensors and modules and low
power consumption.

Because the circuit focuses on low
BOM cost and part count to reach a
wider audience (read: I can give it
away to my friends without going
broke), there are some compromises
made that are a little dubious. A
proper engineer who went to college
has made a device that this one is
heavily based on, and it's called
the Trinket by Adafruit. It's
probably more reliable, but
features entirely SMD components.

Software
--------

The Trinket bootloader has been
recompiled from source with my own
USB VID/PID pair. This is to
appease the USB police and so I
must ask that you don't use my USB
pair for derivative work. I'll
happily detail how I accomplished
this and probably should write a
tutorial at least for my own
reference, because all this took me
a couple days to figure out.

To make the IDE work, I also have
recompiled avrdude 6, changing the
USBispTiny VID/PID pair to my own
as well. Then I drop the new
avrdude bin into ./Contents/Resources/Java/hardware/tools/avr/bin.
This is the same path for the
avrdude.conf file. Basically I
forked the Adafruit Trinket Arduino
IDE I had on my system and now it
won't work with a Trinket, so I
have more than one copy of the IDE
installed.

I also modified the boards.txt,
programmers.txt, and theme files.
The first two files were just to
cut out the uneccessary stuff, and
the theme file was to make a dark
colorscheme for the IDE that pays
homage to OSHPark's awesome purple
boards. Compiling avrdude was done
on Ubuntu... narwhal? I forget, but
I like narwhals so lets go with
that. And the IDE runs both on that
linux machine and on OS X 10.9.
Also the libraries I'm using in the
IDE need to be cleaned up to only
be what's compatible with
Demiduino.
