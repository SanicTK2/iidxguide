---
title: Gauge Calculation and Timing Windows
parent: Compendium
permalink: /compendium/gauges_and_timing
---

# Life Gauge Calculation and Timing Windows in beatmania IIDX
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

* a = a function of total note count in IIDX -- see below
* all units in %

|         | PG     | GREAT | GOOD  | BAD   | POOR   | 空P   | Low Life Adj† |
|---------|--------|-------|-------|-------|--------|-------|---------------|
| A.EASY  | a      | a     | a/2   | -3.2  | -4.8   | -1.6  | -             |
| EASY    | a      | a     | a/2   | -1.6  | -4.8   | -1.6  | -             |
| NORMAL  | a      | a     | a/2   | -2    | -6     | -2    | -             |
| HARD    | 0.16   | 0.16  | 0     | -5    | -9     | -5    | Yes           |
| EXHARD  | 0.16   | 0.16  | 0     | -10   | -18    | -10   | No            |
| DAN     | 0.16   | 0.16  | 0.04  | -1.5  | -2.5   | -1.5  | Yes           |
| EX-DAN  | 0.16   | 0.16  | 0.04  | -3.0  | -5.0   | -3.0  | No            |

† Low Life Adjustment: when the gauge is at or below 30%, the rate of decrease caused by BAD and POORs are halved. For example, when playing on HARD gauge, if you are at 28% life and get a POOR, you lose 4.5% instead of 9%.

### IIDX a-value explained

![Graph explaining what the a-value means in IIDX](/assets/img/gauge/iidx_a_value.png)

## Timing window

| JUDGE  | Window (ms) |
|--------|-------------|
| PGREAT | ±16.67      |
| GREAT  | ±33.33      |
| GOOD   | ±116.67     |
| BAD    | ±250        |
| POOR   | ?           |

All units in milliseconds. Positive means before the note, negative is after the note.

In IIDX, it is possible for some charts to have more restrictive timing windows; the most notable one is GAMBOL.

It is a myth that the timing windows are asymmetric; the timing windows themselves are the same duration before and after the precise timing. It is not larger on one side.

That being said, there are various factors that may make it seem like the entire timing window slightly shifted towards the "fast" side (frame quantization, input capture window, etc) - but it is at most 1 frame difference.

## Further reading

[https://zenius-i-vanisher.com/v5.2/viewthread.php?threadid=5233](https://zenius-i-vanisher.com/v5.2/viewthread.php?threadid=5233)