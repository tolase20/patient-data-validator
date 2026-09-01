````markdown
# Patient Data Validator

The program provides a healthcare facility's Digital Health Team with an automated, rule-based validation system to check patient information, classify patients by age, determine record validity, and generate structured validation reports before a record is accepted into the hospital system.

## Problem Statement

In hospital registration workflows, accurate early-stage patient data validation is essential for safe and efficient care. Traditionally, checking whether a patient's age, temperature, heart rate, gender, and identifying details fall within acceptable ranges involves manual review by registration staff. This manual workflow is susceptible to human oversight, fails to apply consistent validation rules across patients, and can allow incomplete or invalid records to reach clinical staff. Without a standardized validation and reporting process, hospitals frequently encounter data-quality issues that affect patient safety and administrative accuracy.

## Solution

To solve these operational challenges, this project implements a modular Python validation system. The program stores patient information, validates each field against defined medical intake rules using conditional logic, classifies patients into age categories, and determines overall record validity. The tool processes individual patient records and can also process multiple patient records in a batch, compiling summary statistics in a clean, formatted report.

## Importance of the Problem

Patient safety and hospital efficiency depend heavily on accurate intake data. Unvalidated or inconsistent patient records can lead to delayed treatment, incorrect classification of urgency, and administrative errors. Automating validation logic standardizes checks across every patient record, ensures consistent rule enforcement regardless of who processes the intake, and equips healthcare workers with a clear, immediate view of which records are safe to proceed with.

## Features

- **Interactive Field Validation**: Checks patient name, ID, age, gender, temperature, and heart rate against defined hospital rules.
- **Age Category Classification**: Automatically classifies patients as Child, Teenager, Adult, or Senior based on age.
- **Overall Record Validation Status**: Combines all individual checks to determine whether a patient record is Valid or Invalid.
- **Reusable Validation Functions**: Individual functions handle age, temperature, and heart rate checks independently, and a combined function validates a full patient record.
- **Interactive Patient ID Entry**: Repeatedly requests a Patient ID until a valid, non-empty value is provided.
- **Controlled Infinite Loop**: Demonstrates a while True loop with a safe, user-driven exit condition.
- **Formatted Validation Report**: Generates a clean, bordered report summarizing all validation results and the final status.
- **Batch Patient Processing**: Validates multiple patient records at once and reports how many are valid, how many are invalid, which patients failed, and which validation rule fails most often.

## Technologies

- Python 3
- Jupyter Notebook

## Python Concepts Used

Built strictly adhering to core procedural programming fundamentals covered in Semester 2:

- **Variables and Data Types**: Strings, integers, floats, and Booleans used to store patient information.
- **Comparison Operators**: Used comparison checks (>, <, >=, <=, ==) to validate whether values fall within accepted ranges.
- **Logical Operators**: Combined conditions using and and or to evaluate multiple validation rules at once.
- **Conditional Statements**: if, elif, and else used to classify gender validity and age categories.
- **Functions**: Individual validation functions and a combined validate_patient() function make the program reusable and easier to maintain.
- **For Loops**: Used to display validation results and process multiple patient records.
- **While Loops**: Used for repeated Patient ID input until a valid value is entered.
- **Infinite Loops and Break Statement**: Used to demonstrate a controlled while True loop with a safe exit condition.
- **Variable Scope**: Variables created inside functions exist only within that function, keeping the program's logic clean and predictable.

## Project Workflow

- **Data Collection and Field Validation**: Patient information is stored in variables, then each field is checked against its own rule (age between 1–120, temperature between 35–42°C, heart rate between 40–200 BPM, non-empty name and ID, and gender limited to Male, Female, or Other).
- **Age Category Classification**: Based on validated age, the patient is classified as Child, Teenager, Adult, or Senior.
- **Overall Validation and Functional Refactor**: Individual checks are combined into an overall validity result, then wrapped inside reusable functions for maintainability.
- **Result Display**: A for loop iterates through the validation results dictionary, clearly showing which checks passed and which failed.
- **Controlled User Input**: A while loop handles repeated Patient ID entry, and a separate infinite loop demonstrates a safe yes/no exit condition.
- **Report Generation**: A formatted report is generated, showing all patient details, individual validation results, age category, and final validation status.
- **Batch Processing**: Multiple patient records are processed using a for loop, with a summary of valid/invalid counts and the most frequently failing rule.

## Sample Patient Record

