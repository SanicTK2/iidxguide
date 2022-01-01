---
title: Infinitas with ASIO
parent: Miscellaneous
permalink: /misc/infinitas_asio
---

# Running beatmania IIDX infinitas (2020) with ASIO audio mode
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Prerequisite hardware

ASIO-compatible audio output device. While Asus Xonar AE is the only one that is officially supported by the game (as seen on ARESPEAR line of Konami gaming PCs -- also on Lightning arcade cabs), other ASIO capable audio devices may or may not work.

## **Warning**

Before you go out and buy a sound card, be mindful that -

* ASIO makes very little perceivable difference in rhythm games that can already use WASAPI in exclusive mode
* Many rhythm games and old games aren't usually happy about anything BUT on-board sound card
* On Asus Xonar AE, you might run into some minor issues like latency being higher than expected, or sound occasionally cutting out. It is assumed that on Lightning Cab and/or ARESPEAR gaming PCs, they are using a specific revision of the sound card with (potentially) custom drivers.
* Other ASIO-compatible sound cards may or may not work, as described above. Check [this page](https://github.com/darekasan/inf_launch_ext/blob/master/asio.md) for compatibility reports from users.

Also: as of November 2021, Asus Xonar AE drivers do NOT work in Windows 11, and this is confirmed by Asus. [Check with Asus support for updates](https://www.asus.com/us/Motherboards-Components/Sound-Cards/Gaming/Xonar-AE/HelpDesk_knowledge/).

so think twice before you drop a lot of money on one.

## Step by step

1. Launch PowerShell as administrator.
1. Run ```Set-ExecutionPolicy Bypass``` which allows you to run arbitrary PS scripts.
1. Download the script from [https://github.com/darekasan/inf_launch_ext](https://github.com/darekasan/inf_launch_ext)
1. Run the script as administrator; pick 3 (copy script file to game directory and set to new script path (recommended))
1. Launch Infinitas using the shortcut; launch the game through the browser as usual.
1. Instead of the game being launched, a PowerShell prompt will appear; pick 3 (ASIO).
    1. Note: if you choose #3, you skip the launcher... which means you skip the update check. You'll want to occasionally run the launcher so that you can download patches.
1. (If you have an ASIO-compatible sound card that isn't Asus Xonar AE)
    1. Follow [instructions here](https://github.com/darekasan/inf_launch_ext/blob/master/asio.md#xonar-ae%E4%BB%A5%E5%A4%96) to modify the registry. You'll need to manually create a copy of your ASIO device's key under HKEY_LOCAL_MACHINE\SOFTWARE\ASIO and name it as "XONAR SOUND CARD(64)", keeping the original CLSID.

## On audio settings

If you experience glitching, dropped audio, or sync issues in the game, try adjusting the buffer size. The default is 4ms which is the minimum supported by the card; 6ms or 8ms is probably more reasonable (at the cost of very slight audio delay). Right click on the tray icon for Asus Sonic Studio, Open ASIO, and adjust the latency.

![asus asio buffer size option](https://raw.githubusercontent.com/minsang-github/rhythmgame-docs/f27101ed54afe6db7e94a2b5d93a1cb153c4d5d3/res/asus_asio.png)
