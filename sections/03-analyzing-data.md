# Analyzing Data
Now we have a map of each noise complaint filed in New York City from January to March of 2024. But because there are so many point features, this map can hardly tell us anything about where the most noise complaints are filed. In order to figure that out, we need to aggregate our point data to the New York City NTA polygons. 

## Joins and Spatial Joins
Now that we have an appropriate spatial layer, we need to count up how many complaints fall within each neighborhood. To do this we’re going to do something called a **Spatial Join**. **Joins** are the bread and butter of GIS. There are two kinds of join processes in GIS. The first is just a regular ‘**join**,’ and it joins fields from one layer to another based on shared attributes. 
For example, say we have a two different files. One has data on the Names and Addresses of your family members. The other file has data on the Names, Birthdays, and Allergies of your family members. Because both files have data on Names, you can use the join function to append the Birthdays and Allergies attribute data to the layer with the Address data. 

A **spatial join** is just a bit different, but the difference is important. A spatial join is based on spatial relationships rather than attribute values, and it joins the two layers by comparing their geolocation. 

We’re going to do a spatial join today, because we want to compare the locations of the noise complaints with the locations of the neighborhoods. 

### Building a Spatial Index

Since our Complaints point dataset is so large, we first need to create a **spatial index**. A spatial index is A spatial index is a specialized data structure that allows a QGIS to efficiently categorize features based on their location on a grid. Having a spatial index for our Complaints layer will allow our spatial join to run much more quickly. Without an index, the spatial join could take hours to complete. 

To build a spatial index of our Complaints layer, right click the Complaints layer, and select Properties. Click the Source tab of the Layer Properties Window. Then, under the Geometry heading, select the "Build Spatial Index" button. Close the Layer Properties window. 

### Counting Complaints by Location

There are multiple tools to use to do a spatial join in QGIS, the most common one being "Join by Location." But since we also want to _count_ the points, we're going to use a tool called "Count Points in Polygon." This tool is located in the Processing Toolbox. This toolbox is not currently visible right now, so we’re going to have to pull it up.
Go to View > Panels > Processing Toolbox. Dock the Processing Toolbox underneath the Browser in the right corner. 

In the processing toolbox is a catalog of the various geoprocessing tools QGIS has to offer. There are a lot. Spend a few seconds opening and closing the carrots to see all the kinds of tools and get a sense of how they’re organized. 

When you're ready, search for "Count Points in Polygon," which will appear under the Vector Analysis tab. 

In the Count Points in Polygon window, select the neighborhoods layer from the Polygons drop-down menu. Then, select the Complaints layer from the Points drop-down menu. Under "Count field name" type, "NumPoints". Click Run. Even with a spatial index, this may take several minutes. Go stretch your legs!

Once the geoprocessing tool has finished running, a new polygon layer named Count will be added to the top of the drawing order. This layer is an amended copy of the Neighborhoods layer. Rename the layer "Neighborhood Complaints." Open the attribute table of this layer and scroll to the right end of the table to confirm that the NumComplaints field has been created and is populated with the number of noise complaints that fall within each neighborhood.

Close the Attribute Table. 





