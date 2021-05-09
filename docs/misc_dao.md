---
title: Troubleshooting DJ DAO beatmania IIDX controllers
parent: Miscellaneous
nav_order: 0
---

# Troubleshooting DJ DAO beatmania IIDX controllers
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Before we begin: PCB variants

Please note that this guide is for older Dao IIDX controllers - FPS, FP7, PEE, RES, RED. If you have a Phoenixwan - please contact Gamo2 support instead, they have a lot of undocumented features and firmware updates not available to the public that resolves various issues.

Dao produced multiple generations of PCB (logic board inside your controller). Largely, there are two groups. Open up the back plate of your controller (it's magnetic - pull on the rubber feet) and take a look at the PCB...
 
A. New "2014" version PCBs. These are black in color and has this written: SS001 V0.x or SS001 V1.x (where x is a number). Has upgradable firmware.
 
B. Older PCBs. These are green in color, and lacks many features. This is NOT covered here. I recommend that you get a new PCB if you're having trouble with these - see bottom of this page.

This FAQ only covers the newer ones mentioned in A.

## Key combinations and modes

* Hold start+select+1 for a second to switch input modes. If button 2 blinks after doing this, you're in Infinitas mode. If button 4 blinks, you're in LR2 mode. If button 6 blinks, you're in HID-light mode.
    * Use Infinitas mode for e-amusement cloud Infinitas.
    * Use LR2 mode for LR2 (but not beatoraja)
    * Use HID-light for games requiring tools, and beatoraja.
* Hold start+select+2 for a second to turn off all LEDs.
* Hold start+select+7 to enable multifunction mode. When this is enabled, you can single tap select to emulate button 10 input, double tap to emulate button 11 input, and triple tap to emulate 10 and 11. This is useful for accessing E2 and E3 buttons in Infinitas, or VEFCT and Effect buttons in tools.
* Unlike some controllers, these settings are saved, even when you unplug the controller.

Original source is [this image](https://www.gamo2.com/en/images/companies/1/ss001.png?1479545558251).

## Troubleshooting your DAO, follow in order without skipping steps:
 
0. Have you ever installed a driver to make PS3/4 DualShock controllers work on your PC? If so, uninstall them right now. They tend to cause trouble with other controllers. Also please please please turn off joy2key if you have it running.
 
1. Plug in BOTH red & black USB cables into USB ports in the rear of your computer. You must have both of them plugged in at all times in order for your controller to function properly. If you don't have enough ports on your computer, you could use a POWERED USB hub. (If your USB hub plugs into the wall socket, it's powered. If it doesn't, you have the wrong hub.)
 
2. Open Start Menu and search for "Set up USB game controllers". Check that your controller shows up there. If nothing is there, try different USB ports, check your USB cables, or maybe your PCB is completely busted.
 
3. Make sure you're on the latest firmware. If you just purchased the controller, it's likely that it came with an ancient firmware - Dao does NOT ship with newest firmware installed! See https://www.gamo2.com/en/firmware/ for instructions. v1.23 is the latest as of this writing. Some people swear by v1.22, that's fine too. Check their FAQ for details.
 
4. Now that you upgraded the firmware, try switching game modes. See the link from #3 and look for "how to switch mode". Make sure you're in the right mode. A lot of people get stuck in the wrong mode and get confused why the turntables aren't working. Once you're in the right mode, you'll need to remap your input again in tools.
 
5. Open up USB game controllers control panel again. You should see a PS3Controller. Check that all your buttons work & spinning the analog causes the analog stick to move. If turntable is wonky, try flashing the new firmware again and see if that fixes it. If it's still weird, open up the controller and check the sensors are not out place & cables are all plugged in. It should look like this when TT is turned: https://youtu.be/6g771LxV6w8
 
6. Launch tools config. In Buttons section, map your buttons. Make sure that P1 TT +, P1 TT -, P1 TT +/-, P2 TT +, P2 TT -, P2 TT +/- are all BLANK. Do not use any of these for your controller.
 
7. Analogs. This is where you set up your turntable. Pick PS3Controller from the drop down. Pick X or Y from Control -- spin your turntable and see if it works as you expect. If the turntables spin the wrong way, you're in Infinitas mode. If none of them make the circle turn, you might be in LR2 mode.
 
## Additional notes on troubleshooting hardware issues

* Opening it up: the bottom panel is attached using magnets. No screws required! Grab the rubber feet and pull it off.

* Turntable making "grinding" noise - the saw-tooth disc inside your controller is touching the sensors. Take the TT center sticker off & adjust the screws. And by "adjust" try both loosening & tightening it, making sure that the disc does not touch the sensors and instead float between them.

* Are you having trouble disconnecting the wires from switches? The spade connector on quick-release *may* have a small lever that releases the grip. Not all connectors have it, keep in mind.

* Turntable getting stuck when rotating around a certain point - the silver ring around the platter can end up slightly off center which causes the physical turntable to rub up against it. To fix it you just have to firmly push on the silver ring to push it in a direction and center it, no need to open up the controller or anything.

* Last resort: get a replacement PCB... If all fails, perhaps you need a new PCB. Get a replacement from Dao ($18.20 USD plus expensive shipping), or get an arcin ($50 USD, incl shipping), or look into alternatives, such as an Arduino. Don't forget to check various sell/buy marketplaces for used items.

## FAQ:
Q: Do I need joy2key?

A: No, do not use joy2key unless you're trying to play a game that doesn't have gamepad support. Don't use joy2key for IIDX or LR2.

Q: My turntable occasionally stops moving if I change directions.

A: See "Additional notes on troubleshooting hardware issues"
 
Q: Turntable just drops really fast scratches // turntable "deadzone" is too large

A: Buy an arcin or use other PCBs. Dao PCBs aren't great for fast scratches. This happens more often on full-size turntables (PEE, RES, RED) as Dao's firmware is calibrated for smaller turntables.
 
Q: AHH! Did I brick my controller when flashing the firmware?

A: Check the FAQ at the bottom of the link in #3 ("How to deal with upgrade fail"). You can recover it.

Q: My turntable sticker keeps falling off!

A: Use [Scotch Brand x 0.5-inch, Clear, 72 Scotch Restickable Mini Tabs, 0.5"x0.5", (R103)](https://www.amazon.com/gp/product/B004NNEI94). You'll need several of them for a good seal, but it comes in a pack of 72 for about $3.
