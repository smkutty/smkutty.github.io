---
layout: project
type: project
image: images/emlogo.jpg
title: GIS Project
permalink: projects/SantaCatalinaFires
# All dates must be YYYY-MM-DD format!
date: 2025-05-20
labels:
  - Geographic Information Science
  - Fire burn patterns
  - ArcGIS
summary: ENVS 483 - Santa Catalina Mountains Wildfires
---

<h3>Investigating Post-Wildfire Vegetation Recovery in the Santa Catalina Mountains </h3>

## Abstract
<p>Wildfires cause mass destruction to vegetation, particularly in forested regions. The impacts of wildfires and subsequent vegetation recovery can be monitored through remote sensing processes. This project investigates vegetation recovery in the Santa Catalina Mountains after the 2002 Bullock and 2003 Aspen Fires. Using pre-wildfire and post-wildfire data procured from Landsat 5, 7, and 8, change detection methods were applied to investigate how this area has recovered. Image diAerencing for NDVI data showed evidence of area recovery after both major fires but showed that NDVI values decreased overall in certain parts and did not return to its original quality. Similarly, image diAerencing for NBR data showed high post-fire regrowth and little to no burn zones. The MODIS NDVI time series, however, exhibited rapid drops and gradual upward trends in which the peaks do not recuperate. Based on this, we can conclude that vegetation recovered in terms of area after the Bullock and Aspen Fires but not in quality.</p>

## Introduction

### Wildfires and Climate Change

<p>Wildfires play a significant role in changing terrestrial ecosystems, and as global temperatures rapidly increase, this role’s magnitude has expanded as well. In the last few decades, wildfire activity has particularly grown in temperate forests (NASA, 2025). A combination of reduced soil moisture and abundant, dry organic matter, like shrubbery and trees, makes these forests ideal grounds for wildfires. Between 1984 and 2015, large fires doubled in frequency just in the western United States (Center for Climate and Energy Solutions). In a 2019 study, researchers determined that between 1972 and 2018, wildfires particularly increased in forest areas during the summer due to climate change impacts. This trend is likely to continue, and the timeframe of wildfires is expected to lengthen into normally cooler months of fall. These studies are important as forests contain vast amounts of biodiversity, making their destruction catastrophic (Williams, 2019). </p> 

### The 2002 Bullock Fire

<p>An example of this was the Bullock Fire in 2002 near Tucson, Arizona. This fire burned from late May to early June, burning nearly 31,000 acres in the Coronado National Forest in the Santa Catalina Mountains (NASA Earth Observatory, 2002). </p>

### The 2003 Aspen Fire

<p>The summer of 2003 saw an even more disastrous wildfire in Arizona. The Aspen Fire began on 17 June and lasted until 12 July, burning close to 85,000 acres of land. The fire burned large swaths of land across Mount Lemmon near Tucson, Arizona, causing catastrophic damage to the surrounding forests and even decimating the town of Summerhaven. Although human activity caused this fire, changing climate conditions allowed the initial point to spread rapidly and with intensity (Kreutz, 2015). A study was conducted by the USDA Forest Service shortly after the fire’s aftermath to look at spread patterns. They found evidence of surface fires that burned down about 300 homes and high intensity fires amongst canopies and forests (Cohen, 2003). </p>

### Remote Sensing

<p>Remote sensing is an integral tool in studying burn zones and vegetation recovery. Using spectral data, we can determine changes in NDVI (Normalized DiAerence Vegetation Index) to quantify vegetation quality for large swaths of land. Similarly, remote sensing imagery can provide data to calculate NBR (Normalized Burn Ratio) to aid in creating categorized burn zones based on severity. </p>

### Project Objectives

<p>This project will focus on area and quality of vegetation recovery in the Santa Catalina Mountains, which are a specific area of Mount Lemmon. This study area will be further discussed in the Methodology section. The timeline of study will be from 2002 to 2020, an 18-year timespan after the Bullock Fire. We can determine vegetation recovery and temporal changes in burn zones using change detection methods through ArcGIS. For this study, binary change detection using image differencing will visually demonstrate temporal land cover changes. Additionally, an NDVI time series graph will provide supplemental information about the quality of vegetation recovery. The results of these processes should be able to determine whether vegetation quality and area were able to recover.</p>

## Methodology

### Study Area

<p>The map below shows the extent of Tucson, Arizona, with a red box indicating the study area. This study area is where we will investigate vegetation recovery after the Aspen and Bullock fires. </p>

<p>The two fires in question are the 2002 Bullock Fire and 2003 Aspen Fire shown below in red and yellow, respectively. The Aspen Fire region will be denoted as Region A and the Bullock Fire region as Region B. </p>

### Data Collection

