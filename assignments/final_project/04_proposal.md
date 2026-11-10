# Final Project Proposal

**Name:**
**Option:** Option 1 / Option 2 <!-- delete one-->
**Working title:**

> **Due Fr 11/20 at 5:00pm.** Fill in every section below, then commit and push this file to your final-project repo.
> Replace the text in *italics* with your own. You can delete the instruction lines (the ones starting with `>`) when you're done.

---

## 1. Research question

> 1-2 sentences.

*Your question here*

## 2. Motivation

> 2-3 sentences. Why does this question matter? What is the broader context?

*Your motivation here*
 
## 3. Hypothesis

> What do you expect to find? What result would surprise you?

**I expect:** *..*

**It would suprise me if:** *...*

## 4. Data

> Use data we have not analyzed in class. New variables form a source we've used are fine, and so are new places or events. Give the **specific** page you got it from, not just the agency's homepage.
> Copy the Dataset 1 block for each additional dataset.

### Dataset 1

- **Name / description:** *...*
- **Source (specific URL):** *...*
- **Citation:** *...*
- **Format** (CSV, GeoTiff, shapefile, NetCDF, image, ...): *...*
- **File size:** *... MB* <!-- Over ~50 MB? You'lll need a download funciton instead of committing the file -->
- **Proof it's loaded:** paste the output of `df.head()` and `df.shape` (or your array's or image's `.shape`) below.

```text
paste df.head() output here
```

```text
paste df.shape output here
```

### Backup dataset (if your first choice doesn't work out)

- **Name / source:** *...*

## 5. Skills

> **Core skills (everyone):** functions and loops, NumPy arrays and masks, at least one multi-panel figure.
> **More skills:** choose at least 3 (undergrad) or 4 (grad) from: pandas, SciPy, GeoPandas/maps, image processing, gridded data.
> Check the boxes `[x]` and write one line on how you'll use each.

**Core skills**
- [ ] Functions and loops: *how I'll use them*
- [ ] NumPy arrays and masks: *...*
- [ ] Multi-panel figure: *what it will show*

**More skills**
- [ ] pandas (cleaning, `concat`/`merge`, `groupby`/`pd.cut`/`.rolling()`): *...*
- [ ] SciPy (fitting, statistics, peaks, rates of change, integrals): *...*
- [ ] GeoPandas and maps: *...*
- [ ] Image processing (color bands, pixel masks, band math): *...*
- [ ] Gridded data (rasters): *...*
      
## 6. Analysis plan

> Your steps in order. At least 3 (undergrad) or 5 (grad).

1. *..*
2. *..*
3. *..*
4. *..*
5. *..*

## 7. Sketch your main figure

> Before you make it, plan the one figure that will answer your research question. Think of it like the schematic figures in Lecture 22: you're deciding what the graph should look like before you have the data in it.
>
> **Example.** *Question:* Is the glacier retreating faster since 2000 than before? *Figure:* glacier length (m) on the y-axis, with a trend line fit before 2000 and another after. *If I'm right:* the post-2000 line is steeper. *If I'm wrong:* the two lines have about the same slope.

- **What the figure shows:** *...*
- **x-axis (with units):** *...*
- **y-axis (with units):** *...*
- **If my hypothesis is right, the figure will look like:** *...*
- **If my hypothesis is wrong, the figure will look like:** *...*

> Optional: draw it by hand, add a photo to `figures/`, and link it here: `![sketch](figures/sketch.jpg)`

## 8. Uncertainty plan

> Which kind of uncertainty will you report with your main result? Pick one (or more) and explain.
> Options: standard error of a fit (`linregress`) · spread across stations/sites/samples · sensitivity to a choice you made (window, bins, threshold) · measurement error from the data source.

*Your plan here.*

## 9. Challenges and questions

**What I'm worried about** (data, methods, or technical):

*...*

**What I need help with:**

*...*

**One change I made after Pitch Day:**

*...*

## 10. Citations

**1-2 (undergrads) or 2-4 (grads):**

1. *...*
2. *...*
3. *...*
4. *...*

---

## 11. Graduate students only

**How this project connects to my research:**

*...*

**Graduate extras I plan to do** (at least 2):

- [ ] Sensitivity test: *...*
- [ ] Comparison to published values: *...*
- [ ] A second method, compared with the first: *...*
- [ ] Critical evaluation of my own methods and assumptions: *...*

