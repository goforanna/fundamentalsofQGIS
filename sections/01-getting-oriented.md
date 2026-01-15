# Getting Oriented in QGIS
## Navigating the User Interface
Open QGIS and you'll see the user interface. We'll briefly go through each area of the interface before creating a new project. The **Browser** and **Layers** panels are docked on the left side, and at the top are **Menu Bar** and the **Toolbars**. At the bottom is the **Status Bar** and the **Locator Bar**. The rest of the space is the **map canvas**, which at initialization is populated by thumbnails of recent projects, the news feed, and project templates. 

<img width="900" height="461" alt="Screenshot 2025-01-20 at 4 55 32 PM" src="https://github.com/user-attachments/assets/9c242ef1-3187-4d60-8815-4b1f63e14dbc" />

### Browser Panel
The Browser panel contains a file tree that allows you to access your computer's files and folders, and this is how you'll add data into map projects. Below the drives are Database connections. Spend a minute expanding the file tree by clicking the arrows to the left of each folder. Navigate to the project folder that holds our data, right-click and select 'Add as Favorite.' This copies the folder to the Favorites folder at the top for quick and easy access. Collapse the file tree by clicking the arrows again. 
### Customizing the UI
You can reorganize the various panels and bars in the UI to your liking by clicking on the name of the panel and dragging. Left click on 'Browser', and drag the panel toward the right side of the screen by moving your mouse while the left-click is still engaged. Notice how the Browser panel is now free floating as a standalone panel. Continue to drag the Browser panel to the right side of the screen, and a highlighted blank space will appear. You can dock the Browser panel on the right by dropping the panel into the highlighted space. 

<img width="685" height="435" alt="Screenshot 2025-01-20 at 5 52 44 PM" src="https://github.com/user-attachments/assets/94c7fd7b-0ca3-4d54-bd4f-d92d4875cc5a" />

You can also convert a docked panel into a standalone panel by clicking the icon with overlapping squares in the top right corner of the panel. You can remove unnecessary panels by clicking the X icon in the top right corner. Remove the layers panel by clicking the X icon. 

You can add panels or toolbar into the UI by clicking **View** in the Menu Bar and hovering over Panels or Toolbars, then clicking the items you want to be added into the UI. Add the Layers panel with View | Panels | Layers. Dock the Layers panel on the left side of the screen. 
## Creating a project
Now its time to create our first project. You can create a project by double clicking on the 'New Empty Project' template in the templates window, or you can go to Project | New in the menu bar. 

To save the this project, navigate to File | Save As in the menu bar, name the file 'Fundamentals_311Data' and save the file in a QGIS dedicated folder. 
### Adding a Basemap
Now we have an empty map canvas that we can fill with spatial data. To orient ourselves in the map canvas, we're going to add a **Basemap**. A basemap is a background layer that provides contextual geographic information for your data. Basemaps are typically static layers that show general geographic features such as streets, terrain, satellite imagery, or topographic maps, but they do not contain specific data that you want to analyze. 

We're going to use the default basemap from OpenStreetMaps. To do this, expand **XYZ Tiles** in the Browser Panel and double click or drag OpenStreetMap into the Map canvas. Notice that OpenStreetMap is now a layer in the Layers Panel. We'll talk more about this in a bit. But first we'll learn how to navigate the map with **zooming** and **panning**. 

## Navigating the Canvas

### Zooming
You'll often zoom in and out to different scales by using the Mouse Scroll Wheel:
- **Zoom In**: Scroll **up** on your mouse wheel to zoom in.
- **Zoom Out**: Scroll **down** on your mouse wheel to zoom out.
Practice zooming in and out while positioning your cursor in different areas on the map. Notice that as you zoom in, the map readjusts to keep that area in view.  

You can also use the Zoom Tools in the Toolbar. Clicking the **Zoom In** tool (magnifying glass with a "+") in the toolbar. Click around the map in different areas. Notice that as you zoom in, the map readjusts toward the area that you click on. Now, click and drag a rectangle around the area you want to zoom into. This will zoom into that selected region. Now click the Zoom Out tool (magnifying class with a "-"). Click around the map to zoom out. 

To quickly view the entire map extent, click the **Zoom to Full Extent** button (magnifying glass with three arrows). This zooms out to show all data layers in the project. You can also manually set the scale of your map by entering a scale ratio in the Scale Box in the Status Bar. 

### Panning
You can move the map view, which is called panning, in a few ways: 
1. Click the **Pan** tool (hand icon) in the toolbar and then click and drag the map to move around.
2. Hold down the **spacebar** and drag the cursor around the map. Notice that holding down the spacebar turns the cursor into a little fist. 
3. If you have a mouse, you can click and hold the **scroll wheel** and drag the cursor around the map. 
4. Use the **arrow keys** on your keyboard to move the map in small increments.
5. You can also type specific **coordinates** in the **Coordinate Box** in the Status Bar. This allows you to quickly navigate to a precise location based on known coordinates.

### Knowledge Check
1. Zoom to the full map extent.
2. Zoom in to the Continental United States.
3. Pan down to the bottom tip of South America.
4. Zoom in to the Falkland Islands.
5. Zoom to the full map extent.
6. Type the coordinates **-8230535, 4967483** into the **Coordinate Box** and type **1:250000** into the **Scale Box**.
7. Press Enter. Where are we? 


<Secret>
New York City!
</Secret>

## Bookmarks
Since we'll be working at the scale of New York City, we should create a **Spatial Bookmark** of this extent so that we don't have to zoom and pan to it over and over. To do this, click on the Spatial Bookmark button in the toolbar (blue bookmark with yellow star icon). In the Bookmark Editor dialog box, name the bookmark "New York City" and click Save. Now in the Browser panel, expand Spatial Bookmarks and Project Bookmarks to see that the New York City bookmark has saved. Whenever we want to return to this extent, we can click this bookmark. 
