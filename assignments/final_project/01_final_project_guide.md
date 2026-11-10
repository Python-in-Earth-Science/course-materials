# EES 3350/5350 Final Project Guide
### Due Tuesday, December 15, at 3:00pm

## Project Description.

In place of a final exam, you will do a small research project in a Jupyter notebook: 
- ask a real Earth science question
- answer it with **data we have not used in class**
- report a quantitative result **with its uncertainty**
- explain what it means

It is due **Tuesday, Dec 15, at 3:00 pm**.

You have already done one of these. Lab 10 walked you through the whole pipeline as a team: load messy files, clean them, combine them,
summarize, fit a rate, make a story figure, and write it up in a README. **Lab 10 was the dress rehearsal.** The final project is the same process, on your own, with your own question and your own data.

There are two options:
- **Option 1**: a research notebook that answers a question of your choosing using public data we have not used in class.
- **Option 2 (grad students, required)**: a research notebook on an original problem connected to your own research, using data relevant to it.

Everything happens in a GitHub repository, the same way you have been submitting labs.

## Requirements
Every project must have these:
- **new data**. don't reuse the specific data we analyzed in class. New variables from a source we've used are fine, and so are new locations or events with the same variables: another flood, another earthquake, another tide gauge. The 2021 Nashville flood or the Nisqually and Northridge earthquakes again are not.
- **a quantitative result with uncertainty**. Report at least one number that answers your question (a rate, a difference, a fit, a count) and say how sure you are of it. Any of these counts:
    - the standard error of a fit (`scipy.stats.linregress`, Lecture 27)
    - the spread across stations, sites, or samples
    - how much the answer changes when you change a choice you made (window size, bin edges, threshold), like the window test in Lab 10
    - the measurement error reported by the data source.
- **functions and loops**. At least 2-3 functions of your own, each with a docstring, and loops where they make sense.
- **readable code**. Comments, meaningful variable names, and short cells. No 200-line code cells, please.
- **reproducible**. Someone else must be able to run your notebook top to bottom with `Restart & Run All`. Use relative paths and put your data files in the repo. You'll test this for real on Code Review Day on 12/7.
- **at least one multi-panel figure**. Like the one you made in Lab 10.


### Skills checklist
Every project must use these **core skills**:
- functions and loops
- NumPy arrays and masks
- at least one multi-panel figure

Then add more skills from this list:
- pandas (cleaning, combining (`concat`, `merge`), summarizing (`groupby`, `pd.cut`, `.rolling()`))
- SciPy (fitting, statistics, peaks, rates of change, integrals)
- GeoPandas and maps
- Image processing: color bands, pixel masks, band math
- Gridded data (rasters)

| | Undergraduate | Graduate|
|--|--|--|
|Core skills| all | all|
|More skills from the list above| at least 3| at least 4|
|graduate extras (below)| -| at least 2|
|problem connected to your own research|-|required|
|citations| 1-2| 2-4|
|Markdown text| about 1000-1250 words | about 1500-1750|
|figures (a multi-panel figure counts as one) | 4-5| 5-6|

**Graduate extras** (choose at least 2):
- a sensitivity test: how do your results change when a parameter or choice changes?
- a comparison of your results to published values
- a second method for the same answer, compared with the first
- a critical look at your own methods and assumptions: what could be wrong, and how much would it matter?

### Notebook structure
Organize your notebook like a short research paper:
1. **Title & Summary**. Your name, then 3-4 sentences: the question, the data, the main result with its uncertainty, and what it means.
2. **Introduction**. Why the question matters, what is already known, your research question, and your hypothesis.
3. **Data & Methods**. Where the data came from (with a citation), what it contains, how you cleaned and combined it, and the methods you used, with any key equations in LaTeX.
4. **Exploratory Analysis**. What the data look like and what patterns you notice. Explain every figure; don't just show it.
5. **Main Analysis**. The analysis that answers your question, with actual numbers and their uncertainty.
6. **Discussion & Conclusions**. The answer to your question, its limitations, why it matters, and a **Next Steps** paragraph proposing one concrete follow-up analysis.
7. **References**.

