# Bayesian Analysis of Early-Career MLB Performance

## Project Overview

This project applies a **Bayesian Beta-Binomial model** to estimate the true batting ability of MLB players using only their first two MLB seasons.

The model combines:
- A player's observed hits and at-bats
- Historical league batting performance
- Bayesian shrinkage via a Beta prior

The goal is to produce more stable estimates of batting talent and evaluate whether Bayesian estimates improve prediction of future performance.

---

## Methodology

### Data Source
This project uses the Lahman Baseball Database:

- `Batting.csv`
- `People.csv`

Players are restricted to:

- Seasons between 1995–2022
- First two MLB seasons only
- At least 100 combined at-bats during those two seasons

### Statistical Model

For each player:

- Hits are modeled as a Binomial random variable
- True batting ability is modeled with a Beta prior

Outputs include:

- Posterior mean batting ability
- 95% credible intervals
- Probability of being above league average
- Out-of-sample validation using Year 3 performance

---

## Example Visualizations

The notebook generates several figures, including:

### 1. Distribution of First-Two-Year At-Bats
Shows how much information is available for each player.

### 2. Distribution of Raw Batting Average
Compares player batting averages against league-wide averages.

### 3. Bayesian Shrinkage Plot
Compares raw batting average to posterior mean estimates.

### 4. Year-3 Validation Analysis
Evaluates how well Bayesian estimates predict future performance.

### 5. Uncertainty Analysis
Shows how credible interval width decreases as sample size increases.

### 6. Probability Above League Average
Displays posterior probabilities that a player is better than league average.

---

## Project Structure

```text
.
├── data/
│   ├── Batting.csv
│   └── People.csv
├── figures/
├── stats_115_code.Rmd
├── stats_115_code.html
└── README.md
```

---

## Installation

### Required R Packages

```r
install.packages(c(
  "tidyverse",
  "knitr",
  "ggplot2",
  "scales",
  "ggrepel"
))
```

---

## Running the Project

### Option 1: RStudio

1. Open `stats_115_code.Rmd`
2. Ensure the Lahman data files are located in the `data/` directory
3. Click **Knit**
4. An HTML report will be generated

### Option 2: R Console

```r
rmarkdown::render("stats_115_code.Rmd")
```

---

## Key Analyses

### Posterior Estimation

Computes:

- Posterior mean batting ability
- Posterior Beta parameters
- Credible intervals

### League Comparison

Computes:

- Probability player is above league average
- Rankings by posterior confidence

### Out-of-Sample Validation

Compares:

- League-average baseline
- Raw first-two-year batting average
- Bayesian posterior estimates

Metrics:

- Weighted Mean Squared Error (MSE)
- Negative Log-Likelihood (NLL)

## Results
The Bayesian model reduced Year-3 batting average prediction error by 20.2% compared to raw first-two-year batting averages and by 22.2% compared to a league-average baseline.
---

## Author

Michael Shkolnik

University of California, Irvine  
B.S. Data Science
