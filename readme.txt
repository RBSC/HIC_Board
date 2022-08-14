--------------------------------------------------------------------------------
HIC Board version 1.0
Copyright (c) 2021-2022 RBSC
Last updated: 14.08.2022
--------------------------------------------------------------------------------

About
-----

It's a well-known fact that certain MSX2/2+ computers have a so-called "HIC Board" - the special "Hybrid IC" daughterboard that is
mounted onto the MSX computer's motherboard and provides certain functionality. This functionality is as follows:

 - converts RGBS signals to composite video
 - pre-amplifies and buffers audio
 - mutes audio at startup and on pause to prevent clicks
 - mixes all audio inputs
 - amplifies and buffers the cassette interface signals
 - buffers cassette interface's relay operations

This board is known to be installed in the following MSX computers:

 - Sony HB-F1II
 - Sony HB-F1XD
 - Sony HB-F1XV
 - Sony HB-F1XDJ
 - Sony HB-F1XDmkII
 - Panasonic FS-A1
 - Panasonic FS-A1mkII
 - Panasonic FS-A1F
 - Kawai KMC-5000 (Panasonic FS-A1F OEM)

Normally, the board works just fine, but there's a problem with 3 electrolytic capacitors - they leak and damage the board,
sometimes beyond repair. Fixing the leaked boards is difficult as some components can separate from the corroded solder pads,
some tracks can be corroded under the CXA chip resulting in the board's malfunction.

The original HIC board's schematics and layout can be found here:
http://elec-junker-p2.blog.jp/MITSUMI%20EMC-NX0039_REV02_PU.pdf


HIC Board's Redesign
--------------------

Taking into account all the above listed problems, it was decided to clone the HIC board and at the same time add the following
improvements:

 - use a better and commonly available encoder chip CXA2075
 - add s-video output capability
 - try to get rid of the original 4069UBF chip's dependency
 - make the HIC board detachable

It was also desired to get rid of the 2 special components: IMN10 and FMW1, but they appeared to be still available for purchasing,
so they remained on the redesigned board.

During the redesign there appeared a few problems. The 4069UBF chip from Toshiba was used by the original engineers as an amplifier,
so the board's audio and cassette interface operations were dependent on certain features of that chip. When trying to replace this
chip with similar ones, for example 74LS04 or 74HCT04, the audio functionality was crippled. The only possible replacement appears
to be 74HC04 with 68pF capacitor added between pins 3 and 7 (GND). See the "74hc04_fix.jpg" image in the Pics folder.

The optional resistor R35 should not be installed unless the cassette input circuit doesn't work as desired.


Where to buy parts
------------------

At the time of this readme's creation the parts are available from the following sellers:

 - pin headers (male and female): https://www.aliexpress.com/item/4001122376295.html
 - CXA2075 encoder: https://www.aliexpress.com/item/33020885081.html
 - 4069UBF: https://www.aliexpress.com/item/1005002494421415.html
 - 68uH inductor: https://www.aliexpress.com/item/1005002963165525.html
 - LMV358M amplifier: https://www.aliexpress.com/item/4001116443945.html
 - 68pF trim capacitor: https://www.aliexpress.com/item/4000222152928.html
 - 2SA1037 transistor: https://www.aliexpress.com/item/1005002503421569.html
 - 2SC2411 transistor: https://www.aliexpress.com/item/1005004568437670.html
 - IMN10: https://www.aliexpress.com/item/1005004322498640.html
 - FMW1: https://www.ebay.com/itm/325038640119 or from Wierzbowsky (RBSC)

The resistors and capacitors 0805 and 1210 form factor can be ordered from any reasonable seller. The boards can be ordered from the
JLCPCB.COM factory.


IMPORTANT!
----------

The board hasn't been tested on all available MSX2/MSX2+ computers that are listed above. So far, the board was proved to be working
well on Panasonic A1 series computers. There's still no feedback from people who bought the HIC board kits for other computers. As
a result, the project's status is WIP (work in progress).

The RBSC provides all the files and information for free, without any liability (see the disclaimer.txt file). The provided information,
software or hardware must not be used for commercial purposes unless permitted by the RBSC. Producing a small amount of bare boards for
personal projects and selling the rest of the batch is allowed without the permission of RBSC.

When the sources of the tools are used to create alternative projects, please always mention the original source and the copyright!


Contact information
-------------------

The members of RBSC group Tnt23, Wierzbowsky, Pyhesty, Ptero, GreyWolf, SuperMax and DJS3000 can be contacted via the group's e-mail
address:

info@rbsc.su

The group's coordinator could be reached via this e-mail address:

admin@rbsc.su

The group's website can be found here:

https://rbsc.su/
https://rbsc.su/ru

The RBSC's hardware repository can be found here:

https://github.com/rbsc

The RBSC's 3D model repository can be found here:

https://www.thingiverse.com/groups/rbsc/things

-= ! MSX FOREVER ! =-
