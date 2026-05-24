# Everest Snow Cover AI4EO
Monitoring seasonal snow-cover variability in the western Everest during 2025 using Sentinel-2 imagery, unsupervised classification, and Gaussian Process interpolation.



![Monthly K-means snow masks in 2025](figures/fig_07_monthly_kmeans_snow_masks_2025.png)



## Project overview

This project aims to map and estimate seasonal snow-cover variability in a selected area of the western Everest using one Sentinel-2 Level-2A scene for each month of 2025.

The Sentinel-2 images are first clipped to the study area and filtered using the Scene Classification Layer (SCL) to remove invalid, cloud-contaminated and cloud-shadow pixels. Normalized Difference Snow Index (NDSI) and Normalized Difference Vegetation Index (NDVI) are then calculated from the Sentinel-2 reflectance bands.

A fixed NDSI-threshold method is used as a baseline, while K-means clustering is then applied as the main unsupervised classification method to separate snow-dominated and non-snow-dominated pixels. A Gaussian Mixture Model (GMM) is also tested on one representative June scene to compare with the K-means classification, and see if the snow/non-snow classification is sensitive to different unsupervised learning methods.

Finally, the monthly K-means snow-cover fractions are used as input for Gaussian Process regression to reconstruct a seasonal snow-cover curve with uncertainty estimates. An artificial gap validation is also included to test whether the Gaussian Process model can reasonably estimate missing monthly observations.

The main outputs are monthly snow masks, a snow-cover fraction time series, a Gaussian Process seasonal reconstruction, and a simple validation of gap-filling performance.




