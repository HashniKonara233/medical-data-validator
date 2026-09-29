# Medical Records Validation System

A Python-based medical records validation program that checks whether patient records follow the required structure and data constraints.

📌 Project Overview

This project validates a collection of medical records using Python.

The program checks:

* Whether the input is a list or tuple.
* Whether each item in the collection is a dictionary.
* Whether each dictionary contains the required keys.
* Whether each value follows the required data format.
* Whether patient IDs and visit IDs follow the expected patterns.
* Whether patient ages are valid.
* Whether gender values are valid.
* Whether medications are stored as a list of strings.

The project uses Python's built-in 're' module for pattern validation.

🛠️ Technologies Used

* Python 3
* Regular Expressions ('re')
* Lists and Dictionaries
* Functions
* Conditional Statements
* Loops
* Data Validation

📂 Medical Record Structure

Each medical record must contain the following keys:

patient_id
age
gender
diagnosis
medications
last_visit_id


Example:


{
    'patient_id': 'P1001',
    'age': 34,
    'gender': 'Female',
    'diagnosis': 'Hypertension',
    'medications': ['Lisinopril'],
    'last_visit_id': 'V2301'
}

🔍 Validation Rules

1. Input must be a list or tuple

The 'validate()' function first checks whether the supplied data is a list or tuple.

If it is not, the following message is displayed:

Invalid format: expected a list or tuple.

2. Each record must be a dictionary

Every item inside the list or tuple must be a dictionary.

If an item is not a dictionary, the program displays:

Invalid format: expected a dictionary at position <index>.

3. Required keys

Each dictionary must contain exactly these keys:

patient_id
age
gender
diagnosis
medications
last_visit_id


If keys are missing or additional/invalid keys are present, the program displays:

Invalid format: <dictionary> at position <index> has missing and/or invalid keys.


4. Patient ID

The patient ID must be a string matching the following pattern:

P + digits

Examples:

P1001
p1002
P1234

The validation is case-insensitive.

5. Age

The age must:

* Be an integer.
* Be at least 18.

Example:

'age': 34

6. Gender

Gender must be a string containing either:

Male
Female

The validation is case-insensitive.

7. Diagnosis

Diagnosis must be a string or 'None'.

Examples:

'diagnosis': 'Hypertension'

or

'diagnosis': None

8. Medications

Medications must be a list, and every item in the list must be a string.

Example:

'medications': ['Metformin', 'Insulin']

9. Last Visit ID

The last visit ID must be a string matching:

V + digits

Examples:

V2301
v2302
V1234

The validation is case-insensitive.

⚙️ How the Program Works

The program contains two main functions.

'find_invalid_records()'

This function checks individual fields of a medical record against predefined constraints.

It returns a list containing the names of fields that contain invalid values.

Example:

invalid_records = find_invalid_records(**dictionary)

If an invalid field is found, the program displays:

Unexpected format '<key>: <value>' at position <index>.

'validate()'

The 'validate()' function performs the overall validation.

It:

1. Checks whether the input is a list or tuple.
2. Iterates through each record.
3. Checks whether each record is a dictionary.
4. Checks whether the required keys are present.
5. Checks individual field values.
6. Prints validation messages when errors are found.
7. Prints 'Valid format.' when all records pass validation.


▶️ How to Run

Make sure Python 3 is installed.

Save the program as:

medical_records.py

Then run:

python medical_records.py

If all records are valid, the output will be:

Valid format.

🧪 Testing

The program can be tested by intentionally introducing invalid data.

Test 1: Add Non-Dictionary Items

To test the second conditional statement, add two items of your choice that are **not dictionaries** at the end of the 'medical_records' list.

For example:

```python
medical_records = [
    # existing records...
    "invalid record",
    12345
]
```

You should see two validation messages printed to the terminal:

```text
Invalid format: expected a dictionary at position 4.
Invalid format: expected a dictionary at position 5.
```

> Restore the original list after testing.


## Test 2: Change `medical_records` to a String

To test the first validation condition, change `medical_records` from a list into a string.

For example:

```python
medical_records = "medical records"
```

The program should display:

```text
Invalid format: expected a list or tuple.
```

> Restore `medical_records` to the original list after testing.

---

## Test 3: Remove the `age` Key

To test whether missing keys are detected correctly, comment out the `age` key from the first dictionary:

```python
{
    'patient_id': 'P1001',
    # 'age': 34,
    'gender': 'Female',
    'diagnosis': 'Hypertension',
    'medications': ['Lisinopril'],
    'last_visit_id': 'V2301',
}
```

The terminal should display:

```text
Invalid format: {'patient_id': 'P1001', 'gender': 'Female', 'diagnosis': 'Hypertension', 'medications': ['Lisinopril'], 'last_visit_id': 'V2301'} at position 0 has missing and/or invalid keys.
```

> Restore the `age` key after testing.

---

## 📋 Expected Valid Output

When all medical records satisfy the required structure and validation rules:

```text
Valid format.
```

---

## 📁 Project Structure

```text
medical-records-validation/
│
├── medical_records.py
└── README.md
```

---

## 🎯 Learning Objectives

This project demonstrates practical use of:

* Python functions
* Lists
* Dictionaries
* Sets
* Loops
* Conditional statements
* Boolean expressions
* `isinstance()`
* List comprehensions
* Dictionary unpacking with `**`
* Regular expressions
* Data validation
* Error handling through validation messages

---

## 👩‍💻 Author

**Hashini Konara**

Computer Science Undergraduate
