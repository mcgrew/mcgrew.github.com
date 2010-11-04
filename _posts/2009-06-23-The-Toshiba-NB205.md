I recently bought my first netbook, the Toshiba NB205. I saw it at the Buy More on display for $399, so as I always do 
with netbooks on display, I tested my typing on the keyboard. Contrary to most netbooks, I could actually type on this 
one relatively easily. So I did some research to see if there were any problems getting Linux to run on it. I found 
nothing, presumably because this was Toshiba's first netbook in the US, and it had just been released. So I looked at 
the specs, saw mostly Intel chipsets, which usually work well in Linux, and decided to buy it.

My first task was to image the drive onto my external HD so I could put it back to the way I bought it if the need 
ever arose. I didn't intend to use the Windows XP that was on it, but I wanted to have an image "just in case". This 
turned out to be a good move, which I'll explain later.

I went with Ubuntu Netbook Remix for the laptop, because Ubuntu usually works well for me and it seemed like the 
logical option. Upon loading the image onto my thumb drive, I noticed the wireless didn't work. lspci revealed to me 
that it had an Atheros AR9285 wifi chipset, not Intel as I had expected. Luckily Atheros decided to release an open 
source driver for this chip, but it was in the 2.6.29 kernel, not the 2.6.28 which was on the live image. I found that 
I would need to install linux-backports-modules-jaunty after install to get it working - no problem.

So I installed Ubuntu on the laptop, wiping XP. I ran apt-get install linux-backports-modules-jaunty, rebooted, and 
presto, it detected my wireless card. All was well, or so I thought. sudo iwlist wlan0 scan revealed no scan results, 
but I was 2 feet from my router (not to mention the 20 other networks I usually pick up in my neighboorhood). I 
noticed the wifi light on the front of the machine was not lit. The card must not be enabled. After scouring the 
internet for several hours and looking thoroughly through the bios, I found no way to enable the wireless card. I 
remembered a friend of mine once had a similar issue with a laptop - no way to enable the card in Linux if it had been 
turned off in Windows.

So I reconnected my external HD to the laptop and booted from the live usb image of Ubuntu and proceeded to write the 
drive image back onto the internal hard drive and left it for the night (It took a while over USB, the netbook didn't 
have any eSATA or firewire ports).

The next morning I found the image had been written back to the drive, so I rebooted and proceeded to boot Windows 
once to try to enable the wireless card. I tried pressing Fn+F8 on the setup screen, but nothing happened, so I 
continued with the initial setup. After Windows booted fully, I pressed it again and finally, the wifi light lit up. I 
shut down Windows and booted from the thumb drive again.

When it booted up, I noticed that the wifi light was still on. Good. This time I opted to leave Windows XP, with as 
little space as was practical, and set up dual boot, just in case I needed it again. After installing Linux again and 
installing the backports, I tried a scan again and my network showed up. The Gnome network manager worked well with my 
wpa encryption and all was well for the moment.

After using the laptop for about a day I noticed I hadn't heard any sounds, so I tried to play an mp3 file. Sure enough
, nothing. I checked all the mixer settings and played with them a bit, but nothing seemed to work. So again here I go 
scouring the internet for solutions. After a few hours of searching I finally came across the alsa-project bug tracker 
and found bug #4575, which seemed to be the same problem I have. Same sound chip (Intel 82801G with Realtek ALC272) 
and no sound, so I'm assuming this is an alsa bug. For now I guess I'll do without sound, but I hope it's fixed soon.

Overall this netbook is really nice. The keyboard still feels really good and is easy to type on. It also has great 
battery life, about 6-7 hours with wifi on. UNR runs very well on it and I haven't had any problems with suspend-
resume yet, which is crucial for a netbook. It's more than I can say with my Dell Latitude with Kubuntu, where 
resuming is about a 50/50 proposition. I beleive I'll be very happy with this netbook once the sound is working, but 
for now I'm satisfied with my purchase.
