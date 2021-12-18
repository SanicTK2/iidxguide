---
title: Score Calculation
parent: Compendium
permalink: /compendium/exscore
---

# Score Calculation
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Judgement

The following judgement is possible for each note:

* PGREAT (perfect great)
* GREAT
* GOOD
* BAD
* POOR

Each charge note (same for hell charge note) count as two notes - one in the beginning, one at the end. Using LEGACY option turns that into just one in the beginning.

For timing windows, [refer to this page](/misc/iidx_lr2_beatoraja_diff).

### Excessive POOR (空POOR)

Excessive POOR is a POOR that happens when you press a button again, right after the note was already processed, or when you press the button slightly earlier than the beginning of BAD window. See [this page](/compendium/gauges_and_timing) for more details.

To calculate:

```
空POOR = MISS_COUNT - COMBO_BREAK
```

## EX-SCORE

EX score is the only scoring system in the game. Its rules are simple:

* PGREAT gives you 2 points.
* GREAT gives you 1 point.

## DJ LEVEL

DJ level on the result screen is calculated using EX-SCORE, compared to the theoretical maximum score possible for the chart. If you take the ratio (EX_SCORE / MAX), you can see what grade you will get:

| Grade | EX score ratio     | Percentage |
| ----: | :----------------- | :--------- |
|  AAA  | 8/9 or above       | >= 88.89%  |
|  AA   | 7/9 or above       | >= 77.78%  |
|  A    | 6/9 or above       | >= 66.67%  |
|  B    | 5/9 or above       | >= 55.56%  |
|  C    | 4/9 or above       | >= 44.44%  |
|  D    | 3/9 or above       | >= 33.33%  |
|  E    | 2/9 or above       | >= 22.22%  |
|  F    | Under 2/9          |  < 22.22%  |

### What is "max-" ?

You will often hear people talk about scores relative to a grade, for example, "AA-3" to mean 3 points under the AA requirement, or "AAA+10" to mean 10 points above the AAA requirement.

If you get 8.5/9 (**94.44%**) or higher, it is considered a MAX- score. While MAX- is not a rating displayed on the result screen, it does show up in other parts of the interface, and you will hear about players refer to scores in this way.

Getting a MAX (sometimes MAX+0, MAX-0, or 理論値) refer to obtaining the theoretical maximum value of 100%, PGREAT on every note.

---

To put things in to perspective, for AC scores, as of November 2021:

* All SP top scores are in MAX- range, except Mare Nectaris which is in the AAA+ range. Two songs (Mosaic and GRID KNIGHT L) have been MAX'd.
* All DP top scores have AAA or above, except Mare Nectaris.
