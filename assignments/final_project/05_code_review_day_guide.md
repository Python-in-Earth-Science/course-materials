# Final Project: Code Review Day
### EES 3350/5350 · Monday, December 7, 2026
#### `revision_plan.md` turned in at the end of lab

In today's lab, you'll set up Python on your own laptop, then use it to download your groupmates' draft notebooks and run them. Two tests matter most:
- **Does it run on someone else's computer?**
- **Can a reader tell what you asked and what you found?**

This is called a *code review*.

You'll be in a group of 3 (undergrads) or 2 (grads). Each group has a shared **review repo** in the class GitHub organization, set up like your Lab 10 team repos, with a `drafts/` folder and a `feedback/` folder.

## Before Code Review Day
1. **Install Anaconda on your laptop** (instructions will be posted), with at least 10 GB of free disk space. Bring your laptop and charger.
2. **Push your draft by Sun 12/6 at 11:59pm.** On the ExploreHub:
    - `git pull` in your group's review repository
    - Copy your notebook and your `data/` folder into `drafts/<lastname>/`. Copy the files only, not the `.git` folder
    - `git add`, `git commit`, and `git push`.

Everyone has their own folder, so you won't overwrite each other. Your draft must run top to bottom with `Restart and Run All` and include a question, your loaded data, at least one figure, and draft results. It doesn't need to be polished. If you used any package we haven't used in class, list it in your README.

## In Lab

|Part|Time|What you do|
|--|--|--|
|1. Set up| \~60 min| Create the course environment from `environment.yml`, set up an SSH key on your laptop and add it to GitHub, and open JupyterLab |
|2. Clone| \~10 min| Clone your group's review repo onto your laptop|
|3. Review| \~70 min| Read, run, and give feedback on each groupmate's draft (steps below)|
|4. Revision plan| \~20 min| Read your feedback and plan your changes|

### Reviewing each draft
1. **Run it.** Open the notebook in `drafts/<author>/` and run `Restart & Run All`. This is the real reproducibility test: a different computer with a fresh environment. It breaks if a data file is missing, a path is hard-coded to the author's account, a variable came from a cell that was later deleted, or a package isn't listed in the README.
2. **Read it cold** (about 15 minutes) as someone who has never heard the project pitched.
3. **Write your feedback** in a new file, `feedback/<author>_from_<reviewer>.md`, using the template below.
4. **Talk it through** with the author for about 10 minutes, then switch.
5. **Push your feedback.** Never commit changes to someone else's notebook. Run `git restore drafts/` to throw away the outputs from running their notebook, then `git add` only your feedback file, `commit`, and `push`.

### Your revision plan
Read the feedback on your draft, then write `revision_plan.md` in **your own final-project repo** (not the review repo): the three changes you'll make before 12/15, and why. Commit and push it before you leave lab. Note, you must create this file. Here's a template you can use for the content:

```markdown
# Revision plan for <your name>

**Feedback I got:** <the 1-2 comments that mattered most>

**Change 1:** <what you'll change> - **Why:** <which feedback, or what you noticed>
**Change 2:** *...*
**Change 3:** *...*

**Feedback I'm not acting on and why:** <optional>

```

## Feedback template
```markdown
# Feedback for <author> from <reviewer>

**Did it run with `Restart and Run All` on my laptop?** Yes / No. If no: the first error and the cell it came from.

**In one sentence, what is the research question?**

**What is the main finding, with its uncertainty?**

**Strongest figure, and why:**

**Weakest figure, and how to improve it:**

**One cell or step I couldn't follow:**

**One suggestion:**

```
If you can't answer the question or finding lines from the notebook alone, say so. That's useful feedback.

## If something goes wrong

If your laptop gets stuck, do the Review on the ExploreHub instead (`git pull` the review repo there), and we'll finish your setup on Wed 12/9.

## Grading

Code Review counts towards your final project grade: the feedback files you push for your groupmates and your `revision_plan.md`. The review repo is only for drafts; your final project is submitted in your own final-project repo by **Tue 12/15 at 3:00pm**