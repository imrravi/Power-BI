**Objective:** To provide students with hands-on experience in using advanced Power BI
features to analyze and gain insights from product data, enhancing their data analysis and
visualization skills.

**Dataset:** [products.csv](https://docs.google.com/spreadsheets/d/1goWtJKUcRGTsCfnicwhr1DjjYiGoMF6lDJ5PfEk9Ppk/edit)

**Dataset Overview**:
The dataset consists of the following key columns:
- **ProductKey**: A unique identifier for each product.
- **ProductSubcategoryKey**: A reference key linking the product to a subcategory.
- **ProductSKU**: Stock Keeping Unit (SKU), a unique code for tracking inventory.
- **ProductName**: The name of the product.
- **ModelName**: The model’s name of the product.
- **ProductDescription**: A detailed description of the product.
- **ProductColor**: The color variant of the product.
- **ProductSize**: The size specification of the product (e.g., S, M, L, XL or numerical size).
- **ProductStyle**: The style category of the product (e.g., 0, M, U, W).
- **ProductCost**: The cost of the product for the company (manufacturing or procurement cost).
- **ProductPrice**: The selling price of the product.

**Question and Solution**

**Task 1:**

Create a custom column that calculates the profit margin for each product. Use the
formula: ProfitMargin = (ProductPrice - ProductCost) / ProductPrice. Name this
column "ProfitMargin". Add a conditional column to classify products as "High
Margin", "Medium Margin", or "Low Margin" based on their profit margin. Define the
thresholds: High Margin (> 0.5), Medium Margin (0.2 - 0.5), Low Margin (< 0.2).

**Steps:**

1. Add a Custom Column
- Click on Add Column → Custom Column.
2. Create the Profit Margin Column
- Enter the new column name: ProfitMargin.
- In the formula box, insert the calculation:
(ProductPrice - ProductCost) / ProductPrice
3. Add a Conditional Column for Profit Type
- Click on Add Column → Conditional Column.
- Enter the new column name: Profit Type.
4. Define the Conditions
- Column Name: ProfitMargin
- Operator: is greater than
- Value: 0.5
- Output: High Margin
5. Second Condition (Medium Margin):
- Click on Add Clause.
- Column Name: ProfitMargin
- Operator: is greater than
- Value: 0.2
- Output: Medium Margin
6. Else Condition:
- In the Else box, enter: Low Margin.
<img width="518" height="325" alt="1" src="https://github.com/user-attachments/assets/5fa9d1cd-a328-4c28-acb2-9836fef08409" />
<img width="688" height="323" alt="1 2" src="https://github.com/user-attachments/assets/7e6e73d5-fa8b-43e4-b163-4423f7de0ec2" />

**Task 2:**

Use the Q&A feature to find out "What is the average product cost by product color?"
and display the results as a bar chart.

**Steps**

1. Open Report View
- In Power BI, switch to Report View.
2. Access the Q&A Feature
- Go to the Visualizations pane.
- Click on the Q&A icon.
- In the Q&A text box, type: What is the average product cost by product color?
- Power BI will automatically create a visualization based on our data.
<img width="577" height="324" alt="2" src="https://github.com/user-attachments/assets/464473f6-5415-49a6-892b-971658c0d1c0" />

**Task 3:**

Create a decomposition tree to analyze ProductPrice by ProductColor and further by
ProductStyle. Identify key drivers for high prices.

**Steps**

1. Insert a Decomposition Tree Visual
- In the Visualizations pane, select the Decomposition Tree icon.
2. Add the Field to Analyze
- Drag the ProductPrice column into the Analyze box.
3. Add Fields to Explain By
- Drag the following fields into the Explain By box:
  - a. ProductColor
  - b. ProductStyle
<img width="281" height="322" alt="3" src="https://github.com/user-attachments/assets/c1ba6d01-1d9b-448c-8053-72337cd23fbd" />

**Task 4:**

Use the Key Influencer visual to determine which factors (e.g., ProductColor,
ProductSize, ProductStyle) influence high product prices. Provide a summary of your
findings.

**Steps**

1. Insert a Key Influencers
- In the Visualizations pane, select the Key Influencers.
2. Add the Field to Analyze
- Drag the ProductPrice column into the Analyze box.
3. Add Fields to Explain By
- Drag the following fields into the Explain By box:
  - I. ProductColor
  - II. ProductSize
  - III. ProductStyle
4. **Summary**

- **High Prices**: The biggest factor for a high product price is when the ProductStyle is U.
- **Low Prices**: The biggest factors for a low product price are when the ProductSize is 0.
<img width="587" height="319" alt="4" src="https://github.com/user-attachments/assets/bb7748b9-e69a-4d1b-aa0a-2a5c0ae834de" />
<img width="587" height="326" alt="5" src="https://github.com/user-attachments/assets/72e95039-a9f3-413e-88ce-4ca2ec04e093" />

**Task 5:**

Create a new column using the "Column from Example" feature to extract the first
letter from the product color column (eg: red should be R, etc). Create a table visual
to display the total product cost by product color. Highlight the costs column using
conditional formatting (highest costs in dark pink, medium costs in light pink and
lowest costs in white).

**Steps**

**A) Create a New Column Using “Column from Example”**

