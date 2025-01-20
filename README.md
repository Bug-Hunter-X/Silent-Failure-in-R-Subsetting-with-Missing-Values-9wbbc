# Silent Failure in R Subsetting with Missing Values

This repository demonstrates a subtle bug in R's subsetting behavior. When using the `%in%` operator to subset a data frame based on a character vector containing values not present in the data frame's column, R silently ignores these missing values without issuing a warning.  This can lead to incorrect results and difficult-to-debug errors.

The `bug.R` file contains the problematic code, while `bugSolution.R` provides a solution to address this issue.

## Reproducing the Bug

Clone this repository and run `bug.R`.  Observe that the resulting subset data frame only contains rows where the condition is true, without any indication that some values were not found in the original data frame.

## Solution

The `bugSolution.R` file demonstrates a solution to address this issue by explicitly checking if all values in the subsetting vector are present in the relevant data frame column before proceeding with the subsetting operation.