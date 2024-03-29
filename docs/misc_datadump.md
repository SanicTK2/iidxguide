---
title: IIDX LR2 beatoraja differences 
parent: Miscellaneous
permalink: /misc/iidx_lr2_beatoraja_diff
---

# IIDX LR2 beatoraja differences 
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Gauge types

Notes

* T = Total value in BMS
* n = number of notes
* a = a function of total note count in IIDX, but depends on chart. See graph below.
* all units in %

|                      | PG          | GREAT     | GOOD      | BAD   | POOR   | 空P   | Low Life Adj<sup>※0</sup> |
|----------------------|-------------|-----------|-----------|-------|--------|-------|-----------------|
| raja/AEASY           | T/n         | T/n       | T/n/2     | -1.5  | -3     | -0.5  | -               |
| IIDX/AEASY           | a           | a         | a/2       | -1.6  | -4.8   | -1.6  | -               |
|                      |             |           |           |       |        |       |                 |
| raja/EASY            | T/n         | T/n       | T/n/2     | -1.5  | -4.5   | -1    | -               |
| LR2/EASY             | (T/n)x1.2   | (T/n)x1.2 | (T/n)x0.6 | -3.2  | -4.8   | -1.6  | -               |
| IIDX/EASY            | a           | a         | a/2       | -1.6  | -4.8   | -1.6  | -               |
|                      |             |           |           |       |        |       |                 |
| raja/NORMAL          | T/n         | T/n       | T/n/2     | -3    | -6     | -2    | -               |
| LR2/NORMAL           | T/n         | T/n       | T/n/2     | -4    | -6     | -2    | -               |
| IIDX/NORMAL          | a           | a         | a/2       | -2    | -6     | -2    | -               |
|                      |             |           |           |       |        |       |                 |
| raja/HARD            | 0.15 <sup>※2</sup>    | 0.12 <sup>※2</sup>  | 0.03 <sup>※2</sup>   | -5    | -10    | -5    | Yes             |
| LR2/HARD             | 0.1         | 0.1       | 0.05      | -6 <sup>※1</sup> | -10 <sup>※1</sup> | -2 <sup>※1</sup> | Yes          |
| IIDX/HARD            | 0.16        | 0.16      | 0         | -5    | -9     | -5    | Yes             |
|                      |             |           |           |       |        |       |                 |
| raja/EXHARD          | 0.15 <sup>※2</sup>    | 0.06 <sup>※2</sup>  | 0         | -8    | -16    | -8    | No              |
| IIDX/EXHARD          | 0.16        | 0.16      | 0         | -10   | -18    | -10   | No              |
|                      |             |           |           |       |        |       |                 |
| raja/DAN ※3         | 0.15        | 0.12      | 0.06      | -1.5  | -3     | -1.5  | Yes             |
| LR2/DAN              | 0.1         | 0.1       | 0.05      | -2    | -3     | -2    | Yes             |
| IIDX/DAN             | 0.16        | 0.16      | 0.04      | -1.5  | -2.5   | -1.5  | Yes             |
|                      |             |           |           |       |        |       |                 |
| IIDX/EX-DAN          | 0.16        | 0.16      | 0.04      | -3.0  | -5.0   | -3.0  | No              |
| raja/EX-DAN          | 0.15        | 0.12      | 0.03      | -3    | -6     | -3    | No              |
| raja/EXHARD-DAN      | 0.15        | 0.08      | 0         | -5    | -10    | -5    | No              |


These are for 7key and 14key modes; other modes in beatoraja have different values.
* ※0 When the gauge is low, the rate of decrease is lowered; see the two sections below.
* ※1 In LR2, low T and low n leads to increased damage when on hard gauge
* ※2 In beatoraja, exhard and hard gauge increases at a lower rate when total is lower (under 250). If T is under 100 (like ★4Liberte) the gauge never increases.
* ※3 Very important: most DAN courses are tagged with gauge_lr2 to force enable beatoraja to use the LR2 DAN gauge instead.

### IIDX a-value explained

![A graph for A value calculation](/assets/img/gauge/iidx_a_value.png)

