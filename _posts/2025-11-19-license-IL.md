---
layout: page
title: "Visualizing Illinois License Data"
tags: [Illinois, Data Visualizitation, ]
style: fill
color: secondary
description: This is a blog post to get you started.
---


---

## Data and Notebook

- **[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv)**  
- **[The Analysis](https://github.com/anbeeram/anbeeram.github.io/blob/main/assets/notebooks/Workbook.ipynb)**  

---

# 📊 Visualization 1:  Illinois Licenses by County

<iframe src="/assets/charts/chart1_top_license_types.html" width="100%" height="650"></iframe>

### **Explanation**

This map shows how many licenses are located in each Illinois county by using different shades of color and displays the exact count when you hover over a county. Counties with darker shades have more licenses than counties with lighter shades.

To build this map, I grouped all the Illinois license records by county and calculated the total number of licenses in each one. Then I matched each county name to its official FIPS code (a five-digit identification number) by using information from a TopoJSON file, since the mapping tool requires FIPS codes to display data on county shapes. 

Once I added the correct FIPS codes to my summary, I merged the license counts with the county boundaries so the map could show the right color for each region.

---

# 📊 Visualization 2: Top 5 License Types in Illinois by County

<iframe src="/assets/charts/chart2_illinois_map.html" width="100%" height="650"></iframe>

### **Explanation**

This chart displays the five most common types of licenses found in Illinois by counting how many licenses belong to each category. It makes it simple to see which license types are most popular in the data. It makes it simple to see which license types are most popular in a given county.

Each bar has its own color to make the different license types easy to tell apart. The colors help us distinguish between categories but do not represent any numeric information on their own.

Before creating this plot, I cleaned the dataset by removing null values in the key fields, then filtered the data to include only records where the state was “IL,” since the goal was to focus only on Illinois licenses. 

There's a dropdown menu at the top where you pick a county. When you choose one, the chart updates to show only that county's data.
To make this work, I created a parameter called county_param that stores whichever county you selected. Then I used a transform_filter to keep only the rows where the county matches what you picked. After that, the chart ranks the license types in that county and shows you the top five in the bar graph.
---

# Interactivity

The map includes hover tooltips that let users explore the data without making the visualization look cluttered or overwhelming. Additionally, a dropdown menu in the analysis tool allows users to select any county they want and immediately see which license types are most common there. These features make the analysis feel more helpful for users to focus on the specific information.

---

# Files Included
- `chart1_top_license_types.html`  
- `chart2_illinois_map.html`  
- Jupyter notebook with all analysis steps  
- Supporting Python code for data cleaning and transformations  

---

If you have any questions about how these visualizations were created, please refer to the notebook linked above.

