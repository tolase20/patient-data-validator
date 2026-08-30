# PATIENT DATA VALIDATOR

A Python-based Patient Data Validator developed as a practical case study to check, classify, and report on patient information before hospital registration. The project demonstrates the application of core Python programming concepts to a real-world healthcare scenario.

---

## Project Overview

The Patient Data Validator is a Python program built for a hospital's Digital Health Team. It processes patient records, validates each field against defined medical intake rules, classifies patients by age category, and generates a clear, professional validation report for healthcare workers.

This project was developed as part of the Python Study Group (Team J) case study, bringing together Second Semester concepts including operators, conditional statements, loops, functions, and variable scope.

## Project Objectives

- Validate patient name, ID, age, gender, temperature, and heart rate.
- Classify patients into age categories.
- Determine overall record validity based on all checks combined.
- Generate a structured patient validation report.
- Apply Python programming concepts to solve a practical healthcare problem.

## Tools & Technologies

- Python
- Jupyter Notebook

## Python Concepts Applied

- Variables and data types
- Operators (arithmetic, comparison, logical, assignment)
- Conditional statements (if, elif, else)
- `for` loops
- `while` loops, including a controlled infinite loop
- Functions, parameters, arguments, and return values
- Variable scope
- Input validation
- Formatted output

## Project Workflow

1. Collect patient information
2. Validate each field against hospital intake rules
3. Classify the patient by age category
4. Determine overall record validity
5. Display individual validation results
6. Request corrected input where needed
7. Generate a patient validation report

## Validation Rules

| Field | Rule |
| --- | --- |
| Age | Must be between 1 and 120 |
| Temperature | Must be between 35°C and 42°C |
| Heart Rate | Must be greater than 40 and less than 200 BPM |
| Patient ID | Must not be empty |
| Patient Name | Must not be empty |
| Gender | Must be Male, Female, or Other |

## Key Features

### Field Validation
Checks patient name, ID, age, gender, temperature, and heart rate against hospital rules.

### Age Category Classification
Classifies patients as Child, Teenager, Adult, or Senior based on age.

### Overall Validation Status
Combines all individual checks to determine whether a record is Valid or Invalid.

### Interactive Patient ID Entry
Repeatedly requests a Patient ID until a valid, non-empty value is provided.

### Controlled Infinite Loop
Demonstrates a `while True` loop with a safe, user-driven exit condition.

### Patient Validation Report
Generates a clean, formatted report summarizing all validation results and the final status.

### Bonus: Batch Patient Validation
Processes multiple patient records with a `for` loop and answers:
- How many patient records are valid?
- How many patient records are invalid?
- Which patient records contain invalid information?
- Which validation rule fails most often?

## Problem-Solving Approach

The project involved breaking a real-world hospital intake scenario into smaller logical components — one validation rule at a time — and implementing each component using Python. This approach helped transform a healthcare data-quality problem into a functional programming solution.

## Project Restrictions

The project was completed without using:

- Classes
- File handling
- Exception handling
- External Python libraries
- Advanced Python concepts not taught in the Study Group

## Key Learning Outcomes

- Improved understanding of Python fundamentals.
- Strengthened logical thinking and problem-solving skills.
- Gained practical experience with functions, loops, and conditional statements.
- Improved understanding of input validation and variable scope.
- Learned how to structure a Python solution around a real-world healthcare problem.

## Acknowledgements

Special thanks to Coach Timothy and SmartBizCrux Technologies for the guidance and learning materials provided throughout the Python Study Group.

## Author

**Gladys**

SmartBizCrux Python Study Group | Python | Data Analytics | Problem Solving

---

> **Another step in my journey toward becoming a better Data Analyst — learning, building, documenting, and improving one project at a time.**
