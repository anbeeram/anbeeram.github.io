---
layout: page
title: "Visualizing Illinois License Data"
---


This project explores license data issued in the state of Illinois and presents two visualizations:  
(1) a bar chart showing the most common license types, and  
(2) a county-level choropleth map showing the geographic distribution of license counts.

---

## 🔗 Data and Notebook

- **[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv)**  
- **[The Analysis](https://github.com/anbeeram/anbeeram.github.io)**  

---

# 📊 Visualization 1: Top 5 License Types in Illinois

<iframe src="/assets/charts/chart1_top_license_types.html" width="100%" height="450"></iframe>

### **Explanation**
This bar chart displays the top five most common license types issued in Illinois. To create this visualization, the dataset was first filtered to include only rows where the `State` field equals `"IL"`. Then, the `License Type` column was aggregated using `value_counts()` to determine how many licenses existed within each category. A bar chart was chosen because it clearly compares categorical frequencies and makes it easy to recognize which license types appear more frequently. The x-axis encodes the categorical `License Type` field, while the y-axis represents the quantitative count. Color is also mapped to the license category, helping visually distinguish different types. Sorting the bars in descending order highlights the most common license types at a glance.

---

# 🗺️ Visualization 2: Illinois Licenses by County

<iframe src="/assets/charts/chart2_illinois_map.html" width="100%" height="650"></iframe>

### **Explanation**
The second visualization is a chloropleth map representing the number of licenses issued across Illinois counties. To prepare for this visualization, Illinois records were grouped by `County` to compute total license counts. Next, county names were matched with their corresponding five-digit FIPS codes from the official TopoJSON file provided through `vega_datasets`. Using FIPS as the key allowed us to join the license data with the county geometries. The map uses `geoshape` marks with a Mercator projection and a sequential blue color scale to represent variation in license counts. Counties with higher counts appear in darker shades. A separate outline layer ensures that *all* counties—including those with zero or missing data—are clearly visible through black borders.

---

# Interactivity

Interactivity enhances both clarity and exploration in this project. The county map includes hover tooltips that display the county name and exact number of licenses, allowing viewers to explore specific regions without cluttering the visualization. Additionally, the use of separate outline and fill layers ensures meaningful comparison across counties, even when some have no associated data. For deeper analysis, the project also includes an interactive dropdown (in the notebook) that allows the user to select any Illinois county and view the top five license types for that county. This parameter-driven interactivity makes the visualizations more engaging and supports county-level comparisons that would be difficult to see in a static plot.

---

# Files Included
- `chart1_top_license_types.html`  
- `chart2_illinois_map.html`  
- Jupyter notebook with all analysis steps  
- Supporting Python code for data cleaning and transformations  

---

If you have any questions about how these visualizations were created, please refer to the notebook linked above.

