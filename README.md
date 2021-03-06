# SI-Pools

## Goal
The Goal of this project is to used Lidar and NIAP to locate and classify inground and aboveground swimming pools in Staten Island, New York. After the pool data has been classified a market study of the impact swimming pools may have sale sales price will be conducted. 

## Steps 
The first part of the project is the process the Lidar data into a hieght file. Next the NAIP data need to processed into NDWI. After that a decision tree is done. 

### Lidar 
![lidar](https://github.com/bobabugel/SI-Pools/blob/master/img/Lidar.PNG)  
The Lidar part is done using data from 2017 Lidar Flyover. This project use to **Digital Surface Model (DSM)** to find the top of building and trees.The **Digital Elveation Model (DEM)** is the ground. Lidar work by shooting light from the air to the ground. The first hit at the top of the tree is first return and is used in the DSM. The last hit is the ground and is called the ground return. The ground returns are used in the DEM.    

With these data set a **Canopy Height Model(CHS)** can made subtract the DSM from the DEM to get the height of something in this case swimming pools.  

https://github.com/bobabugel/SI-Pools/blob/master/CHS_1013_ArcPro.ipynb

### NDWI 
![NDWI](https://github.com/bobabugel/SI-Pools/blob/master/img/NDWI.PNG)
The Remote Sensing Part of the Project uses NAIP data from the USDA. This data is used because the flyover occured during the summer of 2017 that lines with the Lidar data. This project using **Normalized difference water index (NWDI)**. **Green** and **near-infrared (NIR)** bands and used to calculate this index 

https://github.com/bobabugel/SI-Pools/blob/master/NDWI_101320_ArcPro.ipynb

### Decision tree
After this the NWDI and CHS raster are created they can be combined to filter the fixes for pools and then the the hieght of those pools. Once they are filter they can be brought into taxlots. 

https://github.com/bobabugel/SI-Pools/blob/master/D_Tree_1014_arcPro.ipynb

### Tabulate Area 
![Pools](https://github.com/bobabugel/SI-Pools/blob/master/img/pools3.PNG)
At this point in the project the Raster data is joined with the vector data. The tax lots are brought in and a table is count the number of each type of pixel is in the tax lot. After that is done the inground pool pixels and the above-ground pixel are compared and the greatest one is given to the tax lot. This give all the tax lots fields of inground, aboveground and no pool. 

https://github.com/bobabugel/SI-Pools/blob/master/tabatecount.ipynb

### Join with Tax Data 
At this point the project sale data is brought in to the project. 


## Open Source version 

I been trying to get this to work with Rasterio but I'm having issues exporting it to a geotiff 
https://github.com/bobabugel/SI-Pools/blob/master/PoolProject_110320_OpenSource.ipynb
