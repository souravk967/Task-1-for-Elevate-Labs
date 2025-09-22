 Task-1-for-Elevate-Labs
 
# Data Cleaning and Preprocessing - Netflix Dataset 

##  Objective
The goal of this task was to **clean and preprocess the raw Netflix Movies and TV Shows dataset** to make it consistent, standardized, and ready for analysis or modeling.

---

##  Steps Performed

### 1. Dataset Exploration (Step 1)
- Loaded the dataset `netflix_titles.csv`
- Checked dataset shape (`8807 rows × 12 columns`)
- Used `.info()` and `.describe()` to review data types and summary stats
- Identified missing values in several columns (`director`, `cast`, `country`, `date_added`, `rating`, `duration`)

---

### 2. Handling Missing Values (Step 2 & Step 3)
- **director** → filled missing values with `"Unknown"`
- **cast** → filled missing values with `"Unknown"`
- **country** → filled missing values with **mode** (most frequent: `United States`)
- **rating** → filled missing values with `"Unknown"`
- **date_added** → converted to datetime format, dropped missing ones as they were very few (~98 records)
- **duration** → filled missing values with `"Unknown"`

 After this step, the dataset had **no missing values**.

---

### 3. Removing Duplicates (Step 4)
- Checked for duplicate rows using `.duplicated()`
- Found **0 duplicates**, dataset remained unchanged

---

### 4. Standardizing Text Columns (Step 5)
- Converted `title`, `type`, `listed_in` → **lowercase**
- Stripped extra spaces from text values
- Converted `country` → **title case** (e.g., `"united states"` → `"United States"`)

---

### 5. Renaming Columns (Step 6)
- Converted all column names to **snake_case** (e.g. `Release Year` → `release_year`, `Date Added` → `date_added`) for consistency

---

### 6. Fixing Data Types (Step 7)
- Converted `release_year` → integer
- Converted `date_added` → datetime (`dd-mm-yyyy` format applied at export)
- Verified all columns had appropriate data types

---

### 7. Saving the Cleaned Dataset (Step 8)
- Saved the final processed dataset as:
  - `netflix_titles_clean.csv`
- Kept the original dataset (`netflix_titles.csv`) unchanged for backup

---

##  Deliverables
1. **Data_Cleaning_Task.ipynb** → Jupyter Notebook with all cleaning steps  
2. **netflix_titles_clean.csv** → Final cleaned dataset  
3. **README.md** → Summary of data cleaning steps  

---

##  Outcome
- The dataset is now **clean, consistent, and analysis-ready**  
- Successfully handled missing values, standardized text, ensured correct data types, and exported the clean dataset.  
- Ready to use for analysis, visualization, or machine learning tasks.  

---

##  Example of Cleaned Dataset Preview
| title                   | type     | country       | date_added   | release_year | rating   |
|-------------------------|----------|--------------|--------------|--------------|----------|
| Dick johnson is dead    | Movie    | United States | 09-09-2019   | 2020         | PG-13    |
| Blood & water           | Tv show  | South Africa  | 20-05-2021   | 2021         | TV-MA    |
| Ganglands               | Tv show  | France        | 24-09-2021   | 2021         | TV-MA    |

---
