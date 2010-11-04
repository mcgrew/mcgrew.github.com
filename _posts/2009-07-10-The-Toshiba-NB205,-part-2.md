So it seems there has at least been a partial solution to the sound problem. Putting the 
line:

`options snd-hda-intel model=asus-mode4`

into `/etc/modprobe.d/alsa-base.conf` gives sound through the headphones, although the master volume control doesn't work
, and there is no sound from the built-in speaker. I am satisfied for now, and I'll post any solutions that make this 
work better. Thanks to yorkzhang for the solution to this and for finding me on github to give it to me.
