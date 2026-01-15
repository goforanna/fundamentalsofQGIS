# Visualizing Data
Congratulations, you've made it to the fun part of mapping! Playing with data visualization in GIS is where personality, creativity, and design really get a chance to shine. It is how data transforms into a compelling narrative. We will do this by adjusting the **symbology** of the Neighborhood Complaints layer. Symbology is the use of graphic elements (color, size, shape, transparency) to represent geographic features on a map. While a raw dataset might contain coordinates and numbers, symbology is what turns that data into a visual story. It determines how a point, line, or polygon appears to on the map based on its attributes.

Currently, the Neighborhood Complaints layer is symbolized as a single color. In this section you will change the symbology so that the polygons--the neighborhoods--vary in color according to the number of complaints filed within each group.  

Make sure that the Neighborhood Complaints layer is at the top of the drawing order.

## Applying Graduated Symbology to a Polygon Layer

In order to adjust the symbology of the Neighborhood Complaints layer, right-click the layer in the Layers Panel and select Properties. This opens the Layer Properties window. Select the "Symbology" tab from the left hand side. 
This brings up the Symbology window. There are many options to choose from when styling a layer, and this window can be disorienting. 
<img width="847" height="795" alt="Screenshot 2026-01-13 at 1 40 37 PM" src="https://github.com/user-attachments/assets/a37255c2-2f4a-4d09-9934-baf203e151fe" />
At the very top is a drop-down menu that lists the primary symbology styles. Currently, "Single Symbol" is selected. Expand the drop-down menu and select "Graduated." Notice that this changes the stylization options that are available below. 

**Graduated symbology** is used to show quantitative differences between features by placing them into classes (or "bins") and assigning a specific visual style to each class. Instead of every single feature having a unique size or color, the data is grouped into ranges (e.g., low, medium, and high number of noise complaints).

First, we need to determine the attribute field that the polygons will be graduated by. Click the empty drop-down box to the right of "Value," and you'll see just the fieldnames for just the numeric attribute data in the Neighborhood Complaints layer. 

Select "NumComplaints."

### Classification Mode 

Next, we must select the mode of classification and the number of classes. This sets the size and number of the bins QGIS will sort each feature into. Class Mode is the statistical rule used to group data into different categories. 

The mode you choose determines exactly where the "breaks" occur--deciding which number of complaints is considered minimal, medium, or a lot. 


| Mode  | How it Works | Best Used For |
| ------------- | ------------- | -------------
| Natural Breaks (Jenks) | The computer looks for ""gaps"" and ""clumps"" in your data to find the most natural groupings.| Data that is unevenly distributed or has clusters (the GIS ""default"") |
| Equal Interval | Divides the range of data into equal sized chunks (e.g., 0–25, 25–50, 50–75). | Familiar ranges like temperature, percentages, or grades. |
| Quantile | Places an equal number of features into each class (e.g., 20% of features in each of 5 classes). | Relative rankings; showing the "top 10%" or "bottom 20%." |
| Standard Deviation | Shows how much a value varies from the average (Mean). | Highlighting outliers or seeing what is "normal" vs. "extreme." |
| Manual / Pretty Breaks | You (the human) type in the specific numbers you want for the breaks. | When you have legal or specific industry cutoffs (e.g., Poverty Line).

Most cartographers recommend 5 to 7 classes. Using 15 classes makes it impossible for the human eye to distinguish between the subtle shades of color.
Increase the number of classs to 6 on the right side of the Symbology window. 

Adjust the Symbology window so that both the window and the map canvas are visible. Then, select Natural Breaks and click **classify**. 6 classes populate in the middle of the Symbology window. Click Apply. Notice that the map canvas as re-rendered to display the polygons in colors that correspond to the number of complaints filed in each neighborhood.

Now let's customize the stylization of the graduated symbology.

## Stylizing the Symbology

Click the drop-down arrow on the right hand side of the Color Ramp. Hover over "All Color Ramps" and select **Oranges**. 

Next we will change the weight of the border lines between each polygon. Single-click the white color swatch in the first class. Then, hold the shift key down and double-click the dark orange swatch in the last class class. This opens up the **symbol selector.** 

Because we selected all of the swatches by holding down the shift key, any adjustments made in the **symbol selector** will apply to all of the classes. 

Click "Simple Fill" in the Style Tree at the top of the window. This opens new options for adjusting the Symbol Layer type. Simple Fill is currently selected. Click the drop-down menu for Symbol layer type and explore how the options change when selecting different Symbol layer types. When finished, re-select Simple Fill. 

Adjust the Stroke color by clicking the drop-down arrow to the right of the color swatch. Select the orange hue from the standard colors row, the last swatch on the right. 

Now adjust the Stroke width to 0.100000 millimeters. Click Ok to close the Symbol Selector. 

Click Apply to apply the style changes to the map canvas. Close the Symbology window. 

## Creating Labels

The final step in visualizing the data is to label the neighborhoods with the highest number of noise complaints. These are the 3 darkest polygons in the northwest corner of Manhattan. 

Make sure that Neighborhood Complaints is highlighted in the Layers panel. In the Layers tab of the menu bar, click Labeling. This opens the Label Styling tab of the Layer Properties window. 

Click the drop-down menu that reads "No Labels" to expand the labelling options:

- Single Labels: This is the most straightforward method. Select one column from your attribute table, and QGIS labels each feature in that layer with its attribute data.
- Rule-based labeling: Rule-based labeling applies labels only to features that meet certain user set requirements.
- Blocking isn't a labeling method, but rather a setting that tells QGIS: "Do not let any other labels overlap the features in this layer."

Select **Rule-based Labeling**. 

This brings us to the rule directory that will list the rules applied to the labels. It's empty now. We're going to create one rule to label features with. 

Click the green plus icon at the bottom of the Layer Styling window. 

In the **Description box**, type "Features with most complaints."

Next, click the purple sigma icon (Σ) to open the Expression Builder. Here's where we will define the rule. Since we want to label only the three features with the most noise complaints, we're going to build a rule that selects features with NumComplaints of 2199 or more. 

In the blank expression box, type the following:

 "NUMPOINTS" >= 2199

Click OK to close the Expression Builder. 

Next, under the Labels heading, change the Value to **ntaname**. Select the **buffer tab**, represented by abc surrounded in blue. Check "Draw text buffer". 

Click Apply. 

Now only North Harlem, the Central Upper West Side, and Lincoln Square are labelled. 
 

<img width="1020" height="661" alt="Screenshot 2026-01-14 at 5 01 42 PM" src="https://github.com/user-attachments/assets/4287c1db-2e78-4f8b-a778-ee8f64363548" />

Before we move on to creating a Print Layout, remove all other layers from the **Layers Panel** so that only the Neighborhood Complaints layer is in the drawing order.  

---

← [Analyzing Data](04-analyzing-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Creating a Layout](05-creating-layout.md) →
