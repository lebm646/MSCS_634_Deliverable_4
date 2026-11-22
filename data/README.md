# Dataset dictionary and provenance

These inputs come from the three project repositories linked in the root README. The consolidated notebook preserves original loading and label integration. The alignment audit confirmed matching predictor rows across the source CSVs; models were not rerun. `german.data` remains bundled as the original UCI reference.

| File | Role |
|---|---|
| german_credit_data.csv | Deliverable 1 raw derivative, including export index |
| german_credit_cleaned.csv | Deliverable 1 cleaning reference; input to original regression analysis |
| german_credit_with_risk.csv | Deliverable 3 labeled reference; source-reported UCI good/bad labels |
| german.data | UCI symbolic-format source, 20 predictors plus class |

| Variable | Meaning / treatment |
|---|---|
| Age | Age in years; demographic attribute |
| Sex | Binary derivative of original personal-status/sex codes; simplified representation |
| Job | Skill code 0â€“3; numeric ordinal treatment assumes equally spaced levels |
| Housing | rent, own, free |
| Saving accounts | little: <100 DM; moderate: 100â€“<500; quite rich: 500â€“<1,000; rich: â‰¥1,000; Unknown: unknown/no savings account |
| Checking account | little: <0 DM; moderate: 0â€“<200; rich: â‰¥200 DM / qualifying salary assignment; Unknown: no checking account |
| Credit amount | Historical DM; regression target, classification/clustering predictor |
| Duration | Months |
| Purpose | Simplified categories; original new/used car and education/retraining codes are combined |
| Risk | good/bad benchmark class, mapped from UCI 1/2; bad is positive class 1 in models |

Missing savings/checking cells in the derivative are filled with `Unknown` for continuity. They map to meaningful original UCI codes, not invented balance estimates. Unknown checking must not be interpreted as an established/wealthy account. The regression excludes Risk; clustering excludes Risk; association mining includes Risk only as an exploratory item.

Credit-rule bins are sample quartiles, whose exact edges are printed in the notebook and exported when it is run. Age bins are (0,25], (25,35], (35,50], (50,âˆž]; duration bins are (0,12], (12,24], (24,âˆž]. These boundaries are explicit and their labels match inclusivity.

Source: Hofmann, H. (1994), [Statlog (German Credit Data)](https://doi.org/10.24432/C5NC77), UCI Machine Learning Repository, CC BY 4.0. See [variable definitions](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data). The derivative source supplied in Deliverable 1 is [Kaggle German Credit Data](https://www.kaggle.com/datasets/varunchawla30/german-credit-data).
