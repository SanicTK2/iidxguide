---
title: Running beatmania IIDX infinitas (2020) with ASIO audio mode
parent: Miscellaneous
nav_order: 2
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

# Prerequisite hardware

ASIO-compatible hardware. While Asus Xonar AE is the only one that is officially supported by the game (as seen on ARESPEAR line of Konami gaming PCs -- also on Lightning arcade cabs), other ASIO capable audio devices may work. Check [this page](https://github.com/darekasan/inf_launch_ext/blob/master/asio.md) for compatibility reports from users, and how to make registry modifications to "pretend" to the game that you have the Asus Xonar AE sound card. YMMV of course!!

Personally, I have only tested on Asus Xonar AE with the latest official drivers. This audio card is recognized by the game without any need for registry hacks.

## Warning

Before you go out and buy a sound card, be mindful that -

* ASIO makes very little perceivable difference in rhythm games that can already use WASAPI
* Many arcade games (cough) and old games aren't usually happy about anything BUT on-board sound card

so think twice before you drop a lot of money on one.

# Step by step

1. Launch PowerShell as administrator.
1. Run ```Set-ExecutionPolicy Bypass``` which allows you to run arbitrary PS scripts.
1. Download the script from https://github.com/darekasan/inf_launch_ext
1. Run the script; pick 3 (copy script file to game directory and set to new script path (recommended))
1. Launch Infinitas using the shortcut; launch the game through the browser as usual.
1. Instead of the game being launched, a PowerShell prompt will appear; pick 3 (ASIO).
    1. Note: if you choose #3, you skip the launcher... which means you skip the update check. You'll want to occasionally run the launcher so that you can download patches.

## On audio settings

The game uses 48kHz sampling rate. When using 44.1kHz, the game occasionally has audio glitches, delayed background music sync, or will have crackling sound - very, very minor though. For whatever reason, the game doesn't automatically switch ASIO to use 48kHz, at least on my Asus sound card. To address this, I manually changed the mode to 48kHz in Asus Sonic Studio app:

![](https://raw.githubusercontent.com/minsang-github/rhythmgame-docs/ee220888bf28701d3d061f103d1afc79d3bcb472/res/asus_samplerate.png)

If you experience glitching, dropped audio, or sync issues in the game, try adjusting the buffer size. The default is 4ms which is the minimum supported by the card; 6ms or 8ms is probably more reasonable (at the cost of very slight audio delay). Right click on the tray icon for Asus Sonic Studio, Open ASIO, and adjust the latency.

![](https://raw.githubusercontent.com/minsang-github/rhythmgame-docs/f27101ed54afe6db7e94a2b5d93a1cb153c4d5d3/res/asus_asio.png)
