---
layout: default
title: Homework 5
permalink: /hw5/
---

# Homework 5: Altair Visualizations

Here are two visualizations I created using the Building Inventory dataset.

#### Plot 1: Bar Chart of Building Usage by Status

This bar chart visualizes the number of state-owned buildings by their primary usage type, with color indicating whether a building is currently "In Use" or not. I used `ordinal encoding` on the x-axis because the usage categories are named categories with no inherent order. I used `quantitative encoding` on the y-axis for count, simply counting the number of buildings. The `color scheme` is categorical based on Bldg Status to clearly distinguish between active and inactive buildings, which I found to be interesting information. For data transformation, I grouped the data by Usage description and Bldg Status and then counted the occurrences. I also decided to drop the rows with missing values to make sure my visualization was clean. I also disabled max rows so the plot would work.

#### Plot 2: Interactive Scatter Plot of Building Size vs. Construction Year

This scatter plot shows the relationship between building size (in square footage) and the year that the building was constructed. The x-axis uses `quantitative encoding` for Year Constructed, and the y-axis uses `quantitative encoding` for Square Footage. Color is based on Agency Name to highlight variation across departments. I `filtered the data` to only include construction years within a buffer range of ±3 years of the dataset's min and max. I had to do this otherwise the plot came out way too big, and was less meaningful as a result. However, I also added the affordance of zooming using `.interactive()`, so viewers can see more specific years such as only the 20th century anyways. The `interactivity` I included was the ability to show buildings after a certain year constructed. As well, I made a widget so that the user can select specific Agency Names to only see on the plot. I was only able to include all agencies or one at a time, which I think is sufficient as users may not want to overcomplicate the plot for themselves.

### The Data  
[The Data](https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/building_inventory.csv)

### The Analysis  
[The Analysis](https://github.com/grantfross/grantfross.github.io/blob/main/Workbook.ipynb)

<div id="barChart"></div>
<div id="scatterPlot"></div>

{% raw %}
<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#barChart', '/assets/charts/bar_chart.json');
  vegaEmbed('#scatterPlot', '/assets/charts/scatter.json');
</script>
{% endraw %}
