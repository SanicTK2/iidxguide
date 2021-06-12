---
title: Gauge Options
parent: Compendium
permalink: /compendium/gauge
---

# Gauge Options
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

![gauge options screen](/assets/img/gauge/option_gauge.jpg)

## Normal gauge

Setting the gauge option to "OFF" will use what people usually call the normal gauge.

It starts at 22%; it goes up if you get GOOD or better, and goes down for BAD / POOR. If you end the song with 80% or above, you clear the song.

The rate of increase per note is (usually) relative to the number of total notes. The rate of decrease is fixed.

## Easy Gauge

![easy gauge](/assets/img/gauge/easy.jpg)

Same as normal gauge, except that when you get BAD or POORs, the gauge will **decrease less**. You still need 80% to pass the stage, and the rate of **increase** remains the same.

## Assist Easy Gauge

![assist easy gauge](/assets/img/gauge/a_easy.jpg)

Same as easy gauge, except that you only need 60% to pass the stage.

## Hard Gauge

![hard gauge](/assets/img/gauge/hard.jpg)

This is the "survival" gauge - you start with 100%, and every BAD and POORs will decrease it. GOOD and above will still refill the gauge, although at a fixed rate. Once you hit 0%, you immediately fail out of the song.

About 14 POORs in a row will bring your gauge down from 100% to 0%.

At or below 30% gauge, the rate of decrease for BAD / POORs will halve.

## EX-Hard Gauge

![ex-hard gauge](/assets/img/gauge/exhard.jpg)

Harder version of Hard gauge - each BAD and POORs will greatly decrease the gauge, and failing out of the stage at 0%.

About 6 POORs in a row will bring your gauge down from 100% to 0%.

Unlike hard gauge, there is also no halved decrease rate bonus for 30% and below.

## DAN Gauge

This is not a selectable option in Standard mode, but it is used during Class mode.

You start at 100%, and fail out at 2%. The gauge amount carries over from one stage to the next. It is like hard mode in that there is a halved decrease rate at 30%, but it is much, much more lenient.

About 40 POORs in a row will bring your gauge down from 100% to 0%.

## More details

If you need to know the exact parameters for various gauge types, such as the algorithm used to calculate the increase / decrease, check out [this page](/compendium/gauges_and_timing).