### Hard gauge adjustment

<table>
    <tr>
        <th rowspan=2>Remaining Life</th>
        <th colspan=3 align=center>LR2</th>
        <th colspan=3 align=center>IIDX</th>
        <th colspan=3 align=center>beatoraja</th>
    </tr>
    <tr>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
    </tr>
    <tr>
        <td>60+</td>
        <td rowspan=3>-6</td>
        <td rowspan=3>-10</td>
        <td rowspan=3>-2</td>
        <td rowspan=3>-5</td>
        <td rowspan=3>-9</td>
        <td rowspan=3>-5</td>
        <td>-5</td>
        <td>-10</td>
        <td>-5</td>
    </tr>
    <tr>
        <td>50</td>
        <td>-4</td>
        <td>-8</td>
        <td>-4</td>
    </tr>
    <tr>
        <td>40</td>
        <td>-3.5</td>
        <td>-7</td>
        <td>-3.5</td>
    </tr>
    <tr>
        <td>30</td>
        <td rowspan=3>-3.6</td>
        <td rowspan=3>-6</td>
        <td rowspan=3>-1.2</td>
        <td rowspan=3>-2.5</td>
        <td rowspan=3>-4.5</td>
        <td rowspan=3>-2.5</td>
        <td>-3</td>
        <td>-6</td>
        <td>-3</td>
    </tr>
    <tr>
        <td>20</td>
        <td>-2.5</td>
        <td>-5</td>
        <td>-2.5</td>
    </tr>
    <tr>
        <td>10</td>
        <td>-2</td>
        <td>-4</td>
        <td>-2</td>
    </tr>
</table>