| Information | Value |
| --- | --- |
| Patient Name | David Okoro |
| Patient ID | PT20260801 |
| Age | 45 |
| Gender | Male |
| Temperature | 37.2°C |
| Heart Rate | 82 BPM |
| Emergency | False |

For example, David Okoro is 45 years old, so his category is:

Adult

His record passes every validation rule, so the final status is:

Patient Record: Valid

## Program Screenshot
<img width="1366" height="768" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/2cca32aa-f9e5-4cf2-93b7-50726983f9a1" />

<img width="1366" height="768" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/169564d6-4f84-430f-abf9-86bdf62eb851" />
<img width="1366" height="768" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/ce69e20e-bd23-4752-9ac2-172f8c5b2e8a" />
<img width="1366" height="768" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/e04ecce4-31fe-4124-9908-f2af1a9bc9d1" />
<img width="1366" height="768" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/41abbdd0-bff1-4f7d-8e98-03b5c8431167" />
<img width="1366" height="768" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/39ef913d-1756-46cc-a6c1-b80953f41199" />


## Code Snippets

Validating a field:

```python
age_valid = age >= 1 and age <= 120
```

Classifying age category:

```python
if age <= 12:
    age_category = "Child"
elif age <= 17:
    age_category = "Teenager"
elif age <= 64:
    age_category = "Adult"
else:
    age_category = "Senior"
```

Reusable validation function:

```python
def validate_patient(name, patient_id, age, gender, temperature, heart_rate):
    results = {}
    results["Name Valid"] = name.strip() != ""
    results["Patient ID Valid"] = patient_id.strip() != ""
    results["Age Valid"] = age >= 1 and age <= 120
    results["Gender Valid"] = gender == "Male" or gender == "Female" or gender == "Other"
    results["Temperature Valid"] = temperature >= 35 and temperature <= 42
    results["Heart Rate Valid"] = heart_rate > 40 and heart_rate < 200
    overall_valid = all(results.values())
    return results, overall_valid
```

Processing multiple patients:

```python
for p in patients:
    results, overall_valid = validate_patient(
        p["name"], p["id"], p["age"], p["gender"], p["temperature"], p["heart_rate"]
    )
```

## Results

Bonus Batch Validation Summary

- Total Patient Records Evaluated: 4
- Valid Records: 2 (David Okoro, Grace Bello)
- Invalid Records: 2 (Samuel Ade — missing Patient ID; Anita James — age 130 exceeds the valid range)
- Most Common Failing Check: Patient ID Valid / Age Valid

## Key Findings

- **Field-Level Isolation Improves Debugging**: Writing each validation rule as its own Boolean before combining them made it easy to confirm each rule worked correctly in isolation.
- **Reusable Functions Simplified Batch Processing**: Because the core validation logic was already wrapped in validate_patient(), extending the program to handle multiple patients required no new validation code, only a loop.
- **Consistent Rule Enforcement**: Every patient record, whether processed individually or in a batch, is checked against the exact same rules, removing any inconsistency that manual checking could introduce.

## Limitations

- Uses sample patient data rather than a live hospital database.
- Patient records are not permanently saved between runs.
- The system does not have a graphical user interface.
- Input type errors (e.g. entering text where a number is expected) are not gracefully handled.
- The project is primarily designed for learning and practicing Python fundamentals, not production hospital use.

## Future Improvements

- Adding exception handling (try/except) to gracefully manage invalid input types.
- Connecting to a real database such as MySQL or SQLite for persistent record storage.
- Creating a graphical user interface for non-technical registration staff.
- Adding search functionality to look up existing patient records.
- Generating downloadable validation reports (PDF or text file).
- Expanding validation to cover additional patient fields (blood pressure, allergies, etc).

## How to Run

### 1. Clone the Repository

````
git clone https://github.com/tolase20/patient-data-validator.git
````

### 2. Open the Project

Open the Jupyter Notebook containing the Patient Data Validator.

### 3. Run the Program

Run the cells from the beginning and follow the prompts displayed. When the program reaches the Patient ID or yes/no sections, enter a valid value to continue, or type:

no

to stop the infinite loop demonstration.

## Author

**Gladys**

## Acknowledgement

This project was completed as part of my practical Python learning journey and is focused on applying Python fundamentals to a real-world healthcare validation scenario.

Special appreciation to **SmartBizCrux** and **Coach Timothy** for the guidance, training, and support throughout the learning process.
````