1. Open Power Query Editor
- From the Home tab, click on Transform Data
2. Select the Column
- Click on the ProductColor column.
3. Create Column from Example
- Go to Add Column → Column from Example → From Selection.
4. Type the Example Value
- In the new column, type the first letter of the product color.
- Power BI will detect the pattern and automatically fill in the rest of the rows.
  
**B) Create a Table Visual**

1. Insert Table Visual
- In Report View, click on Table from the Visualizations pane.
  
2. **Add Fields to the Table**

- Drag the following fields into the Columns area:
- First Character Color
- Product Color
- Product Cost
  
**C) Conditional Formatting for Background Color**

1. In the Format pane, scroll to Cell Elements.
2. Select Sum of ProductCost from the series.
3. Under Background color, click Conditional formatting.
   
**4. Set colors**:

- Lowest value → White
- Middle value → Light Pink
- Highest value → Dark Pink
<img width="488" height="200" alt="6" src="https://github.com/user-attachments/assets/7cc8f4e6-36be-41da-ae6c-989fe6dfa0cd" />

**Task 6:**

Set up bookmarks to save different views of your report. Create bookmarks for views
by ProductStyle, ProductColor, and ProductSize based on your own set conditions or
filters.

**Steps:**

1) **Create Charts**
   
- Create three charts showing ProductStyle, ProductColor, and ProductSize by Product Price.
  
2) **Add Slicers**
- From the Visualizations pane, add slicers for ProductStyle, ProductColor, and ProductSize.
  
3) **Insert Buttons**
   
  - Go to Insert → Add two buttons:
  - Bookmark
  - Clear All Slicers
<img width="592" height="333" alt="7" src="https://github.com/user-attachments/assets/0632e15e-ac72-4309-a5da-36bd6e4e6094" />

4) **Set Bookmark State**

- In slicers, select:
- ProductStyle → M, U
- ProductColor → Black, Blue
- ProductSize → L, M, S, XL

5) **Create a Bookmark**

- Go to View → Pane Manager → Bookmarks → Click Add.

6) **Assign the Bookmark to Button**

- In Report Canvas, select the Bookmark button.
- Click Format → Enable Action → Assign the created bookmark.
<img width="591" height="333" alt="7 2" src="https://github.com/user-attachments/assets/cd9e52fc-f350-44e0-9c48-6f58f8eaaf0c" />

**Task 7:**

Create a single row card to display the total number of unique products in the
dataset. Create a multi-row card to display the total product cost, total product price,
and average profit margin.

**Steps:**

1) **Create Measures**

- **TotalUniqueProducts = DISTINCTCOUNT(Products[ProductName])**
  
- **Average Profit Margin by Product = AVERAGE(Products[ProfitMargin])**
  
2) **Add a Card Visual**
   
- In Report View, click on Card from the Visualizations pane.
- Drag TotalUniqueProducts into the Fields section.

3) **Add a Multi-Row Card**
   
- Click on Multi-row Card from the Visualizations pane.
- Drag Product Cost, Product Price, and Average Profit Margin by product into the Fields section.
<img width="532" height="83" alt="8" src="https://github.com/user-attachments/assets/244795fd-b2c2-427d-a64a-6305f09ed22a" />

**Task 8:**

Add a reference line in a line chart to show the average product price over different
product styles.

**Steps:**

1. **Insert a Line Chart**

- In Report View, click on Line Chart from the Visualizations pane.

2)  **Add Fields**

- Drag Product Style into the X-axis field.
- Drag Product Price into the Y-axis field.

3)  **Add an Average Line**

- Open the Format pane.
- Click on Analytics → Average line → Add line.

4) **Customize the Line**

- Adjust line style, color, and transparency as needed.
<img width="580" height="246" alt="9" src="https://github.com/user-attachments/assets/84cc208e-5aee-4007-bcda-6174c1012e98" />

**Task 9:**

Identify and remove any duplicate product records in the dataset.

**Steps:**

1. **Open Power Query Editor**
   
- In Power BI, click Transform Data.
- Select the Products table.

2) **Select All Columns**
  
3) **Remove Duplicates**

   - Go to Home → Remove Rows → Remove Duplicates.

**Task 10:**

Create a Treemap to show product price for each color and subcategory. Also show
the top 3 subcategories based on profit (price-cost).

**Steps:**

1. Go to Report View. In the Visualizations pane, select the Treemap visual.
2. Drag ModelName to the Category field, ProductColor to the Details field, and the ProductPrice to the Values field.
<img width="583" height="323" alt="10" src="https://github.com/user-attachments/assets/02aebebc-a3a3-4f39-9266-6603b2bea37e" />

- The top 3 subcategories based on profit (price-cost).
  1) Create Measures
     
     - **Profit = SUM(Products[ProductPrice]) - SUM(Products[ProductCost])**
       
  3) Again, in the Visualizations pane, select the Treemap visual.
  4) Drag ModelName to the Details field and the Profit to the Values field.
  5) In the Filters pane, select ModelName → change the filter type to Top N → set Show items to 3 → drag the Profit measure into the By value field → click Apply filter.
<img width="586" height="309" alt="11" src="https://github.com/user-attachments/assets/d67c49ce-ebfa-4374-843d-3dbc3a297fcb" />

#### Dashboard

<img width="590" height="332" alt="12" src="https://github.com/user-attachments/assets/966a972c-1241-48f8-b3ae-fb9588f58d87" />
