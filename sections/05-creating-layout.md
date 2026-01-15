# Creating a Map Layout

You've made it to the final step of the map-making workflow for QGIS, which is transforming this map canvas into a final, sharable format. This is called a map **Layout**. 

Once your map looks exactly how you want it in the map canvas (layers turned on, colors set), go to the menu and select Project > New Print Layout.

Give your layout a name (e.g., "NYC Noise Complaints, Jan-March 2024").

A new window will open. This is your page layout workspace.

## Getting Oriented

Let's briefly talk about the new panels and toolbars available in the layout workspace. 

**The Left Sidebar: "The Toolbox"**

This is where you find the tools to add graphic items to your layout. Here are a few commonly used tools, starting from the top:

- Pan Layout: The white glove. Just like in the map canvas, this tool lets you pan within the print layout by clicking and dragging your cursor around the print layout.

- Zoom: The magnifying glass. Just like scrolling up and down on the mouse, this tool allows you to zoom in and out from the print layout.
   
- Select/Move Item: The white arrow. Use this to move or resize items in the layout (the map, the legend, etc.).

- Move Item Content: (Crucial!) The blue arrows inside a box. This lets you pan and zoom _inside the map frame_ without moving the frame itself.

- Add Map: The unrolling piece of paper with the green plus icon. This tool draws the **map frame** that will display your GIS data.

- Add Legend, Scale Bar, North Arrow: The "Big Three" map elements. Use these tools to add the map elements into your print layout by clicking and dragging to place and size them. 

**Panels**

Usually docked on the right-hand side, the Layout panels help with fine-tuning. It usually has two or three tabs, and you can pull them up by selecting View > Panels from the menu bar:

- Items Panel: Shows a list of everything on your page (Map 1, Legend, Label 1). It works like the layers panel in the main QGIS mapping window; you can select, lock, or hide layers here.

- Item Properties: This is the most important tab. When you click on an item (like your Legend), this panel changes to show settings for only that item (fonts, colors, columns, etc.).

- Layout Panel: General settings for the whole page, like export resolution (DPI) and world file settings.

**The Top Toolbars**: The Actions Toolbar, the Layout Toolbar, the Atlas Toolbar, and the Navigation Toolbar. 

These buttons handle the "big picture" tasks:

Layout Barar: The top left side of the toolbar contains tools for saving and exporting the print layout to Image, SVG, or PDF.

Atlas Bar: The top right side of the toolbar. Buttons that look like a world globe with a blue "play" button. They are usually greyed out. Use these if you are generating dozens of maps at once.

Navigation BAr: The bottom left of the toolbar. Standard magnifying glasses to navigate your paper workspace.

Actions Bar: The bottom middle of the toolbar, this row of icons helps with positioning map elements. You'll find tool like "Align Left," "Distribute Vertically," or "Bring to Front."

**The Print Canvas**  (The Middle)

This is the page on which you'll create the print layout by adding and arranging map elements to the page. Also in the middle are the **rulers**--located at the top and left. You can click and drag from these rulers to pull out **Guides** (red lines) to help you align your map elements perfectly with your print layout. Finally there is the **Status Bar** at the bottom. This displays the X/Y coordinates of your mouse on the page and the current zoom level of the paper.

If you're not sure what an icon does, you can hover over it with your cursor to display the name of the tool. 


Before we get started adding map elements to the print layout, here's what the final result will look like.

<img width="2550" height="3300" alt="NYC Noise ComplaintsImage" src="https://github.com/user-attachments/assets/98a4f40d-e9a8-434d-8fc9-dbf3e806985f" />

The title will be at the top, the legend will be at the left, the map frame will be in the bottom right corner, and the scale bar and north arrow will be small and in the bottom right corner as well. Keep this positioning in mind and use this image as a reference while you follow along. 

## Setting the Page Properties

To set the size of the paper layout, click **View** in the menu bar, hover over **Panels**, and click **Item Properties** if it's not already checked on. Then click once on the white page layout to bring up its properties options in the **Item Properties** window. 

Select Letter in the Size drop-down menu and Portrait for the Orientation. 

