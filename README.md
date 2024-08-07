# Medical Records Formatter

## Overview

This project contains a script to format medical records from a CSV file into a structured text format. The script reads a CSV file containing medical records, processes each record, and writes the formatted output to a text file.

## Files

- `medical_records.csv`: The input CSV file containing medical records.
- `medical_records.txt`: The output text file where formatted records are written.
- `formatter_script.py`: The Python script used to read the CSV file and generate the formatted text file.

## Script

The `formatter_script.py` script contains the following code:

```python
import pandas as pd

# Load the CSV file
file_path = '/mnt/data/medical_records.csv'
df = pd.read_csv(file_path)

# Create a text file to write the formatted output
output_file_path = '/mnt/data/medical_records.txt'

with open(output_file_path, 'w') as txt_file:
    for index, row in df.iterrows():
        for column in df.columns:
            txt_file.write(f"{column}: {row[column]}\n")
        txt_file.write("\n")  # Add a newline for separation between records

print(f"Formatted text file has been created at {output_file_path}")