## Your repository
You'll accept a **final-project** assignment repository, which gives you your own private repository built from a template. Everything you submit goes there: your proposal, your notebook, your data, your figures, and your revision plan.
```
final-project-username/
├── README.md            # title, question, data sources + citation, how to run the notebook
├── proposal.md          # your proposal (due Fri 11/20, 5pm)
├── final_lastname.ipynb
├── data/
├── figures/
├── revision_plan.md     # written at the end of Code Review Day (12/7)
```

### Your notebook vs. your README
These are two different things. **The notebook is your project.** **The README is its front page:** what someone sees first when they open your repo on GitHub, telling them what the project is and how to run it.

| | Notebook (`final_lastname.ipynb`)| README (`README.md`)|
|--|--|--|
|what it is| The full research project: question, data, code, figures, results, discussion| A short cover page for the repo|
|length| About 1000-1250 words of markdown (grad: 1500-1750), plus code and figures | About half a page|
|what goes in it| Everything in "Notebook structure" above | Title and your name; a 2-3 sentence summary of the question and main result; data sources with citations; what's in each folder; how to run the notebook (which packages it needs, and to use `Restart & Run All`)|
|figures| All of them, each explained | Optional: your main figure from `figures/` with a one-line caption|
|analysis or code| Yes, all of it | No|
|graded as| The project itself| Part of "reproducible" and overall presentation|

The README is like the one your team wrote in Lab 10, but shorter: the full write-up now lives in the notebook, not the README. Don't paste your notebook text into the README.

Three habits will save you a ton of trouble:
- **Commit and push often**, not just at deadlines. Your repo is your backup.
- **Watch your file sizes**. GitHub rejects any file over 100 MB. If a data file is bigger than about 50 MB, don't commit it. Instead, write a function in your notebook that downloads it, and say so in your README.
- **Use relative paths** like `data/my_file.csv`, never a full path like `/home/course-materials/Morey_EES5350/...`. A full path only works on your account.

## Timeline and Deadlines
The project has six checkpoints before the final deadline. Four of them happen during class or lab time.

| When| What happens | What you bring or submit | Where |
|--|--|--|--|
|Mon 11/9 (lab) | Final Project introduction and brainstorming | 2-3 candidate questions, a possible dataset for each | In lab |
|Mon 11/16 (lab)| **Pitch Day**: draft your proposal, then pitch it in a group | One new dataset already opened in Python | In lab|
|Fri 11/20 @ 5 pm | **Proposal due**| `proposal.md`| Your final-project repo|
|Wed 12/2 (class)| Project work time + 5-minute one-on-one check-in | Data loaded + one exploratory figure| In class|
|Sun 12/6 @ 11:59 pm| **Draft due**| A copy of your draft notebook + data | Your group's review repository |
|Mon 12/7 (lab)| **Code Review Day**| Your laptop with Anaconda installed; your feedback on your groupmates' drafts; your revision plan | Review repo + your final-project repo |
|**Tue 12/15 @ 3:00pm**| **Final Project due**| The finished notebook, data, figures, README | Your final-project repo|

## Pitch Day, the Project Proposal, and Code Review Day
Each of these has its own document with the full details.
- **[Pitch Day](pitch_day_guide_2026.md) (Mon 11/16, lab)**. Before it, find a dataset we haven't analyzed in class and open it in Python. In lab, you'll draft your proposal, then pitch your project to two classmates and trade written feedback on the Pitch Day Worksheet.

