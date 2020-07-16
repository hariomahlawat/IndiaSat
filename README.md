# An-open-datset-for-pixel-level-classification-of-Landsat-7-and-Landsat-8-imagery

This repo contains an open dataset for pixel-level classification of Landsat 7 and Landsat 8 Imagery along with the code for classification as well as the error correction methods on top of it.

## Methodology for pixel-level classification of Landsat 7 and Landsat 8 Imagery
![alt text](images/landsat_classification.png?raw=true)

## Step by step procedure to do classification of a selected area.
* **Step 1  : Run the GEE script**

Run the corresponding GEE script for Landsat 7 or Landsat 8. (landsat7_classification.js or landsat8_classification.js).
The output of the GEE script will be three images for each area for each year. 
* **Step 2 : Run final_classification.py script**

It will make a different folder of each area and put all classification outputs for that area (for all the years) in that folder.


the command-line argument for the script - the path of root folder for a given area. (path of the unique folder which you just created) 


* **Optional- only_temporal_correction.py**


the command-line argument to be given while running the script - the path of root folder for a given area. (which you created in step 2)

This script is for experimentation with temporal correction technique. This performs only the temporal correction.

* **Optional- check_accuracy_2cat_landsat.py**

the command-line argument to be given while running the script - the path of root folder for a given area. (which you created in step 2)

This script is to check the BU/NBU accuracy when the ground-truth is available in four categories (green, water, bareland and built-up).
This script will provide four options to the user to check the accuracy of outputs from four different methods/techniques. The output of this script will be saved in a .txt file. 

  
