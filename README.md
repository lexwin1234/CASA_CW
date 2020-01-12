# CASA_CW
This repository provide the data applied into the study
The procedures of the investigation can be divided into 3 parts, which are 
	1) Data input  
	2) Create isochrones
	3) Cover area calculation 
  
Firstly, the data collected form Esri are in WGS 84 projection and it have to be transformed into Hong Kong 1980 Grid to match the other data. 
To transform the projection, the "Project" tool was applied. 
Then the Land Utilisation have to be transformed into vector (polygons) to provide meaningful comparison in further processes. 
Hence, the "Raster to polygons" too was utilised. After that the product of "Raster to polygons" have to dissolved by using "Dissolve" tool, and the dissolve input is gridcode. 
However, the residential area have to be selected in the attribute table, which are gridecode 1 , 2 and 3. 
After selecting the gridecode, export the shape file and rename it. 
Then use the "intersect" tools to locate which districts are the polygons in, the input will be the 18 Districts and the product of the dissolved Land Use data.

Secondly, when all the data are sorted, the isochrones are ready to be created. 
Open the "Network Analyst" window and select the Sports Centres Location as the inoput of "Facility". 
Then create a new "Services Area Layer", and select time (driving time) or distance (metres, walking distance) for the preferable input in the "Analysis Setting" then right click solve to generate the isochrones. 
After that export the polygons and dissolve it by "Ename". 
Repeat the process for all the variables.

Lastly, when all the isochrones are created, the last step is calculate the cover percentages of each variables. 
Use the "Intersect" tool to check what residential area had covered, and the input will be the product of isochrones and intersected Land Use data. 
Open the attribute table and click "Add field", rename it then open the field calculator.  
The equation of the cover percentages is " (Isochrones covered area/residential area)*100 ". Repeat the process for all the variables.
