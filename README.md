##### lalboard - A 3D-printed keyboard inspired by the DataHand.

<img src="https://jesusfreke.github.io/lalboard/lalboard.jpg" alt="drawing" width="595"/>

## Links

[More Images](https://github.com/JesusFreke/lalboard/wiki/Images)

[120 WPM Typing Demo](https://www.youtube.com/watch?v=oMhOIgrdeE0)

[V2 Project Logs (hackaday.io)](http://lalboard.com)

Online viewer for cluster assemblies:

- [finger](https://a360.co/3vxlLLL)
- [left thumb](https://a360.co/3c63TzE)
- [right thumb](https://a360.co/3c6tvws)

## Project Details

I am a long-time user of a DataHand keyboard. With the scarcity and rising cost of second hand
DataHands these days, I wanted to ensure that I always had access to a DataHand-like keyboard. And
so this project was born.

The overall functionality of the lalboard is obviously heavily based on the DataHand, but I designed
all of the specific key mechanisms, etc. from scratch, to be printable on a normal hobby-level
FDM printer.

With my DataHand, I never felt like I could get the keys positioned *quite right* for my hand. So
one of my primary focuses with the lalboard was adjustability. Each key cluster can be independently
adjusted in all 6 degrees of freedom to some extent.

Most parts need to be printed in a very opaque PLA, but there are a few parts that don't work well
in PLA which should be printed in polycarbonate or similar material, for its strength and heat
resistance.

##### Key Mechanisms

All keys use a pair of magnets to provide the clickiness and key return force, and an IR LED and
phototransistor for detecting a keypress. They are all held in place only with magnets, so they
are easily removable for cleaning, etc.

The feel/clickiness of the keys was another focus area. I tried to get them to feel as similar to
those on a DataHand as possible. They require roughly the same amount of force, and have that same
unique clicky feel due to the magnetic holding force.

##### Adjustability

The key clusters have a trio of standoffs that are designed to be mounted onto a steel sheet with
magnets. Each standoff has an adjustable height, and is mounted to the key cluster via a
ball socket. This provides a limited 6 degrees of freedom in adjusting the angle and position of
each key cluster, in order to get it perfectly positioned for your hands.

##### Fit

Fit is hard and individual.  Additionally, if you're not already a DH user, you'll be adjusting to the new mechanism, layout and typing style, too.  Doing all of this simultaneously can lead to overly fussy adjustment -- sometimes you just have to settle in.

Recommendations for fit:
Your hand should feel relaxed, and your palms should be supported beneath the center of the palm beneath the middle finger, at the minimum.  A palmrest that is too wide will cause discomfort in the outside of the hand, as the base of the pinky really wants to be able to curl around the palmrest a bit.

The palmrests should feel a little crazy tall compared to any other keyboard -- the motions are so small that you can get way more support from the palmrests on a lalboard/datahand.  That said, there are users who use the DH without palmrests at all, so it's a matter of experimentation and preference.  Start with rests, for sure because the relaxation of your hands from the high force, big motion world of traditional keyboards will take some time.

Finger position should be gently curved, maybe 45 degrees from vertical on the final knuckle to the keys -- too much curvature will cause a feeling of being cramped, with many unintentional N keypresses.  Too little will make you strain to hit the N keys.  You want to be able to relax and let your fingers extend naturally.

##### Electronics

As of V2, the lalboard uses standard PCBAs with a mix of SMT and through hole components.  The LEDs and phototransistors (PTs) are vertically mounted and side-firing, so they need to be soldered carefully to ensure they fit into the cluster body.  Once they are installed, there is little need for any additional fasteners, although a clamping screw hole is included in the design.

Each side of the keyboard uses an ESP32S2 MCU, and either can function as the USB connection to the PC.
The connections between the keys are 7 conductor JST cables which can be purchased directly on Amazon, and work fine.  If you want to make your own with nice silicone wires you can (see V1 readme), but the off-the-shelf ones do okay.

The halves are built flashed individually with separate Left and Right FW images that must each be built separately with a special command.
Noted here for convenience (assuming your device is on /dev/ttyACM0)
`SIDE=left idf.py -p /dev/ttyACM0 flash`
`SIDE=right idf.py -p /dev/ttyACM0 flash`
"SIDE" is an environment variable passed to the build system.

##### Handrest

The handrest was first molded for my wrist in plasticine clay, and then scanned in using the
[meshroom](https://github.com/alicevision/meshroom) photogrammetry software. Since they were molded
for my wrists specifically, I'm not sure how "one-size-fits-all" they are, or how comfortable they
would be for someone else to use.

##### [BOM](https://github.com/JesusFreke/lalboard/wiki/BOM)

##### [Printing tips & instructions](https://github.com/JesusFreke/lalboard/wiki/Printing-tips-&-instructions)

--------

Note: This is not an officially supported Google product.
