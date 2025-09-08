##### Data: [Sales_Data](https://drive.google.com/file/d/10kmZayKtKYv7BByv9djEAZYeDCrf0AjY/view)
We have three tables: **Customer, Product, and Sales.**

**Question and Solution**

**Task 1:**
- Round the 'Price' column in the Product dataset to the nearest integer for simplicity.
- Split the 'Customer' column in the Customer table into two columns: 'FirstName' and
'LastName'.

**Steps:**

**1.(a)**
1. Select the ‘Price’ variable.
2. Click on Transform ➡️ Rounding ➡️ Choose Round Up.
<img width="955" height="365" alt="1" src="https://github.com/user-attachments/assets/3eeee1cc-fe40-4028-a551-9c3363cdd45e" />

**1.(b)**
1. Select ‘Customer’ vatiable.
2. Transform ➡️ Split Column ➡️ By Delimiter.
3. Choose Space from select and select Left-most delimiter ➡️ Ok.
4. They will split into two variables.
5. Rename both variables.
<img width="956" height="282" alt="2" src="https://github.com/user-attachments/assets/fa79cd85-1b87-4a4c-9fac-cf4d284c580f" />

---

**Task 2:**

- Convert all entries in the 'Category' column in the Product table to uppercase.
- Replace all occurrences of 'unemployment' with 'Unemployed' in the 'Profession' column of the Customer table.

**Steps:**

**2.(a)**
1. Select ‘Category’ variable.
2. Transform ➡️ Format ➡️ UPPERCASE.
<img width="959" height="290" alt="3" src="https://github.com/user-attachments/assets/a4a2bd58-9101-463f-b010-cac59c13bd5f" />

**2.(b)**
1. Select ‘Profession’ column.
2. Home ➡️ Replace Values.
3. In Value to find enter ‘unemployment’ and replace with ‘Unemployed’.
4. Click Ok.
<img width="763" height="286" alt="4" src="https://github.com/user-attachments/assets/f94c1488-4082-470c-ab8c-6e99c806a155" />

---

**Task 3:**
- Ensure all columns in the datasets have appropriate data types, e.g., 'Date' column as Date type, 'Price' as Decimal type.
- Identify and replace any inconsistent values in the 'Size' column of the Product dataset to ensure uniformity (e.g., replace "medium" with "Medium").

**Steps:**
  
**3.(a)**

All columns in the datasets have appropriate data types.
  
**3.(b)**
1. Select the ‘Size’ variable.
2. Home ➡️ Replace Values.
3. In Value to find enter ‘medium’ and replace with ‘Medium’.
4. Click Ok.
<img width="640" height="285" alt="5" src="https://github.com/user-attachments/assets/8417e88b-3faf-4c6f-bf6c-ad011865b986" />

---

**Task 4:**
- Create relationships between the tables using 'CustomerID' and 'ProductID' as keys.
- Clean the data by removing any duplicate entries in the Customer and Product tables.

**Steps:**
  
**4.(a)**
1. Click on model view.
2. From the Product table, drag ProductID to the ProductID field in the Sales table. Then, from the Sales table, drag CustomerID to the CustomerID field in the Customer table.
3. Set a one-to-many (1:M) relationship from Product to Sales by selecting the appropriate cardinality. Then, set a many-to-one (M:1) relationship from Sales to Customer by selecting the appropriate cardinality, and click Save.
<img width="811" height="256" alt="6" src="https://github.com/user-attachments/assets/68c2cc34-d3ec-462d-bad9-aa7a572e5596" />

**4.(b)**
1. Click Transform Data to open the Power Query Editor.
2. In the left panel, select the Customer table.
3. Select all columns.
4. Go to the Home tab and click Remove Duplicates.
5. Repeat the same process for the Product table.
---

**Task 5:**

**Sales by Category:**
- Create a chart showing total sales (TotalPrice) by product category.
- Customize colors, refine the title, and add data labels for exact sales amounts.

**Sales Percentage by Category:**
- Create a chart showing the percentage share of sales (Price) for each product
category.
- Keep the chart compact and easy to understand.

**Steps:**

**5.(a)**

1. In Power BI Desktop, click on Report View.
2. In the Fields pane, click on the Sales table.
3. Right-click the Sales table and select New Measure.
4. Enter the following formula:
**TotalSales = SUMX(Sales, Sales[Quantity] * RELATED(Product[Price]))**
5. For visualizations, select the Clustered Column Chart.
6. Drag Category from the Product table into the X-Axis field.
7. Drag the newly created TotalSales measure from the Sales table into the Y-Axis field.
7. Go to Add to your visual ➡️ Size and style ➡️ Columns ➡️ customize the colors.
8. Click on Format ➡️ select Title ➡️ edit the text.
9. Click on Format ➡️ Data Labels ➡️ turn them On.
<img width="617" height="362" alt="9" src="https://github.com/user-attachments/assets/cb64bf5e-8a8c-4616-abdd-82d45db59898" />

**5.(b)**

1. click on Report View.
2. From the Visualizations panel, select the Donut Chart.
3. Drag Product[Category] into the Legend field.
4. Drag TotalSales into the Values field.
5. Click on Format Visual.
6. Go to Detail labels ➡️ Label contents ➡️ select Percent of total.
<img width="410" height="292" alt="10" src="https://github.com/user-attachments/assets/4df08f31-bd9c-40bc-86e5-7471c5c04ac0" />

---

##### Dashboard
<img width="592" height="332" alt="11" src="https://github.com/user-attachments/assets/686b2dca-892a-42a0-a9aa-b6785d037e05" />
<img width="429" height="314" alt="12" src="https://github.com/user-attachments/assets/ee2687d7-4bfe-485f-b3d3-e758bf422491" />
<img width="590" height="330" alt="13" src="https://github.com/user-attachments/assets/6b66d5a7-49c2-422a-ab35-298371732259" />

---




   