- **[Proposal](proposal_guide.md) (due Fri 11/20 @ 5pm)**. Your plan, written in `proposal.md` in your repo: question, hypothesis, data (with proof it's loaded), skills, analysis steps, a sketch of your main figure, and your uncertainty plan.
- **[Code Review Day](code_review_day_guide.md) (Mon 12/7, lab)**. Push your draft to your group's review repo by Sun 12/6. In lab, you'll set up Python on your laptop with Anaconda, then clone and run your groupmates' drafts and give them feedback. Bring your laptop.

## Check-ins (Wed 12/2)
Class on 12/2 is project work time. While everyone works, I'll meet with each of you for about 5 minutes.

Come with:
- your data loaded in your notebook
- one exploratory figure
- any GeoPandas, image or raster methods from your proposal working on your data
- your biggest question

If you need longer than 5 minutes, arrange office hours with me that week. The draft of your project is due four days later, so this is the time to fix anything that's stuck.

## Grading
The project counts for 15% of your course grade, in two parts.

| Part | Share of course grade | What's graded|
|--|--|--|
| Proposal workshop (Pitch Day + proposal) | 5%| Your `proposal.md` (complete, specific, and feasible, with proof your data is loaded) and the feedback cards you wrote on Pitch Day (11/16) |
| Full Final Project | 10% | Your finished notebook and repo; your Code Review (12/7) feedback and revision plan count towards the grade too|

The final notebook is graded on:
- a clear question and motivation
- data and methods that are described well enough to repeat
- an analysis that answers the question, with uncertainty
- an honest discussion of what you found and its limitations
- figures that are clear, labeled, and explained (meet our figure checklist)
- working, documented, reproducible code that runs top to bottom from a fresh copy
- a notebook that reads as one story from question to answer
- for graduate students, the graduate extras and the connection to your research

A detailed rubric with points will be posted before the proposal is due.

## Finding data, tips, and getting help

### What counts as new data

You can use the same sources we used in class, with new variables or new places and events: a different flood, a different earthquake, other tide gauges, other glaciers. What you can't do is redo an analysis we already did. These specific datasets are off limits:
- the solar-system planets
- Nashville climate normals and 2025 daily weather
- the Calwood Fire gullies
- the factor-of-safety slope data
- the Nisqually and Northridge earthquakes and the Assignment 2 aftershocks
- the Kaneohe and NH10 acidification buoys
- the Lab 10 tide-gauge stations
- the 2021 Nashville flood gauges
- Mauna Loa CO$_2$
- GISP2
- Rembesdalskaka glacier
- the Cedar River profile
- Hurricane Helene analysis from Lab 12

Not sure? Ask me before 11/16.

### Places to look
- **NASA Earthdata** and **USGS EarthExplorer:** satellite imagery (Landsat, MODIS) and elevation data; both need a free account
- **OpenTopography:** high-resolution elevation data (DEMs, lidar)
- **NSIDC (National Snow and Ice Data Center):** sea ice extent, snow, and ice sheets
- **NRCS SNOTEL:** snowpack and snow water equivalent at mountain stations in the western US
- **Smithsonian Global Volcanism Program:** eruption records for volcanoes worldwide
- **NOAA NCEI Paleoclimatology:** ice cores, tree rings, lake and ocean sediment records
- **World Glacier Monitoring Service:** glacier mass balance and length changes worldwide
- **NASA Global Landslide Catalog:** rainfall-triggered landslide events
- **EarthScope GNSS data:** station position time series (plate motion, uplift, subsidence)
- **PANGAEA** and **USGS ScienceBase:** data published alongside research papers

Some sources serve gridded data as NetCDF (`.nc`) files, which need the `xarray` package. That's doable, but check with me first so we can plan for it.

### Tips
- **Start with data.** Get it loaded before you fall in love with a question.
- **Keep it focused.** One clear question beats three vague ones.
- **Write functions early** and test each piece as you go. Don't write 100 lines before running anything.
- **Be specific in your writing.** "Glacier length shrank 410 ± 30 m from 1990 to 2020" beats "the glacier shrank a lot".
- **Explain every figure.** Say what the reader should notice, and connect it to your question.
- **Run `Restart & Run All` often.** If it breaks for you, it will break for your reviewer.

### Getting Help
Schedule office hours! Use the 12/2 check-in! If you're stuck on data, tell me early, before 11/16 if you can.