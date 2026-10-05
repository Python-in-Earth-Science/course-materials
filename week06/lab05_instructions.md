# Lab 05: Loops on Nashville's Climate (Temperature Edition)

> **Version 2**. New since version 1: a commit-and=push checkpoint after Exercise 3.

**EES 3350/5350 · Python in Earth Science · Monday, October 2026**</p>
**Due:** Wednesday, October 07, at 11:59pm, submitted by pushing to your assignment repo.

This is practice, not new material. It's the same weather station as the Lab 4 worksheet, but now with **temperature** and **extreme days**, stored in a **dictionary of dictionaries**. You'll write every loop from scratch, with no blanks to fill in. Plan for about 30 minutes in lab.

## Getting started

1. In your ExploreHub, open your Lab 05 repo folder (`~/assignments/ees-3350-5350-lab-05-USERNAME`).
2. Create a new notebook there and rename it `lab05_LastName.ipynb`.
3. Do all of your work in `lab05_lastName.ipynb`. **Don't edit this instructions file.**
4. For every exercise, add a Markdown cell with the exercise number (feel free to copy the exercise itself into a Markdown cell if that is helpful), then a code cell with your code.

Need help? use the [cheat sheets](https://python-in-earth-science.github.io/cheatsheets.html) on the class website.

## Setup: Nashville climate normals

Copy this into the first code cell of your notebook and run it.

```python
climate = {
    'January':   {'tmax': 49.1, 'tmin': 30.1, 'tmean': 39.6, 'precip': 4.02, 'freeze_days': 18.8, 'hot_days': 0.0},
    'February':  {'tmax': 53.8, 'tmin': 33.0, 'tmean': 43.4, 'precip': 4.47, 'freeze_days': 14.2, 'hot_days': 0.0},
    'March':     {'tmax': 62.7, 'tmin': 40.2, 'tmean': 51.5, 'precip': 4.52, 'freeze_days': 7.4,  'hot_days': 0.0},
    'April':     {'tmax': 72.6, 'tmin': 48.9, 'tmean': 60.8, 'precip': 4.72, 'freeze_days': 0.9,  'hot_days': 0.1},
    'May':       {'tmax': 80.4, 'tmin': 58.3, 'tmean': 69.3, 'precip': 5.02, 'freeze_days': 0.0,  'hot_days': 2.0},
    'June':      {'tmax': 87.7, 'tmin': 66.4, 'tmean': 77.1, 'precip': 4.36, 'freeze_days': 0.0,  'hot_days': 10.8},
    'July':      {'tmax': 90.9, 'tmin': 70.5, 'tmean': 80.7, 'precip': 4.16, 'freeze_days': 0.0,  'hot_days': 18.2},
    'August':    {'tmax': 90.4, 'tmin': 69.0, 'tmean': 79.7, 'precip': 3.79, 'freeze_days': 0.0,  'hot_days': 15.9},
    'September': {'tmax': 84.4, 'tmin': 61.8, 'tmean': 73.1, 'precip': 3.80, 'freeze_days': 0.0,  'hot_days': 6.8},
    'October':   {'tmax': 73.5, 'tmin': 49.9, 'tmean': 61.7, 'precip': 3.36, 'freeze_days': 0.7,  'hot_days': 0.4},
    'November':  {'tmax': 61.4, 'tmin': 39.2, 'tmean': 50.3, 'precip': 3.86, 'freeze_days': 8.4,  'hot_days': 0.0},
    'December':  {'tmax': 52.2, 'tmin': 33.3, 'tmean': 42.7, 'precip': 4.43, 'freeze_days': 15.8, 'hot_days': 0.0},
}
months = list(climate.keys())
seasons = {'winter': ['December', 'January', 'February'],
           'spring': ['March', 'April', 'May'],
           'summer': ['June', 'July', 'August'],
           'fall':   ['September', 'October', 'November']}
```

`climate` is a **dictionary of dictionaries**: each key is a month and each value is another dictionary of that month's numbers. To get one number, use two keys in a row: `climate['July']['tmax']` is July's average high.

| Key| What it is|
|--|--|
|`tmax`| average daily high temperature (°F)|
|`tmin`| average daily low temperature (°F)|
|`tmean`| average daily temperature (°F)|
|`precip`|average total precipitation for the month (in)|
|`freeze_days`|average number of days with a low of 32°F or colder|
|`hot_days`|average number of days with a high of 90°F or hotter|

*Data: NOAA National Centers for Environmental Information (NCEI), U.S. Climate Normals 1991–2020, Station USW00013897 (Nashville Intl AP, TN), [Summary of Monthly Normals](https://www.ncei.noaa.gov/access/services/data/v1?dataset=normals-monthly-1991-2020&format=pdf&stations=USW00013897). All values are 30-year averages, which is why day counts can be fractions.*


## Exercises

For Exercises 3-5, **write your plan as comments first**, then write the code underneath.

<div class="alert alert-info">

### Exercise 1: Getting around a dictionary of dictionaries

1. Pring July's average high, using two keys.
2. Loop over `climate.items()` and print one line per month with its average high and average low, like `July: high 90.9 F, low 70.5 F`
    
</div>


<div class="alert alert-info">

### Exercise 2

The difference between a month's average high and average low is its **daily temperature range**

1. Build a dictionary called `temp_range` that maps each month to its range.
2. Using the best-so-far pattern (no `max()` or `min()`), find the month with the biggest range and the month with the **smallest**. Pring both, rounded to one decimal place.

</div>

<div class="alert alert-warning">

**Question 1:** Look at the two months closest to the top. How close is this race? In a Markdown cell, say what that suggests about checking answers carefully.
    
</div>

<div class="alet alert-info">

### Exercise 3: The freeze season

Midsummer has no freezing nights, so start every seartch in **July** (position 6 in `months`).

1. Walk **forward** from July and printt the first month with any freezing nights. Stop the loop with `break` once you find it.
2. Walk **backward** from July and print the first month you reach with any freezing nights, again, with `break`.

</div>

<details>
<summary style="color:green;"><strong>Hint.</strong></summary>
    
`range(6,12)` counts forward 6, 7, 8, ..., 11. `range(6, -1, -1)` counts **backward** 6, 5, ..., 0. Remember that the third number is the step. Use the position to look up the month name, `months[i]`, then that month's numbers in `climate`</details>

<div class="alert alert-warning">

**Question 2:** Based on your two answers, which months of the year have no freezing nights at all, on average?
    
</div>

<div class="alert alert-danger">
    
### CHECKPOINT: commit and push

Save your notebook, then:
```
git add lab05_LastName.ipynb
git commit -m "Finish Exercises 1-3"
git push
```
Committing as you go means your work is saved on GitHub even if you don't finish today. I'll  be looking for a history of these exact three commands in your repository.

</div>


<div class="alert alert-info">

### Exercise 4: Extreme days by season

Using a nested loop over `seasons`, add up each season's `freeze_days` and `hot_days`. Store the results in a **new dictiona* called `season_counts`, shaped like `{'winter': {'freeze_days': ... 'hot_days': ...}, ...}`. Print one line per season.

</div>

<details>
<summary style="color:green;"><strong>Sanity check.</strong></summary>

Add up all four seasons. NOAA reports 66.2 freezing nights and 54.2 days at 90°F or more for the whole year.
</details>


<div class="alert alert-warning">

**Question 3:** Compare spring and fall. Which one has more freezing nights, and which one has more hot days? Is this what you expected?
    
</div>


<div class="alert alert-info">

### Exercise 5: Warm and wet, cold and wet

Build two lists of month names:
- `warm_and_wet`: months with an average temperature of **at least 60°F** *and* at least **4.0 in** of precipitation
- `cold_and_wet`: months with an averatge temperature **below 45°F** *and* at least **4.0 in** of precipitation

Use one loop over `climate.items()`, and print both lists.
    
</div>

# End for Undergraduate Students
Grad students should continue to exercise below

## Submitting
Save your notebook (ctrl + S), then in the terminal from your Lab 05 repo folder:
```
git status
git add lab05_LastName.ipynb
git commit -m "[insert a message here]"
git push
```
Add your notebook by name. Check your repo's page on GitHub to make sure your commit arrived. You can push as many times as you like before the deadline; your most recent push is what counts.

# <span style="color: blue;"> For Graduate Students Only  <span>
<div style="background-color:#e8daef; border:1px solid #d2b4de; color:#6c3483; padding:10px; border-radius:4px; margin-bottom:20px;">

Build `climate_c`, a new dictionary of dictionaries with the same months and keys as `climate`, but every **temperature** converted to Celcius, $°C = (°F - 32) \frac{5}{9}$, rounded to one decimal place. Every other value should be copied over unchanged.

<details>
<summary style="color:green;"><strong>Hint.</strong></summary>

Use a nested loop: the outer loop over months, the inner loop over each month's `.items()`. Use `continue` to handle the keys that aren't temperatures. Print January and July to check your work.
</details>

</div>

## Submitting
Save your notebook (ctrl + S), then in the terminal from your Lab 05 repo folder:
```
git status
git add lab05_LastName.ipynb
git commit -m "[insert a message here]"
git push
```