<p>Data for this project will come from two types of remote sensors—Landsat and MODIS. Landsat has nine current versions, of which we will look at images taken by Landsat 5, 7, and 8. These images can be used for raster algebra to look at area recovery. MODIS, or Moderate Resolution Imaging Spectroradiometer, is eAective for collecting NDVI data for vegetation studies. Data from MODIS will be used to look at vegetation quality and collected from NASA’s Earth Data website.</p>

### False Color Imagery

<p>The first set of images developed of the study area will be in false color. To render the image in false color, we change the RGB (Red, Green, Blue) channels to NRG (Near-infrared, Red, Green). This causes healthy vegetation to look bright red, making this a great tool for preliminary vegetation studies. We can use these images to expect patterns in vegetation changes from 2002 to 2020. </p>

### NDVI and NBR

<p>NDVI (Normalized DiAerence Vegetation Index) measures vegetation quality. Using the equation 
below, we produce a value generally between -1 and 1, with -1 as unhealthy/barren areas and 1 as 
lush, high-quality vegetation. In this equation, NIR is the near infrared band, and Red is the red band.</p>

<p>NBR (Normalized Burn Ration) is a type of vegetation index that demonstrates burn severity. The 
equation for NBR is similar to NDVI’s and also typically results in values between -1 and 1, with 1 as 
healthy vegetation and -1 as severe burns. In this equation, NIR is near infrared and SWIR is short 
wave infrared.</p>

<p>The Raster Calculator tool in ArcGIS pro can apply both equations separately to the entirety of the 
maps/rasters and generate an NDVI or NBR map/raster. This will show us vegetation patterns and 
burn zones and subsequently use them for change detection analyses. </p>

### Binary Change Detection

<p>n order to determine temporal changes across an area, we can employ change detection methods on ArcGIS. One set of methods is binary change detection, which produces a “change or no change” result. The type of binary change detection used here is image diAerencing. This involves applying basic algebra to rasters from diAerent time periods to identify changes. Because NDVI and NBR may sometimes have outliers beyond the -1 to 1 scale, we need to normalize the raster sets such that raster values all fall in this range.</p>

<p><b>NDVI Difference:</b> Subtracting rasters (before – after) produces a new raster where numbers close to 1 are positive changes in vegetation (regrowth) and numbers closer to -1 are losses in vegetation.</p>

<p><b>NBR Dfference:</b> The process for NBR is similar. Using the raster calculator tool, we subtract the postfire layer from the prefire layer (before – after) to create a new raster. However, the resulting values between -1 and 1 can tell us additional information summarized in the table below. (Note: ΔNBR means change in NBR) </p>


### MODIS NDVI Time Series

<p>This portion again employs the use of NDVI to determine vegetation quality. An NDVI time series collects NDVI values from a specified area and creates a line graph for the interested period. This line graph gives us a visual representation of how NDVI values change temporally. A region is requested, and a CSV file is provided with dates and relevant data. Using the date and the average NDVI value columns, we can create a line graph to display fluctuations over time.</p>

## Results

## Conclusion

<p>The maps generated through ArcGIS allowed for visual investigation of vegetation recovery and identification of burn zones. Data collected from MODIS generated graphs that supplement the maps and provide NDVI values to better understand changes in vegetation quality. Important to highlight is Figure 13, which showed the diAerence in NDVI values between 2002 and 2020. Region A has large portions of purple, demonstrating loss. However, Figure 10 appears to establish that vegetation recuperated in Region A. This ultimately provides evidence that while vegetation area recovered after the Aspen Fire, the quality in 2020 did not match that of 2002. When paired with data from MODIS, we can see that the NDVI peaks do not return to their original values before summer of 2002. 

<p>This analysis does not involve corrections for geometry or weather. For proper change detection analyses, it is important to apply corrections for weather issues such as cloud coverage or rain, as this may affect NDVI values. Because we did not correct the pre- or post-images, confounding variables such as climate events could have skewed data collected on certain pixels. Another component that may be skewed is the MODIS time series. The chosen coordinate covers a region that is 6.25 km by 6.25 km (3.88 miles) in dimension. This box does not cover the entirety of the study area, so the data may be missing fluctuations and relevant information.</p>

<p>Additional analyses can include thematic change detection through pre- and post-classification tools through ArcGIS. This would involve either supervised or unsupervised classification to determine how land cover has changed in terms of identified classes. Alongside ground truth data, this could be a powerful and eAective method to analyze vegetation recovery. We can also use additional Landsat data from different years and months to create supplemental maps to show granular temporal changes.</p>

<p>While the data suggests that vegetation mostly recovered by area, we can also see that the quality did not appear to recuperate.Unfortunately, the Santa Catalina Mountains experienced a third highly destructive fire in June of 2020, just a month after the 2020 post-fire data used for this project. A possible extension of this project is investigating vegetation recovery following all three fires to 
determine overall flora changes and predicting recovery patterns across regions.  </p>

## References
