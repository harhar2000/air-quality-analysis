# Air Quality Analysis

## Overview

This repository provides a Python-based tool for analysing air quality data from CSV files. The project includes functionality to:
- Check if a file exists in the directory.
- Read and process data from a given CSV file.
- Extract specific data rows for Christmas Day.
- Calculate the average value of the `PT08.S1(CO)` column for Christmas Day, rounded to two decimal places.

## Features

1. **File Existence Check**  
   - Function: `does_file_exist(file_path)`  
   - Returns `True` if the file exists, otherwise `False`.

2. **Read File Contents**  
   - Function: `get_file_contents(filename)`  
   - Reads the contents of a file and handles cases where the file doesn't exist.

3. **Extract Christmas Day Data**  
   - Function: `christmas_day_air_quality(filename, include_header_row)`  
   - Extracts all rows for December 25th from the file. Optionally includes the header row.

4. **Calculate Christmas Day Average**  
   - Function: `christmas_day_average_air_quality(filename)`  
   - Computes the average value of the `PT08.S1(CO)` column for Christmas Day, handling missing or imperfect data.

## File Descriptions

- **`data_manipulation.py`**  
  Contains all the Python functions for analysing air quality data.

- **`AirQuality.csv`**  
  A sample dataset containing air quality measurements with columns such as `Date`, `Time`, `CO(GT)`, `PT08.S1(CO)`, and others.

## Usage

### 1. Check if a File Exists
```python
print(does_file_exist("AirQuality.csv"))  # Returns True if the file exists
```
### 2. Read File Contens
```python
print(get_file_contents("AirQuality.csv"))  # Prints the file's contents or "Not found"
```

### 3. Extract Christmas Day Data
```python
# Include the header row
print(christmas_day_air_quality("AirQuality.csv", True))

# Exclude the header row
print(christmas_day_air_quality("AirQuality.csv", False))
```

### 4. Calculate the Average Value for Christmas Day
```python
print(christmas_day_average_air_quality("AirQuality.csv"))  # Outputs the average value
```

## Example Dataset
Sample structure of AirQuality.csv
```cs
Date;Time;CO(GT);PT08.S1(CO);NMHC(GT);C6H6(GT);PT08.S2(NMHC);...
10/03/2004;18.00.00;2,6;1360;150;11,9;1046;...
25/12/2004;00.00.00;5,9;1505;...
25/12/2004;01.00.00;6,2;1430;...
```
