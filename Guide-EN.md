# beach-contracts-mapping guide _(english version)_
**How-To visualize lease areas, found in lease contracts via [diavgeia.gov.gr](https://diavgeia.gov.gr/) on a google map.**


---

So you've found the contract for a place that you suspect is violating its lease agreement. Here's an easy-to-follow guide on how to plot these coordinates on a map. You will only need a text editor and an internet connection.

### Preparing the File
You will find a folder "files" with accompanying files inside this repo. Open the file called `empty.geojson` with a text editor. If you use a basic one like WordPad or Word, it's best to select all and change the font to a fixed-width family like "Courier", which should be available on Windows and MacOS to ease the editing process.

**[01_data-extraction.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/01_data-extraction.jpg?raw=true)**  
This is how the `empty.geojson` file should look. I have changed the "name" entries to "Paros on the rocks" since that is the lease contract I will be using for this example.

**[02_data-extraction.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/02_data-extraction.jpg?raw=true)**  
Here you can see the selected section that defines one polygon area. If contracts include multiple areas, refer to (05_data-extraction.jpg).

### Editing Coordinates
**[03_data-extraction.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/03_data-extraction.jpg?raw=true)**  
Now, open the lease contract pdf-file and find the section that describes the lease area. It usually starts with square meters, followed by blocks of X and Y coordinates. Copy the first X-coordinate, in our example, 607718.65, and paste it into the `empty.geojson` file, where I put a placeholder "X-COORD". Repeat this with the first Y-coordinate, in our example 4109623.16, and place it where the "Y-COORD" placeholder is. Continue until you've finished with the coordinate blocks. If you run out of placeholders, copy/paste the existing one at the end of the last closing square bracket of the last coordinate pair, and add a comma to separate the square bracket-enclosed coordinate pairs.  
```
[
    X-COORD,
    Y-COORD
],
[
    X-COORD,
    Y-COORD
]
```
**IMPORTANT:** When you're done, copy the first coordinate pair and paste it at the end of all coordinate pairs to properly close the Polygon.

**[04_data-extraction.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/04_data-extraction.jpg?raw=true)**  
This is how the geojson file should look in our example. You can save it as a new file; I called this one "paros-on-the-rocks-2100.geojson". The _-2100_ suffix emphasizes that the coordinate system of the data is EPSG:2100, commonly used in Greece.

**[05_data-extraction.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/05_data-extraction.jpg?raw=true)**  
If there is more than one area in the lease contract, multiple areas can be added to the geojson file. Duplicate the section enclosed by curly braces inside the "features" block for this to work.

### Data Conversion
**[06_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/06_data-conversion.jpg?raw=true)**  
Visit the [MyGeodata Cloud](https://mygeodata.cloud/) website. To convert more than 3 times, create a free account by clicking "Sign In" on the main page. Choosing Google should speed up the process.

**[07_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/07_data-conversion.jpg?raw=true)**  
After signing in, click on "Go to Converter >>."

**[08_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/08_data-conversion.jpg?raw=true)**  
Click on "Or browse files to convert" and select the geojson file you edited, "paros-on-the-rocks-2100.geojson" in our example.

**[09_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/09_data-conversion.jpg?raw=true)**  
This screen shows the file is uploaded and ready for conversion. Click "Continue."

**[10_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/10_data-conversion.jpg?raw=true)**  
You can check that everything worked by looking for your chosen name in the "Input Layers to Convert" textbox. Also, in the "Input parameters" section, it should correctly state the Greek Grid coordinate system. Click "Show in a Map" to verify all coordinates are correct.

**[11_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/11_data-conversion.jpg?raw=true)**  
If everything went well, the area is displayed on the map at the expected location.

**[12_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/12_data-conversion.jpg?raw=true)**  
Choose "KML" as the Output Format and "WGS 84 (EPSG:4326)" as the Coordinate System. Select the "name" in field assignments to carry the names over to the KML file. Click "Convert now!"

**[13_data-conversion.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/13_data-conversion.jpg?raw=true)**  
Conversion should be successful. Click "Download" to save the KML file.

### Creating the Map
**[14_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/14_map-creation.jpg?raw=true)**  
Visit [Google Maps](https://www.google.com/maps) and click the "Saved" icon on the left sidebar. Choose the "Maps" tab, then click "Open My Maps."

**[15_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/15_map-creation.jpg?raw=true)**  
Click "+ CREATE A NEW MAP."

**[16_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/16_map-creation.jpg?raw=true)**  
You are now ready to import the KML data. You may want to change the "Base Map" to satellite data.

**[17_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/17_map-creation.jpg?raw=true)**  
Click the "import link."

**[18_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/18_map-creation.jpg?raw=true)**  
Select or drag the KML file that you saved onto the window.

**[19_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/19_map-creation.jpg?raw=true)**  
The newly created layer should appear, and the map should be zoomed into its extent.

**[20_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/20_map-creation.jpg?raw=true)**  
You can customize the layer's appearance by choosing fill color, transparency, and border width.

**[21_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/21_map-creation.jpg?raw=true)**  
Name your map by clicking on the title.

**[22_map-creation.jpg](https://github.com/digitalparos/mapping-lease-agreements/blob/cf1721dd2557fc8a5a72dc1fc6851e7490fb5e74/step-by-step-jpgs/22_map-creation.jpg?raw=true)**  
Click "Share" to open Share Map Options. Copy the unique URL and share it, ensuring "Anyone with this link can view" is selected.

### NOTES
- More often than not, the coordinates include typos. Which means that they miss a number or add a number too many. This will show up as a distorted area, since usually one coordinate is out of place. Since the system is in meters, with a bit of examination you should be able to figure out errors. Ultimately these numbers are just X/Y coordinates in meters, layed upon Greece. You may refer to [this website](https://epsg.io/2100) for an explanation.
- Don't forget to copy the first coordinate pair and paste it at the end of all coordinate pairs to properly close the Polygon.