Now that we've set the page properties, it's time to add the map into the layout. 

## Adding Map Elements

### Adding and Adjusting a Map Frame

From the left-hand Toolbox toolbar, click the Add Map icon (it looks like an unrolling blank page with a plus sign). Click and drag a box on your print canvas where you want the map to appear. The map will automatically render in the map frame at the extent set in the mapping canvas. 

Let's display just Manhattan to center the three neighorhoods with the most noise complaints. 
To move the map extent: Use the Move Item Content tool to pan or zoom inside the map box without moving the box itself. Once you've got the map extent and the map frame positioned how you want them, lock the map frame layer by checking the box under the padlock icon in the **Items** panel. This will prevent any accidental adjustments or misclicks on the map frame. 

### Adding a Legend

To add a legend, click **Add Legend** from the Toolbox, then drag a box. This automatically generates a legend with all items from the **Layers panel** of the mapping window.  

In QGIS, the legend doesn't behave like a simple image you can stretch. If you drag the corners, you often just change the "window" size rather than the text size. To truly adjust it, you have to use the Item Properties panel.

With the legend selected in the print layout, open the Item Properties tab to see adjustment options for the legend. To remove layers you don't want shown, uncheck "Auto update" under Legend Items and use the plus/minus buttons at the bottom of the window. Let's rename the Neighborhood Complaints layer. With the Neighborhood Complaints layer selected under Legend Items, click the pencil icon in the row of buttons at the bottom of the window. In the text box that pops up, type "Number of Complaints Filed". Then click the blue back arrow.

Scroll down in th Item Properties window to view the other Legend properties options, like adjusting the text formatting and positioning. 

## Adding a Scale Bar and North Arrow.

To add a **scale bar**, Click Add Scale Bar in the lefthand Toolbox. Then, click and drag a box in the print layout where you want to scale bar to be placed. With the new scale bar selected, you can change its properties in the Item Properties panel. Change the scale bar units to **Miles**, then scroll down and expand the **Appearance** heading. Click the down arrow to the right of the primary fill color swatch and select **Red**, the third color from the right in the row of Standard colors. 

To add a north arrow, click Add North Arrow from the Toolbox. Then click and drag a box in the page layout to create a north arrow. Just like the scale bar, you can change its appearance in the Item Properties window. To change the icon, click the "arrows" folder and select a new arrow icon from the SVG images box that populates on the right. 

## Adding a Title and Data Source

The title is the first thing a reader looks at. It should be prominent and clear, usually at the top.

Click the Add Label icon on the left toolbar and drag a box across the top of your map to create a text box for the title. In the **Item Properties** panel on the right, look for the Main Properties text box. Delete the default "Lorem Ipsum" and type your title, "Neighborhoods with the Most Noise Complaints Filed in New York City, January to March,  2024". 

Now let's style the font. Scroll down to the Appearance section. Click the Font button to change the typeface, set the style to Bold, and increase the size (usually 24–36 pt for titles). Click the blue back bottom to go to the main options of Item Properties, and change the Horizontal Alignment to "Right."

### Knowledge Check

Using the same process, add the data source just underneath the title with the text, "_Dataset from NYC Open Data,  "311 Noise Complaints." Updated January 2025._" Make the font size 15 points. 

## Exporting Your Map

It's time to export it as an image file to share with your friends. 

In the **Layout** **toolbar**, select the Export as Image tool, which is the icon with the page with a mountain image and a rightfacing arrow. Set the file name to "NYC Noise Complaints 2024" and the save location to your First_Project folder. Click Save. 

Keep the image export options as they are, but check "Open File After Exporting" on. Click Save. 

Congratulations! You've created your very first map. This workflow of Adding and Organizing data from the Browser, Analyzing it with geoprocessing tools, Visualizing it with the symbology window, and building a Print Layout is the most standard workflow when working in any mapping platform. Now you'll be able to practice this workflow with data of your own. 

---

← [Visualizing Data](04-visualizing-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Main Page](https://github.com/goforanna/fundamentalsofQGIS/README.md) →
