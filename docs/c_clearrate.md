---
title: Clear Rate in Class Mode
parent: Compendium
permalink: /compendium/dan_clear_rate
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
    if y >= 0:
        y /= 2

    return 40 * progress / note_count + median([60 * (y + 50) / 100, 0, 60])

cr = clear_rate(637, 170, 38, 28, 88, 980)
print(cr)
```

Here is a live JavaScript version:

<div class="form_container">

<label>Total note count:
    <input class="form_input" type="number" min="0" value="0" id="tc">
</label>

<label>PGREAT:
    <input class="form_input" type="number" min="0" value="0" id="pg">
</label>

<label>GREAT:
    <input class="form_input" type="number" min="0" value="0" id="gr">
</label>

<label>GOOD:
    <input class="form_input" type="number" min="0" value="0" id="gd">
</label>

<label>BAD:
    <input class="form_input" type="number" min="0" value="0" id="bd">
</label>

<label>POOR:
    <input class="form_input" type="number" min="0" value="0" id="pr">
</label>

<button id="calculate">Calculate</button>

<div style="font-size: large; font-weight: bold">
    Clear rate = <span id="dan_result">0</span> %.
</div>

</div>

<script
    src="https://code.jquery.com/jquery-3.6.0.slim.min.js"
    integrity="sha256-u7e5khyithlIdTpu22PHhENmPcRdFiHRjhAuHcs05RI="
    crossorigin="anonymous"></script>

<script
    src="https://cdnjs.cloudflare.com/ajax/libs/mathjs/9.5.1/math.min.js"
    integrity="sha512-7+fUzDKxopLeVKiXTdoQQZBl6Zh9Bbl/NrZoowiddStpj7GXTUCM+LOPay4Wzxz14HazsoSsO96UFvvZqAH5rw==" crossorigin="anonymous"
    referrerpolicy="no-referrer"></script>

<script>
    $(document).ready(function() {
        
        function clear_rate(pgreat, great, good, bad, poor, note_count) {
            var progress = math.min(pgreat + great + good + bad + poor, note_count);
            if ((note_count <= 0) || (progress <= 0)) {
                return 0;
            }

            var x = 8 * (pgreat + great) + 2 * good - (68 * bad + 100 * poor);
            var y = 100 * x / (6 * note_count);
            if (y >= 0) {
                y /= 2;
            }

            var result = 40 * progress / note_count + math.median(60 * (y + 50) / 100, 0, 60);
            return result;
        }

        function update() {
            var tc = parseInt($("#tc").val());
            var pg = parseInt($("#pg").val());
            var gr = parseInt($("#gr").val());
            var gd = parseInt($("#gd").val());
            var bd = parseInt($("#bd").val());
            var pr = parseInt($("#pr").val());
            var cr = clear_rate(pg, gr, gd, bd, pr, tc);
            $("#dan_result").text(math.round(cr, 0));
        }

        $(".form_input").change(update);
        $("#calculate").click(update);
    });
</script>

Bonus fun fact: [it is possible to get a 100% clear rate and fail the class exam.](https://www.youtube.com/watch?v=z-DDlDoCqVM)
