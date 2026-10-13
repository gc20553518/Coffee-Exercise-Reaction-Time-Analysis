# Coffee-Exercise-Reaction-Time-Analysis

**UCLA STATS 101B · Design and Analysis of Experiments · Spring 2026 · Group Project**

## Overview

We investigated whether regular versus decaffeinated coffee and a short bout of exercise affect reaction time, and whether caffeine and exercise interact. The study was conducted with **The Islands virtual population**, not with human participants in a real-world clinical trial.

## Experimental design

- **Design:** 2² factorial experiment, blocked by sex.
- **Factor A — Caffeine:** 250 mL decaf vs. 250 mL regular coffee.
- **Factor B — Exercise:** Rest vs. 30 seconds of jumping.
- **Response:** Percent change in ruler-drop reaction time from before to after treatment; negative values indicate faster reactions.
- **Analytic sample:** 72 virtual subjects, balanced at 9 subjects per Sex × Caffeine × Exercise combination. The source file contained 96 observations; the R script uses `set.seed(101)` and subsamples within each combination.

## Analysis

The group used R for factorial ANOVA (`aov()`), effect estimates from a linear model (`lm()`), power calculations (`pwr`), interaction and main-effect plots, and residual diagnostics.

## Results (reported 72-subject analysis)

| Treatment | Rest (mean % change) | Jump 30 s (mean % change) |
|---|---:|---:|
| Decaf | −0.29% | −13.05% |
| Regular coffee | +0.07% | −13.92% |

- **Exercise:** −13.378 percentage-point estimated factorial effect; ANOVA *F* ≈ 306.03, *p* < 0.001.
- **Caffeine:** No statistically significant effect in this experiment (*p* = 0.746).
- **Interaction:** No statistically significant caffeine × exercise interaction (*p* = 0.424).
- **Model R²:** Approximately 0.821.

These findings describe this **virtual-population experiment** and do not establish an effect in real-world people.

## Files

- [`analysis.Rmd`](analysis.Rmd): The group's R Markdown analysis, with a machine-specific input path replaced by a relative path and raw dataset printing removed.
- [`final-report.pdf`](final-report.pdf): Six-page group report (June 7, 2026), including figures and detailed interpretation.

### Reproducing the analysis

1. Obtain `stats101b_experiment.csv` from an authorized source and place it next to `analysis.Rmd`.
2. In R, install `rmarkdown`, `knitr`, `pwr`, and `phia` if needed (a PDF render also needs a LaTeX installation).
3. Knit `analysis.Rmd`. It uses a fixed random seed of 101 for the 72-subject balanced subsample.

**Dataset note:** The original CSV is not included, because it contains participant names and household/location fields from the virtual environment and its redistribution permissions have not been confirmed. The presentation was not included because it used an earlier 96-subject analysis in milliseconds, rather than the final 72-subject percent-change analysis.

## Limitations

The experiment uses simulated island residents from a single town. Treatment timing, age variation, and limited power for small effects may affect interpretation. See the report for discussion.

## Contributions and acknowledgment

This was a **group project**, not an independent project. Group 20: Siddharth Chittapuram, Jonathan Yu, Kyle Thai, Ace Zhang, Guo Chu, and Yichen Xuan. The report and code represent collaborative work; individual contributions are not separated in the supplied materials.
