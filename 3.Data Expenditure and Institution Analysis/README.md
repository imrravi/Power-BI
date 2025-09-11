**Data**: [Data](https://drive.google.com/file/d/1iX5Sw1h4GDgOKQEcj8Zqw0SH0UvZUU36/view)

We have two tables: **Expenditure and Data**

**Datasets Overview:**

1. **Expenditure Dataset:**

   - **Columns:**
     - country: The name of the country.
     - institute_type: Type of institution (e.g., all institutions).
     - direct_expenditure_type: The type of expenditure (e.g., public).
     - 1995, 2000, 2005, 2009, 2010, 2011: Direct expenditure values for respective years.

    - **Usage:** This dataset provides insights into the public expenditures of various countries over different years.

  2. **Data Dataset:**

     - **Columns:**
       - world_rank: Global ranking of the institution.
       - institution: Name of the institution.
       - country: Country where the institution is located.
       - national_rank: National ranking of the institution.
       - quality_of_education: Quality score of education.
       - alumni_employment: Alumni employment rank.
       - quality_of_faculty: Quality rank of faculty.
       - publications, influence, citations, broad_impact,
         patents: Various impact and research-related metrics.
       - score: Overall score.
       - year: The year of the ranking.
      - **Usage**: This dataset can be used to analyze the performance and global standing of educational institutions over the years.

**General Instruction:**

For each of the following tasks, create an appropriate visualization to represent your findings.
The type of visualization you select should best suit the data and analysis you are performing.

---

**Question and Solution:**

1. Calculate the average public expenditure for the year 2005 across all countries.

  - **average public expenditure for the year 2005 = CALCULATE(AVERAGE(Expenditure[Value]),Expenditure[direct_expenditure_type]="Public",Expenditure[Years]=2005)**

<img width="206" height="136" alt="1" src="https://github.com/user-attachments/assets/f1f700d3-2684-4128-ba96-022ba0a403ad" />

---

2. Calculate the total publications for institutions in the UK.

   - **Total publications for institutions in the UK = CALCULATE(SUM(Data[publications]),Data[country]="United Kingdom")**

   <img width="202" height="128" alt="3" src="https://github.com/user-attachments/assets/9863f895-d854-4eb6-964c-f51deeccece0" />

---

3. Filter the dataset to show only institutions with a world rank below 100.
   
 - **Top 100 Institutions = CALCULATE(DISTINCTCOUNT(Data[institution]),Data[world_rank]<101)**
   
   <img width="581" height="329" alt="2" src="https://github.com/user-attachments/assets/fae86d86-ebee-491a-888c-a788d6c38bf3" />

---

4. Calculate the total expenditure for all years for each country.
<img width="883" height="482" alt="4" src="https://github.com/user-attachments/assets/c9829ea2-190c-4991-9d55-015a1e823553" />

---

5. Write a DAX formula to ignore any filters on the year column and calculate the total
score across all years.

- **Total Score all Years = CALCULATE(SUM(Data[score]),ALL(Data[year]))**

<img width="422" height="302" alt="5" src="https://github.com/user-attachments/assets/489d4bc4-6f0a-4c50-aa1a-fcc7d65f9b28" />

---

6. Calculate the growth in expenditure for Austria from 1995 to 2000.

   - **Growth_Austria_1995_2000 = 
VAR Expend2000 =
CALCULATE ( SUM ( Expenditure[Value] ),
Expenditure[country] = "Austria",
Expenditure[Years] = 2000
)
VAR Expend1995 =
CALCULATE ( SUM ( expenditure[Value] ),
expenditure[country] = "Austria",
Expenditure[Years] = 1995
)
RETURN
DIVIDE ( Expend2000 - Expend1995, Expend1995 ) * 100**

<img width="251" height="100" alt="6" src="https://github.com/user-attachments/assets/2b6e9974-17c6-42ca-94f5-4a729b9219e1" />

---

7. Calculate the total expenditure for each country.
<img width="623" height="277" alt="7" src="https://github.com/user-attachments/assets/baef78a8-f4eb-4ec9-b464-03a83a867889" />

---

8. Create a report showing each visual in different sheets:

   - a). Break down the total patents of institutions by country and then by quality of
faculty. Analyze which factors contribute most to the number of patents across
different countries.

<img width="471" height="466" alt="8" src="https://github.com/user-attachments/assets/76c50c0c-8925-4629-b184-a49764702c47" />
<img width="866" height="453" alt="9a" src="https://github.com/user-attachments/assets/a63324d2-0f4f-47c7-a685-f5e9395b1e69" />
<img width="825" height="303" alt="8 3" src="https://github.com/user-attachments/assets/cb4bf135-a1ee-4018-8d4e-683256856b40" />

**Factors contributing most across countries**

- USA leads by a large margin, followed by China and Japan.
- Together, USA and China account for the biggest share of patents.
- Quality of Faculty 218 and 210 contribute the highest patent counts across countries.
- In the USA and China, these two faculty categories alone make up most of the patents.
- Other countries (UK, Italy, France, Germany, etc.) contribute fewer patents overall, and the effect of faculty quality is weaker compared to USA and China.

---

- b). Use the Q&A feature in Power BI to answer the question: "What is the total
publications and citations for institutions in the USA?" and display the results in a
table and bar chart format.

<img width="721" height="221" alt="9b" src="https://github.com/user-attachments/assets/7d9e7603-ada3-444e-8f11-dce029e6fd7c" />

---

- c). Display key metrics for the top 5 institutions by world rank, including fields
such as institution, country, score, and national rank.

<img width="425" height="211" alt="9c" src="https://github.com/user-attachments/assets/cd0327b6-3527-4d7c-aa99-2fc4235fd412" />

---

- d). Represent the distribution of direct_expenditure_type (e.g., public vs. private)
for the year 2011 across all countries. Highlight the OECD Average as a separate
segment.

<img width="1792" height="973" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/131aed59-fd06-4dde-9b0b-da014c6cc17a" />

---

#### Power BI Service Dashboard

<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/dfca237e-54b7-4877-83c7-5ec7540e960c" />


- For the complete measure, with data preprocessing and all previous steps, please download the file I have [provided](https://github.com/imrravi/Power-BI/blob/main/3.Data%20Expenditure%20and%20Institution%20Analysis/Data_Expenditure.pbix).

---
