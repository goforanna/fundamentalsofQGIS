# Adding and Organizing Data
Now its time to add our own data into the map. 

We have two sets of spatial data for this project: 

## A shapefile of the New York City Neighborhood Tabulation Areas (NTAs): "geo_export_941b0fdf..."
- This file was downloaded from [NYC Open Data](https://data.cityofnewyork.us/City-Government/2020-Neighborhood-Tabulation-Areas-NTAs-/9nt8-h7nd/about_data). NTA boundaries are used for statistical purposes only and may not reflect all local understandings or definitions of NYC neighborhoods. While they use familiar names, they aren't official neighborhood boundaries.


## A CSV of 311 Noise Complaint Data with x,y coordinates: "311_Service_Requests_from_2010_to_Present"
- Even though the file name says all service requests 2010 to Present, the data only contains noise complaints from the first three months of 2024.
- The main dataset for this workshop is from [NYC Open Data](https://data.cityofnewyork.us/Social-Services/311-Noise-Complaints/p5f6-bkga/about_data) collected from NYC’s 311 call center. Some of the most popular complaints filed through 311 are about parking, noise, garbage, etc. We’ll be working with just the noise complaints in this workshop.

  The 311 dataset is a great resource for anyone studying New York City. However, it is important to remember that 311 data tracks complaints, not necessarily the real conditions themselves. Because the data relies entirely on people choosing to speak up, it carries a natural bias toward the habits of those who complain. While 311 is a powerful tool for understanding city life, we must look at it critically, recognizing that this dataset shows us what people are bothered by noise by rather than a real picture of the noisiness of the city.
   
## Adding Data: Shapefiles

We'll start by adding the two shapefiles and will deal with the CSV in a bit.

In the Browser panel, expand the Data subfolder in the First_Project folder. Add the "geo_export_941b0fdf" file into the map by double clicking. 

QGIS randomly assigns a fill color to the borough features, and we can change the color later. 
Notice how the Neighborhoods layer was added to the Layers panel on top of the basemap. 
Rename the Neighborhoods layer by right-clicking the file name in the Layers panel > selecting 'Rename Layer' > typing in 'NYC Neighborhoods' > and hitting enter. 

## Data Layers

Since we added the NYC Neighborhoods layer most recently, QGIS automatically places the data as the topmost layer in the map canvas above the base map, and this layering correlates with the ordering in the Layers panel. This ordering is called the **drawing order**.  

Click the checkmark to the left of NYC Neighborhoods. This checkmark toggles the layer visibility. It does not remove the data from the map project, it just tells QGIS to not render the data in the canvas so that you can see the layers underneath in the map canvas. 

Now turn the visibility of NYC Neighborhoods back on. You can change the drawing order of the data layers by clicking and dragging the layers up or down in the Layers panel. Play with the drawing order of the two layers, and notice how the map canvas changes to reflect the drawing order. 

When you're done experimenting, place the OpenStreetMap layer at the bottom of the drawing order. 

To fully remove data from the project, right-click the layer you want to remove and select 'Remove Layer.' Right-click the NYC Neighborhoods layer. Before we select remove, let's pause and go over some of the other options accessible with a right-click in the Layers panel: 

- **Zoom to Layer** zooms and pans the map canvas to bring the selected layer into view.
- **Copy Layer** adds a temporary copy of the layer to your clipboard so you can paste it into other projects.
- **Duplicate Layer** creates a copy of the layer within the same project and adds it below the original layer in the drawing order. 
- **Open Attribute Table** opens the attribute table of the layer to let you review or edit it. We'll talk more about attribute tables later.
- **Set Layer Scale Visibility** allows to you set a particular scale at which QGIS will render the layer in the map canvas. This can be useful for layers that have extremely local data which might obscure other map features at a small scale. 
- **Properties** opens the Layer Properties window, which is where you can review the metadata and access even more tools for data analysis and visualization.

Now we can remove the NYC Neighborhoods layer. Click Remove Layer. 

## Knowledge Check
Add the NYC Neighborhoods layer back into the map from the **Browser**. 

<Secret>
Navigate the **Browser** panel to the Data folder of First_Project. Drag and drop "geo_export" into the map canvas.
</Secret>


## Setting A Coordinate Reference System

Remember from the previous workshop that all maps are projections, and they should be projected differently depending on a map's purposes and goals. The basemap that we added, OpenStreetMaps, is meant to be useful at a world scale and local scales, so it uses a **Coordinate Reference System** (CRS) that is applicable to world scales, but not particularly accurate for our New York-based project. As a reminder, a CRS defines how the two-dimensional or three-dimensional coordinates of a location on Earth are mapped onto a flat surface, these are often called projections. 

We're going to change the CRS to one that's useful for this project. 

In the bottom right corner of the interface, you'll see an icon of a globe intersected by a plane with text to the right that most likely says something like "EPSG: 3857." Hover over this button to see information about the current CRS applied to the map project. The EPSG code is a numeric identifier that uniquely represents a specific CRS or projection. The code helps standardize the use of projections across different GIS software and systems. To the right of the EPSG code is the name of the CRS. If the EPSG is 3857, the CRS is the Web Mercator projection. 

Click the **CRS button** to open the **CRS Tab** in the Project Properties window, where you can explore and change the CRS for this project. 

<img width="826" height="586" alt="Screenshot 2025-01-21 at 11 22 56 AM" src="https://github.com/user-attachments/assets/3fa8f474-444a-444c-a274-795cce80fe1b" />

At the top of this window is a Filter Bar where you can search for a particular CRS. This filters the catalog of CRSs below. Under the Filter Bar is a catalog of recently used CRSs, which has the current CRS highlighted. Next down is the catalog, which is organized first by CRS types: Compound, Geocentric, Geographic, or Projected. We need a Projected CRS. Expand the Projected folder. Here you'll see subfolders of many different types of projections. And these subfolders expand to show the different projections of that type. Browsing these projections can be quite overwhelming, especially if you aren't familiar with all the different projection types. That's ok! At the bottom of the window is projection information and projection preview, which offer useful information on how the selected projection works and what its useful for. 

Spend a few moments exploring the catalog, expanding the subfolders and clicking various projections to see how the properties and previews change for each projection. (Don't click apply or OK). 


Now its time to find the projection we need, which is **NAD 1983 (2011) StatePlane New York Long Isl FIPS 3104 Ft US**. Instead of browsing through the whole catalog to find this projection, use the Filter Bar to pare down the projections that display in the catalog. Begin to type 'NAD83' into the Filter Bar, and notice that the catalog filters accordingly, but there are still so many projections to choose from! Continue to type the rest of the projection name into the Filter Bar, and soon you should be left with just a few projections. 

Select **NAD_1983_2011_StatePlane_New_York_Long_Isl_FIPS_3104_Ft_US**. 

Notice that in the projection preview, the area in the red box is the projection's area of accuracy, and the purple box represents the current view in our map canvas. Click Apply. 

A Dialog Window will open asking you to decide how to transform the data from the current projection (Mercator) to the selected projection (NAD83). Explaining this transformation is a bit beyond what you need to know for most projects, so usually you'll select the first operation, which is bolded to indicate the recommended option. Select the first operation, click OK to close the Dialog Window. Then click OK in the CRS Properties Window to close the window. It may look like not much has changed, but the layers have adjusted at a minute scale to conform to the NAD projection.   

## Adding Data: CSVs

So far we have one polygon shapefile (NYC Neighborhoods) and a basemap (OpenStreetMap) added a layers into the map. It's time to add our Noise Complaints data, which is held in the CSV file. Drag the '311_Service_Requests' file from the Data folder in the Browser into the map canvas. 

Nothing about the map changed! That's because CSVs are not formatted as spatial data, they're just tabular data. Notice that even though nothing changed in the map canvas, the Noise Complaints file was added into the drawing order as a **Table**, marked with a table icon.  
## Inspecting the Attribute Table

We'll inspect the tables of our two data formats to see their differences. Open the NYC Neighborhoods attribute table by right-clicking the layer in the Layers Panel and selecting **Open Attribute Table**. The layer's attribute table will open in a new window. This is almost as simple as an attribute table will ever look. There are 11 fields, indicated by the eleven columns with field names at the top of the table. Scroll to the bottom of the table and not that there are 262 rows, indicating that there are 262 features in this layer. Each row contains data for one feature--one neighborhood. So, there are 262 rows holding the data for the 262 polygon features, which are the 262 neighborhoods in New York City. The last two fields, shape_area and shape_leng hold the data that tells QGIS what the placement and shape of each feature is. These should almost never be edited. 

If you need to edit other data--let's say there was a typo in one of the borough names, you can toggle editing mode by clicking the **pencil icon** in the top left corner of the attribute table window. Click the pencil icon and hover over the buttons to the right of the pencil to briefly learn about the tools for editing the Attribute Table. Be sure to not click any of these tools. Turn off editing mode by clicking the pencil icon again.  Close the Attribute Table. 

Open the 311_Service_Requests Table. Just like the Neighborhoods attribute table, this table has fields in the columns, and has entries for every noise complaint in each row. Scroll to the right to explore the different fields, taking note of Agency, Descriptor, X Coordinate, and Y Coordinate. Close the table.


## Converting a CSV to Point Feature Layer
We are going to use the data in the X Coordinate and Y Coordinate fields to convert this CSV into a point feature layer. 

To do this, we will use just one of the many, many, many tools available for data management in QGIS. It's likely that your future projects will require that you do some learning on your own to figure out which tool is right for the job at hand. But for this workshop, we will use just a few tools. 

Click **Layer** in the menu bar, then hover over **Add Layer**. To the right, select **Add Delimited Text Layer**.  This tool allows you to convert delimited text files into feature layers, which is exactly what we need. 

In the Data Source Manager Window that opens, click the ellipses in the top right corner to navigate to the 311_Service_Requests CSV in your file explorer. 

In the Layer name field, type: 2024 Noise Complaints Jan - Mar.
Under Geometry Definition, select Point coordinates. Click the drop down arrow in the X field box. Here is where we tell QGIS what field in the CSV to use as X Coordinates. Scroll to and select "X Coordinate (StatePlane)." Do the same thing for the Y field, selecting "Y Coordinate (StatePlane)" instead. 
Make sure that:
- the selected file format is CSV
- 'First record has field names' is checked
- the Geometry CRS is NAD 1983 State Plane NY Long Isl FIPS 3104 US Ft. 

Click Add and Close the window. 

<img width="1341" height="857" alt="Screenshot 2025-01-21 at 2 36 04 PM" src="https://github.com/user-attachments/assets/afbe03d9-eab4-4ca4-abe0-8e1ec136381a" />

Open the Attribute Table of the newly created Noise Complaints Layer to see that the fields and attributes were accurately converted and that there are no unexpected NULL values. Close the Attribute Table.

Remove the 311_Service_Requests CSV table from the Layers panel. 

## Exporting Feature Layers

Before we go further and play with how this data is visualized, we should export this point feature layer for future use. An important thing to note that while we continue to change and visualize this data in the map project, the original files housed in the browser haven't changed. So, while we have the Noise Complaint layer in the map project, it doesn't exist in our browser. If we delete it or want to use it in a different project, we would have to create this layer over again. Instead, we can export the layer as a standalone file housed on your computer and accessible through the browser. 

To do export the Noise Complaint feature layer, right-click 2024 Noise Complaints and hover over **Export**, then select **Save Features As**. 

Select **ESRI Shapefile** from the Format Dropdown box. 
For File Name, use the ellipses to navigate to the data folder for this project, and name the file 2024NoiseComplaints. 
Select **point** for the **Geometry Type**. 
Uncheck 'add saved file to map' and click Save. 

Now expand the Data folder in the Browser to see that the point feature layer has been saved into the folder. 

Later on in this workshop, we are going to combine the NYC Neighborhoods layer with the Noise Complaints layer. In order to do that, we need to make sure both layers are using the same Coordinate Reference System. Let's check the Coordinate Reference System of the NYC Neighborhoods layer by right-clicking the layer in the Layers panel, then hovering over "Layer CRS." At the top of the new drop-down menu is the Reference System that the file was created in, which is **WGS 84**. This is different from the Noise Complaints layer. The x,y coordinates used to plot the points in the Noise Complaint layer were collected in **NAD 1983 State Plane NY Long Isl FIPS 3104 US Ft**. 

To ensure that these layers can be combined, we're going to the NYC Neighborhoods layer as a new layer with a **NAD 1983 State Plane NY Long Isl FIPS 3104 US Ft** as its Coordinate Reference System.

## Knowledge Check
Follow the same steps for exporting the NYC Neighborhoods layer as you did for exporting the Noise Complaints layer, with a few adjustments. 
- Name the file "NYC_Neighborhoods_NAD"
- Select **polygon** for the "geometry type
- Select NAD 1983 State Plane NY Long Isl FIPS 3104 US Ft for the CRS.
<Secret>
  <img width="592" height="661" alt="Screenshot 2026-01-14 at 12 14 48 PM" src="https://github.com/user-attachments/assets/055483c8-6caa-4454-8e03-8ed21f423485" />
</Secret>

Notice that the re-projected NYC Neighborhoods NAD layer has been added to the map at the top of the drawing order. Move this layer below the Noise Complaints layer. 

Remove the original NYC Neighborhoods layer so that there are only three layers in the Layers panel: 
1. 2024 Noise Complaints
2. NYC Neighborhoods NAD
3. OpenStreetMap
