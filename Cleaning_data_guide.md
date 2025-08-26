# Data Cleaning Guide – Bike Buyers Dataset

This document describes the data cleaning process applied to the **bike_buyers** dataset in Excel.  

## 1. Copy Data to Working Sheet  
- Copy all data from the `bike_buyers` (raw data) sheet.  
- Paste it into a new sheet named **Working_sheet**.  
- This ensures the original raw dataset remains unchanged.  

## 2. Remove Duplicates  
- Go to the **Working_sheet**.  
- Select the entire dataset (or press **Ctrl + A**).  
- Navigate to **Data > Remove Duplicates**.  
- Select all columns to check for exact duplicate rows.  
- Click **OK** to remove duplicates.  

## 3. Standardize Values with Find and Replace  

### Column: *Marital Status*  
- `M` → **Married**  
- `S` → **Single**  

### Column: *Gender*  
- `M` → **Male**  
- `F` → **Female**  

Steps:  
1. Select the target column.  
2. Press **Ctrl + H** (Find and Replace).  
3. Replace each code with the corresponding full value.  

### 4. Create Age Brackets
- Insert a new column named **Age Brackets** next to the `Age` column.
- Use the following formula (assuming `Age` is in column L):

```excel
=IF(L2>54,"Old",IF(L2>=31,"Middle Age",IF(L2<31,"Adolescent","Invalid")))
```

- This categorizes customers into:
  - **Old**: Age > 54
  - **Middle Age**: Age between 31 and 54
  - **Adolescent**: Age < 31
  - **Invalid**: Any unexpected values


After these steps, the dataset in **Working_sheet** is clean and ready for pivot tables and dashboard analysis.
