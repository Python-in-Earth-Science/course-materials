# Final Project: Proposal
### EES 3350/5350 · Monday, November 16, 2026
#### Due Friday, November 20 at 5:00pm

Your proposal is a short plan for your final project: your question, your data (already loaded), your methods, and what your main figure will show. Starting on Pitch Day, write it in `proposal.md` in your final-project repo and push it by **Friday 11/20 at 5:00pm.**

## What goes in `proposal.md`?

The template in your repo has these sections. Replace the italic text with your own.

| Section | What to write |
|--|--|
|1. Research question| 1-2 clear sentences |
|2. Motivation|2-3 sentences: why it matters and the broader context|
|3. Hypothesis|What you expect to find, and what result would surprise you|
|4. Data|For each dataset: name, specific source URL, citation, format, file size, and **proof you've loaded it** (paste the output of `df.head()` and `df.shape`, or an array's `.shape`). Plus a backup dataset.|
|5. Skills|Check the core skills (functions and loops, NumPy arrays and masks, a multi-panel figure) and at least 3 more (undergrad) or 4 more (grad), with one line on how you'll use each|
|6. Analysis plan|Your steps, in order: at least 3 (undergrad) or 5 (grad)|
|7. Sketch your main figure|Plan the one figure that will answer your question before you make it: what it shows, each axis with units, and how it will look if your hypothesis is right vs. wrong (like the schematic figures in Lecture 22)|
|8. Uncertainty plan|Which kind of uncertainty you'll report: standard error of a fit, spread across sites, sensitivity to a choice you made, or measurement error|
|9. Challenges and questions|What you're worried about, what you need help with, and one change you made after Pitch Day|
|10. Graduate students only|How the project connects to your research, 2-3 citations, and which graduate extras you plan to do|

It's fine to propose GeoPandas, image processing, or raster methods before we've covered them in class. You'll need them working by the 12/2 check-in.

Files over about 50 MB can't go in your repo. If your data is that big, say so in section 4, and plan to write a function that downloads it.

## Submitting, feedback, and grading
- **Submit** by committing and pushing `proposal.md` to your final-project repo by **Fri 11/20 at 5pm**. Check on GitHub that it's there.
- **Feedback.** I'll read every proposal and send feedback as soon as I'm able. If I suggest changes, make them before your 12/2 check-in.
- **Grading.** The proposal is part of the 5% proposal workshop grade (with your Pitch Day feedback forms). It's graded on completeness (every section filled in, data loaded) and on quality and feasibility:
    - a clear, answerable question
    - specific data sources
    - methods that match the question
    - a scope you can finish
    - grad students: connected to your research and the planned graduate extras
- **Late Policy.** 10% off per day. 
