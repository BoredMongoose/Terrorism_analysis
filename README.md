# Global Terrorism Database Analysis

Exploratory analysis of the [Global Terrorism Database (GTD)](https://www.start.umd.edu/gtd/): 181,691 recorded attacks from 1970 to 2017 (1993 is missing because those records were lost).

<!-- business:start -->
## Business impact

- **Question:** Where do terrorist attacks happen most, and what kind of attacks are they?
- **Key finding:** Mostly in Iraq, Pakistan and Afghanistan, which had 46% of all attacks in 2012–2017. And mostly bombings: 49% of the 181,691 attacks from 1970 to 2017.
- **Recommendation:** Put prevention effort where the attacks are: those three countries, and bombings first. In Central America and Sub-Saharan Africa, plan for armed assaults too, which are as common as bombings there.
- **Estimated impact:** **46%** of attacks in 2012–2017 happened in just three countries: Iraq, Pakistan and Afghanistan.
- **Case study:** [boredmongoose.github.io/projects/terrorism.html](https://boredmongoose.github.io/projects/terrorism.html)
<!-- business:end -->

## Questions
1. Are the number of attacks and casualties related, and which years are outliers?
2. What are the most common attack methods, and how does the mix vary by region and decade?
3. Where did attacks happen?

## Highlights
- Attacks peaked in 2014 (16,903), driven mostly by Iraq, Pakistan and Afghanistan. The earlier rise (1979-1992) came largely from Peru, El Salvador and Colombia.
- Attacks and yearly casualties are strongly correlated (Pearson 0.95, Spearman 0.83); 1998-2007 have unusually high casualties per attack.
- Bombing/Explosion (48.6%), Armed Assault (23.5%) and Assassination (10.6%) make up about 83% of attacks.
- Data quality notes: 45.6% of attacks have an unknown group, a likely duplicated 2001 US event, and one corrupted longitude (fixed).
- The method mix depends on the region: bombings are 61% of attacks in the Middle East and North Africa, but in Central America & the Caribbean and Sub-Saharan Africa armed assaults are more common than bombings. Assassinations fell from 20% of attacks in the 1970s to about 6% after 2000.

## Charts

![Attacks per year](images/attacks_per_year.png)

![Attacks by method](images/attack_methods.png)

![Attack density map](images/attack_density.png)

## Limitations
- The data was collected by different teams over the years, so some changes (like the drop in 1998) may come from how attacks were counted, not real changes.
- For 45.6% of attacks the group is unknown, so I can't say much about who was behind them.
- Missing killed and wounded numbers are counted as 0, so casualties are probably a bit too low.
- The two 2001 US rows look like one event recorded twice, which would double-count about 9,600 casualties in 2001.

<!-- next:start -->
## Next steps

1. Check the two 2001 US rows that look like one event recorded twice.
2. Look at attacks per million people, not just counts, so big countries don't dominate.
3. Add 2018 onwards when a newer version of the database is available.
<!-- next:end -->

## Files
- `terrorism_analysis_clean.ipynb` - the cleaned, written-up analysis
- `analysis.ipynb` - original working notebook

## Data
The dataset is not included (too large for GitHub). Download `globalterrorismdb_0718dist` from [Kaggle](https://www.kaggle.com/datasets/START-UMD/gtd) or START, and place `globalterrorismdb_0718dist.tar.bz2` in the project folder.

## Requirements
Python 3, pandas, numpy, matplotlib, jupyter.

## Reproduce
1. Download the data (above) and put `globalterrorismdb_0718dist.tar.bz2` in the project folder.
2. Install the requirements and open the notebook:

```bash
pip install pandas numpy matplotlib jupyter
jupyter notebook terrorism_analysis_clean.ipynb
```
