# Luminal A Meta-Analysis

This repository contains an R script that performs a meta-analysis to estimate the prevalence of the Luminal A breast cancer subtype across different studies and regions using the `meta` and `metafor` packages. The analysis includes a forest plot, funnel plot, and heterogeneity testing.

## Files

- `new_lum.xlsx`: Excel file containing the input data. Required columns include:
  - `Study`: Study identifier
  - `Lum`: Number of Luminal A cases
  - `Total`: Total number of cases
  - `Region`: Region of study
- `forest_plot.pdf`: Output file containing the forest plot of Luminal A prevalence.

## Requirements

Install the following R packages before running the script:

```R
install.packages("tidyverse")
install.packages("meta")
install.packages("metafor")
install.packages("readxl")
```

## Running the Analysis

The script performs the following steps:

1. Loads required libraries and data.
2. Summarizes and previews the dataset.
3. Conducts a meta-analysis using `metaprop()` to estimate Luminal A subtype prevalence.
4. Generates a forest plot and saves it as a PDF.
5. Plots a funnel plot to assess study effects.
6. Attempts to test for publication bias with `metabias()` (though note: `Lum_a` is undefined in the script and needs correction).

## Notes

- Make sure `new_lum.xlsx` is in the working directory before running the script.
- Ensure that the columns used in the `metaprop()` call (`Lum`, `Total`, `Study`, and `Region`) are correctly named and formatted in the Excel file.
- There is a likely error at the end of the script: `metabias(Lum_a)` references an undefined object `Lum_a`. You may need to revise this line depending on your intended use (e.g., `metabias(Lumi)` if applicable).

## Output

- `forest_plot.pdf`: A stratified forest plot showing prevalence estimates and confidence intervals by study and region.
- Funnel plot: Visual assessment of possible publication bias.

## License

MIT License

## Contact

For questions or contributions, please contact Abimbola Fatimat Onyia at [abimbolajolaoluwa@gmail.com](mailto:abimbolajolaoluwa@gmail.com).
