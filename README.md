# 📊 Data Science Salary & Tech Skills Analytics (End-to-End)

An advanced business intelligence project built directly inside Excel using Power Query, Power Pivot, and DAX. This project transforms, models, and analyzes global tech job market data to extract key insights about in-demand tech skills, cross-border salary variations, and the specific financial return (ROI) of mastering specific technical skills.

## 🎯 Project Objectives
* **Skill Demand Mapping**: Identify non-negotiable core skills and high-paying niches.
* **Salary Benchmarking**: Compare tech salaries inside the US vs. International markets.
* **ROI of Learning**: Determine if a higher volume of skills directly correlates with increased compensation.

## 🛠️ Tech Stack & Tools
* **Data Transformation**: Power Query (ETL pipeline, advanced text splitting, and unpivoting).
* **Data Modeling**: Power Pivot (1-to-Many relational star schema design).
* **Analytics & BI**: Excel PivotTables & Complex DAX measures.
* **Visualization**: Interactive Dashboards, Slicers, Scatter Plots, and Combo Charts.

<img width="1359" height="583" alt="Screenshot P Q" src="https://github.com/user-attachments/assets/4c15ded8-f5e8-48fc-9efd-34eff5c65d06" />

---
## ⚙️ Data Pipeline & Architecture

### 1. Data Cleaning & Wrangling (Power Query)
Raw, nested job market datasets were processed through a robust Power Query pipeline:
* **Atomic Skill Extraction**: Split multi-skill strings using custom delimiters to isolate individual technologies.
* **Normalization**: Unpivoted skill listings to structure the data into a clean, relational dimension table.
* **Text Scrubbing**: Handled missing values, stripped trailing spaces (`Trimmed Text`), and standardized casing (`Capitalized Each Word`).

<img width="1359" height="582" alt="Screenshot P-Q" src="https://github.com/user-attachments/assets/08b8eee4-8d1a-477c-b06d-8d6bcf9035cc" />

### 2. Relational Data Modeling
A relational **Star Schema** was built using Power Pivot, connecting tables over a `Job ID` key with a **One-to-Many (1:*) relationship**:
* `Fact Table`: `data job salary (2)` (Job details, titles, base salary rates, and locations).
* `Dimension Table`: `data job skils` (Atomic breakdown of technical skills per posting).

<img width="1328" height="580" alt="Screenshot P P" src="https://github.com/user-attachments/assets/7bdc499d-8da2-4573-8618-8f2525ecb5af" />

### 3. Advanced DAX Calculations
Custom Business Intelligence measures were engineered to allow cross-filtering across detached tables and geographical subsets:
```dax
median salary skills = 
CALCULATE(
    [median salary], 
    CROSSFILTER('data job salary 2'[Job ID], 'data job skils'[Job ID], Both)
)
```

<img width="1339" height="565" alt="Screenshot en" src="https://github.com/user-attachments/assets/3d7f9ffa-b2a5-44f3-8bfc-05a1be87ad9a" />

---

## 📈 Interactive Dashboards & Analytical Deep-Dives

Here is the breakdown of the interactive dashboard tabs developed to explore the market:

### 🏙️ 1. Global vs. US Salary Benchmarking (`salary analysis` tab)
* **Analysis**: Compares mid-point salaries across tech roles, separating US-based roles from the rest of the world.
* **Key Finding**: Roles like *Senior Data Scientist* command top-tier compensation globally ($155,000), while *Machine Learning Engineers* see a substantial premium inside the US ($150,000) compared to non-US locations ($101,029).

<img width="1353" height="600" alt="Screenshot 2026-06-25 111110" src="https://github.com/user-attachments/assets/60852aa6-4548-41f4-a65e-a48d4c770082" />

### 💰 2. ROI Correlation: Skills vs. Money (`salary vs skills` tab)
* **The Core Question**: *Do more skills equal more money?*
* **Visualization**: A custom **Scatter Plot with a Trendline** plotting `median salary` against `average skills requested`.
* **Key Finding**: A clear positive correlation exists. *Senior Data Engineers* require the highest breadth of stack (8.1 skills on average) and are rewarded with premium median salaries (~$147,500).

<img width="1352" height="595" alt="Screenshot 2026-06-25 111036" src="https://github.com/user-attachments/assets/abca4487-4f9d-4e54-bd5a-2afccee3569c" />

### 📊 3. Tech Stack Penetration (`skills job analysis` tab)
* **Analysis**: Tracks market frequency and likelihood of tool prerequisites.
* **Key Finding**: **SQL** (57% likelihood) and **Python** (54% likelihood) are foundational necessities across more than half of all data postings worldwide.

### 📊 4. High-Paying Skills vs. Market Demand (`skill salary analysis` tab)
* **Analysis**: Investigates the financial premium of technical skills weighed against their actual market frequency.
* **Visualization**: An advanced **Dual-Axis Combo Chart** combining clustered columns (`median salary skills`) with scatter markers (`skill likelihood`).
* **Key Finding**: Premium niche skills like **Spark** and **AWS** offer the highest median salaries ($140,000 and $135,000), but foundational skills like **SQL** and **Python** strike the best balance with high salaries (~$120,000+) and massive market penetration (over 54%).

<img width="1338" height="448" alt="Screenshot 2026-06-25 111131" src="https://github.com/user-attachments/assets/b6a10ee7-a481-4994-99b8-48add02653fe" />

### 🕹️ Dynamic Dashboard Walkthrough (GIF)
* **Interactive Slicers**: Filter data dynamically by Country and Job Title.

<img width="1350" height="560" alt="Animation R" src="https://github.com/user-attachments/assets/304353d9-1fdb-459f-9235-e90e3980c4c9" />

---

## 👤 Author
* **ayoubelguet** 
