---
title: Clear Rate in Class Mode
parent: Compendium
nav_order: 10
---

# Clear Rate in Class Mode (Dan)

In the result screen of class mode (dan-i-nintei), you are given a two-digit percentage value as the "clear rate". The algorithm for calculating clear rate is as follows (Python code):

```python
from statistics import median 

def clear_rate(pgreat, great, good, bad, poor, note_count):
    progress = min(pgreat + great + good + bad + poor, note_count)
    if note_count <= 0 or progress <= 0:
        return 0

    x = 8 * (pgreat + great) + 2 * good - (68 * bad + 100 * poor)
    y = 100 * x / (6 * note_count)
    if y >=0:
        y /= 2

    return 40 * progress / note_count + median([60 * (y + 50) / 100, 0, 60])

cr = clear_rate(637, 170, 38, 28, 88, 980)
print(cr)
```

Bonus fun fact: [it is possible to get a 100% clear rate and fail the class exam.](https://www.youtube.com/watch?v=z-DDlDoCqVM)
