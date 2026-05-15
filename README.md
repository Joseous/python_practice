## Using Python Requests library to pull data from file uploaded on GitHub
### This help practice working with Python, APIs, JSON data, GitHub raw files, and saving extracted data into well-structured CSV files.

**Steps:**
* Created a synthetic dataset using Mockaroo
* The dataset exported as a JSON file.
* Uploaded the JSON file to a public GitHub repository.
* Opened the file on GitHub and got the raw GitHub link.
* Using google colab, imported requests library
* Used the Python requests library to extract/read the JSON data from the raw GitHub link
* Converted the extracted JSON data into a well-structured DataFrame.
* Saved the final output as a well-structured CSV file.

**Note:** The same process was used to extract, convert Json data into well structured dataFrame and saved the final output as well structured CSV file

**Importing requests library**
```python
# Importing "Requests" library

import requests
```
**assigning raw GitHub URL a variable**
```python
# Assigning the raw file url a variable

patient_url = "https://raw.githubusercontent.com/Joseous/python_practice/refs/heads/main/mock_patient_data.json"
```
**Getting content and checking requests status**
```python
content = requests.get(patient_url)

# Checking if the "Requests" worked.

content.status_code
```

**Inspecting the Json file content
```python
# Printing the extracted Json data

patient_content = content.json()

patient_content
```

**Inspecting the records**
```python
# Checking the lenth of extracted Json data

len(patient_content)
```

**Inspecting the type of data Extracted**
```python
# Checking the type of extracted data

type(patient_content)
```

### Converting the extracted JSON data into a well-structured DataFrame.
```python
# Import pandas library for data manipulation

import pandas as pd

df = pd.DataFrame(patient_content)

df.to_csv("patient_data.csv", index=False)
```

*simple steps involved in extracting data from a raw **JSON** file using link from uplaoded JSON file from GitHub to converting it into a well structured **CSV file***
