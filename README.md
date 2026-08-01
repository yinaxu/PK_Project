# Clinical Pharmacokinetics Learning Lab

Interactive educational tools for learning precision dosing and Bayesian pharmacokinetics.

**[Live site →](#)** *(https://yinaxu.github.io/PK_Project/)*

![status](https://img.shields.io/badge/status-portfolio%20project-0F766E)

## Overview

This project contains interactive educational demonstrations illustrating core principles of model-informed precision dosing. The goal is not to replace validated clinical software, but to help pharmacists, students, and clinicians understand the pharmacokinetic concepts underlying therapeutic drug monitoring.

Topics include: Bayesian forecasting, population pharmacokinetics, MAP estimation, vancomycin AUC monitoring, extended-interval aminoglycoside dosing, and clinical decision support.

## Philosophy

Each project emphasizes transparent equations, interactive visualizations, clinical reasoning, evidence-based references, and educational explanations — rather than serving as production clinical software.

## About this project

As a community pharmacist transitioning into health technology, I wanted to better understand the pharmacokinetic principles behind model-informed precision dosing. Rather than only reading about Bayesian forecasting and extended-interval dosing, I implemented interactive educational tools from first principles. These projects are intended to help learners visualize how pharmacokinetic models inform clinical decisions and are not validated for patient care.

## Pages

| File | Description |
|---|---|
| `index.html` | Landing page — links to all three tools. This is what GitHub Pages serves by default. |
| `vancomycin-explorer.html` | **Bayesian Vancomycin Explorer** — compares a population PK prediction against a Bayesian posterior computed from an observed drug level, using MAP estimation. |
| `aminoglycoside-explorer.html` | **Extended-Interval Aminoglycoside Explorer** — recommends a starting dosing interval from renal function, then classifies a random level against boundary curves derived from the same target-trough logic behind Hartford-nomogram-style dosing, with an auto-generated clinical interpretation. |
| `case-explorer.html` | **Clinical Case Explorer** — a full case: an initial regimen, two sequential vancomycin levels, and a renal function trend, with a step-by-step narrative explaining how and why the Bayesian estimate and AUC recommendation change between levels. |
| `about.html` | Overview, philosophy, and project motivation. |
| `references.html` | Guidelines and papers the models are built from. |
| `disclaimer.html` | Full disclaimer — not for clinical use. |

## Run it

No build step, no dependencies — plain HTML/CSS/JS throughout. Open `index.html` in a browser, or:

```bash
git clone <your-repo-url>
cd clinical-pk-learning-lab
open index.html   # or double-click the file
```

## Hosting it for free

**GitHub Pages (recommended).** Push this repo to GitHub, go to **Settings → Pages**, set the source to your default branch, and your live link will be at `https://<username>.github.io/<repo-name>/`. This is the best option here specifically because the repo itself — commit history, structure, code — is visible alongside the live site, which is a stronger signal for a tech-adjacent healthcare role than a live link alone.

**Alternatives**, if you want a shorter deploy loop or a custom domain later: [Netlify](https://www.netlify.com) and [Vercel](https://vercel.com) both have generous free tiers for static sites and deploy straight from a GitHub repo with zero configuration — either works well for a project this size if you outgrow GitHub Pages.

## Model notes / limitations

- Both explorers use population-average or single-parameter simplified models — not the richer, multi-parameter, validated models used in production clinical dosing software.
- The aminoglycoside boundary curves are derived from the same target-trough logic that underlies the published Hartford nomogram, not digitized from its original chart.
- The Case Explorer's second-update prior blends the individual posterior with a population estimate recalculated at the updated creatinine — a simplification of how a clinician would weigh both signals, not a validated sequential-Bayesian algorithm.
- None of these tools are intended for, or validated for, real patient care. See [`disclaimer.html`](disclaimer.html).

## Stack

Plain HTML/CSS/JS — deliberately dependency-free so it's trivial to read, run, and review.

## License

MIT — feel free to reuse or extend.
