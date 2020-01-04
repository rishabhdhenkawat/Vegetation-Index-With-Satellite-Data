# Satellite Imagery Analysis with Python

Objective
In this article, we shall study how we can examine the vegetation cover of a region with the help of satellite data. This article aims to familiarise the readers with the concept of satellite imagery data and how it can be analyzed to investigate real-world environmental and humanitarian challenges.
Region of Interest
I was particularly interested in knowing about the vegetation density in Central India . Therefore, the dataset in this article pertains to that area. However, the analysis would remain the same for any area in the world.
Satellite Imagery: An Overview
Satellite Imagery is the image of Earth(or other planets) which are collected by imaging satellites. Governments or private firms may own these Satellites. Satellite imaging companies sell images by licensing them to governments and businesses such as Apple Maps and Google Maps.
Setting up the System
The following libraries are required to run this project:
Planet’s Python Client
Rasterio: Geographic information systems use GeoTIFF and other formats to organize and store gridded raster datasets such as satellite imagery and terrain models. Rasterio is a Python library which reads and writes these formats and provides a Python API based on Numpy N-dimensional arrays and GeoJSON.
numpy
matplotlib
requests
Getting the Data
For this particular case study, we will be working with the Surface Reflectance (SR) Data. Simply put, the SR data is that satellite data which has been algorithmically corrected to remove any interference from the atmosphere. Let’s search & download some imagery of area around central India.
The data used in this exercise has been downloaded from Planet Explorer. Planet Explorer is a product of Product labs and is used to explore daily imagery right in our browser. Planet labs operate the largest fleet of Earth-imaging satellites, and the data provided by them is used for monitoring vegetation to measuring agriculture outputs.
An outline of the steps needed to download the imagery data.
Open the link: geojson.io. It is a fast time editor for map data
Define an Area of Interest (AOI): AOI is the location/geographical window out of which we want to get data.

Save the AOI’s coordinates generated in GeoJSON format in Jupyter notebook

Create filters for the date range, cloud coverage, and geometry. This will enable us to further constrain our Data API search.

Planet API Key
To use Planet’s APIs, you’ll need an API key. Create an account(14-day trial) at Planet Explorer and access the API key from here.
Searching: Items and Assets
The pictures taken by satellites can be classified as either Items or Assets. Whereas items refer to a single observation captured by satellite, assets describe a product that can be derived from an item’s source data and can be used for various analytic, visual or other purposes
In our case, we will try and get an image on which analytical operations can be conducted. Thus, we want a 4 band image with spectral data for Red, Green, Blue and Near-infrared values. To get the image we want, we will specify an item type of PSScene4Band and asset type.analytic

Activating and Downloading the Image
To download the image, we need to activate it. Once the activation status becomes “active,” we can then download the image of interest.

When the activation status changes to “active” from “inactive”,”we can download the image in .tiff format.

Exploring the Satellite Imagery
The python’s Rasterio library makes it very easy to explore satellite images. Satellite Images are nothing but grids of pixel-values and hence can be interpreted as multidimensional arrays.

Vegetation Index calculation from Satellite Imagery

Figure showing the changes in NDVI with the changing seasons.
Vegetation Index
A vegetation index is an indicator of the greenness of any area. It is a measure to monitor the health of a vegetation. A variety of data is captured by satellite sensors and one such type of data specifically measures wavelengths of light absorbed and reflected by green plants.
Dense vegetation reflects a lot of near-infrared light(not visible to the human eye) as compared to the visible red light. The reverse happens in case of sparse vegetation. Thus, as a plant canopy changes from early spring growth to late-season maturity and senescence, these reflectance properties also change.
NDVI
One of the most widely used index to measure vegetation is the Normalized Difference Vegetation Index (NDVI). the NDVI values range from +1.0 to -1.0. It was developed by NASA scientist Compton Tucker in 1977 and is derived from satellite imagery. It can be expressed as follows.

NDVI compares the reflected near-infrared light to reflected visible red light, by the plants.

Benefits of NDVI
The NDVI values give a rough estimation of the type, amount and condition of a vegetation at a place which is very useful fo researchers.
NDVI values can also be averaged over time to establish “normal” growing conditions in a region for a given time of year. This primarily helps in identifying areas where there are changes in vegetation due to human activities such as deforestation, natural disturbances such as wildfires, or changes in plants’ phenological stage.
Calculating NDVI for our Area of Interest
We already have our downloaded data in the form of a .tiff image. In this section, we shall calculate and NDVI index and analyse it.

BY RISHABH DHENKAWAT
