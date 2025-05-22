# Data Wrangling with Python & Pandas

**Estimated time:** 30 minutes

---

## 📝 Objectives

After completing this lab, you will be able to:

1. Identify and handle missing values  
2. Correct data formatting (types, units)  
3. Standardize and normalize data  
4. Perform binning (discretization)  
5. Create indicator (dummy) variables  

---

## 📑 Table of Contents

1. [Introduction](#introduction)  
2. [Importing the Dataset](#importing-the-dataset)  
3. [Identifying & Handling Missing Values](#identifying--handling-missing-values)  
   - Convert “?” to `NaN`  
   - Count and visualize missing data  
   - Impute or drop missing entries  
4. [Correcting Data Formats](#correcting-data-formats)  
5. [Data Standardization](#data-standardization)  
   - Converting mpg → L/100 km  
6. [Data Normalization](#data-normalization)  
   - Scaling to [0, 1]  
7. [Binning](#binning)  
   - Creating categorical bins for continuous data  
8. [Indicator Variables](#indicator-variables)  
9. [Questions & Exercises](#questions--exercises)  

---

## Introduction

Data wrangling converts raw data into a clean format ready for analysis. In this lab, you’ll work with the “Automobile Dataset” (UCI) to practice common cleaning tasks using Pandas in a JupyterLite environment.

---

## Importing the Dataset

1. **Download via Pyodide** (JupyterLite only):
   ```python
   from pyodide.http import pyfetch
   async def download(url, filename):
       resp = await pyfetch(url)
       if resp.status == 200:
           with open(filename, "wb") as f:
               f.write(await resp.bytes())

   await download(data_url, "usedcars.csv")