* In IIDX and LR2, the gauge decreases at a lower rate when the gauge is at or below 30%
* In beatoraja, this is more of a gradual decrease from 50% and down
* According to the latest release of [LR2oraja](https://github.com/wcko87/lr2oraja/releases/tag/build1099684698), LR2 damage reduction begins at 32% and not at 30%, and you get a stage fail at 2%. This has not been confirmed by other sources but good to keep in mind that there may be slight differences.

### DAN gauge adjustment
<table>
    <tr>
        <th rowspan=2>Remaining Life</th>
        <th colspan=3 align=center>LR2</th>
        <th colspan=3 align=center>IIDX</th>
        <th colspan=3 align=center>beatoraja</th>
    </tr>
    <tr>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
        <th>BD</th>
        <th>PR</th>
        <th>空P</th>
    </tr>
    <tr>
        <td>30+</td>
        <td>-2</td>
        <td>-3</td>
        <td>-2</td>
        <td>-1.5</td>
        <td>-2.5</td>
        <td>-1.5</td>
        <td>-1.5</td>
        <td>-3</td>
        <td>-1.5</td>
    </tr>
    <tr>
        <td>30</td>
        <td rowspan=6>-1.2</td>
        <td rowspan=6>-1.8</td>
        <td rowspan=6>-1.2</td>
        <td rowspan=6>-0.75</td>
        <td rowspan=6>-1.25</td>
        <td rowspan=6>-0.75</td>
        <td>-1.5</td>
        <td>-3</td>
        <td>-1.5</td>
    </tr>
    <tr>
        <td>25</td>
        <td>-1.2</td>
        <td>-2.4</td>
        <td>-1.2</td>
    </tr>
    <tr>
        <td>20</td>
        <td>-1.05</td>
        <td>-2.1</td>
        <td>-1.05</td>
    </tr>
    <tr>
        <td>15</td>
        <td>-0.9</td>
        <td>-1.8</td>
        <td>-0.9</td>
    </tr>
    <tr>
        <td>10</td>
        <td>-0.75</td>
        <td>-1.5</td>
        <td>-0.75</td>
    </tr>
    <tr>
        <td>5</td>
        <td>-0.6</td>
        <td>-1.2</td>
        <td>-0.6</td>
    </tr>
</table>

* Again, most DAN courses are tagged to enable LR2 DAN gauge in beatoraja.

## Timing window

For notes:

|                            | PG     | GR     | GD      | BD        | 空PR      |
|----------------------------|--------|--------|---------|-----------|-----------|
| **IIDX (most charts)**     | ±16.67 | ±33.33 | ±116.67 | ±250      | ?         |
| **LR2 easy**               | ±21    | ±60    | ±120    | ±200      | +1000     |
| LR2 normal                 | ±18    | ±40    | ±100    | ±200      | +1000     |
| LR2 hard                   | ±15    | ±30    | ±60     | ±200      | +1000     |
| LR2 very hard              | ±8     | ±24    | ±40     | ±200      | +1000     |
| raja very easy (125%)      | ±25    | ±75    | ±187    | +275 -350 | +500 -150 |
| **raja easy (100%)**       | ±20    | ±60    | ±150    | +220 -280 | +500 -150 |
| raja normal (75%)          | ±15    | ±45    | ±112    | +165 -210 | +500 -150 |
| raja hard (50%)            | ±10    | ±30    | ±75     | +110 -140 | +500 -150 |
| raja very hard (25%)       | ±5     | ±15    | ±37     | +55 -70   | +500 -150 |

All units in milliseconds. Positive means before the note, negative is after the note.

Notes:

* A POOR happens if a button is not pressed before the LATE BAD window ends.
* Exact numbers for excessive POORs in IIDX are not known.
* In LR2, excessive POORs are only possible before a note; not after.

Detailed rules for beatoraja (based on easy judge):

* Scratch notes: add -10 +10 to each end of note timing window
* Release window of long notes: significantly larger (±120, ±160, ±200, {+220, -280})
* Release window of long scratch notes: add -10 +10 to each end of long note window
* For other judge windows: VERYEASY is 25% wider than EASY, NORMAL is 25% narrower, HARD is 50% narrower, and so on. Integer math is used to scale (discard decimal value).

## Concluding Remarks

If you only care about EX-score, beatoraja is ever so slightly harder than LR2, since its PGREAT window is 2ms narrower while GREAT window is the same.

Excessive POORs work differently in LR2 and beatoraja, which can make a notable impact on life gauge.

If you are playing BMS DAN courses, the difference between LR2 and beatoraja is very minor, since the gauge calculation will follow LR2 algorithm in both cases. It's difficult to make a 1:1 comparison, however; while beatoraja has a wider GOOD window, but excessive-poor calculation is stricter.

If you are playing difficulty tables, your experience will differ in beatoraja vs. LR2, since difficulty tables are rated using LR2 algorithm. Tables are usually rated on easy or normal gauge of LR2. Even if you ignore the differences in timing, no direct comparison can be made between LR2 groove gauge and beatoraja groove gauge, since their calculation methods are different. On survival gauges though, beatoraja tends to be easier than LR2 due to the penalty fall off in the lower part of the gauge.

If you like to use LR2 timing and gauge for everything, check out [LR2oraja](https://github.com/wcko87/lr2oraja/).

## References

[https://lntakeshi.hateblo.jp/entry/2017/05/19/002127](https://lntakeshi.hateblo.jp/entry/2017/05/19/002127)

[https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/GaugeProperty.java](https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/GaugeProperty.java)

[https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/GrooveGauge.java](https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/GrooveGauge.java)

[https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/JudgeProperty.java](https://github.com/exch-bms2/beatoraja/blob/master/src/bms/player/beatoraja/play/JudgeProperty.java)

[https://ch.nicovideo.jp/mirai_s_bemani_blog/blomaga/ar1389382](https://ch.nicovideo.jp/mirai_s_bemani_blog/blomaga/ar1389382)

[https://twitter.com/n13092s/status/908795911286878208](https://twitter.com/n13092s/status/908795911286878208)

[http://stairway.sakura.ne.jp/bms/delay.htm#input](http://stairway.sakura.ne.jp/bms/delay.htm#input)

[https://zenius-i-vanisher.com/v5.2/viewthread.php?threadid=5233](https://zenius-i-vanisher.com/v5.2/viewthread.php?threadid=5233)

[https://hitkey.nekokan.dyndns.info/diary1501.php#D150119](https://hitkey.nekokan.dyndns.info/diary1501.php#D150119)
