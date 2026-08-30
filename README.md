# Patient Data Validator

Team J - Case Study Project #1 (SmartBizCrux Python Study Group)

## Overview

A Python program built for a hospital's Digital Health Team to validate
patient records before they are accepted into the hospital system. The
program checks patient information against defined rules, classifies
patients by age category, and generates a clear validation report.

## Features

- Validates patient name, ID, age, gender, temperature, and heart rate
- Classifies patients into age categories (Child, Teenager, Adult, Senior)
- Determines overall record validity based on all checks combined
- Generates a formatted validation report
- Includes an interactive loop that keeps requesting a Patient ID until
  a valid one is entered
- Includes a controlled infinite loop demonstration with a safe exit
  condition
- Bonus: validates multiple patient records in a batch and summarizes
  results (valid/invalid counts, most common failing check)

## Validation Rules

| Field | Rule |
|---|---|
| Age | Must be between 1 and 120 |
| Temperature | Must be between 35°C and 42°C |
| Heart Rate | Must be greater than 40 and less than 200 BPM |
| Patient ID | Must not be empty |
| Patient Name | Must not be empty |
| Gender | Must be Male, Female, or Other |

## Concepts Used

- Operators (arithmetic, comparison, logical, assignment)
- Conditional statements (if, elif, else)
- For loops
- While loops, including a controlled infinite loop
- Functions, parameters, arguments, and return values
- Variable scope

## How to Run

1. Open `Patient_Data_Validator_TeamJ.ipynb` in Jupyter Notebook or
   JupyterLab.
2. Run the cells in order from top to bottom.
3. When prompted, enter values for the interactive Patient ID and
   yes/no loop sections.

## Author

Gladys — SmartBizCrux Python Study Group, Team J# patient-data-validator
Python Semester 2 case study: validates patient records
