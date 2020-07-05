# An-open-datset-for-pixel-level-classification-of-Landsat-7-and-Landsat-8-imagery

An open dataset for pixel level classification of Landsat 7 and Landsat 8 Imagery. The repo contains the code for classification as well as the error correction methods on top of it.

## Procedure to do the pixel level classification for Landsat 7 and Landsat 8
![alt text](images/landsat_classification.png?raw=true)
* **Step 1 : Run the GEE script**

Run the corresponding GEE script for Landsat 7 or Landsat 8. (landsat7_classification.js or landsat8_classification.js).
You will get three images for each area for each year on ehich you have run the above GEE script for classification. 
* **Step 2 : Run final_classification.py script**

Make a unique folder of each area and and put the all classification outputs for that area (for all the years) in that folder.


command line argument to be given while running the script - path of root folder for a givern area. (path of unique folder which you just created) 

Calssification outputs from step 1 will be in .tif format.
The final_classification.py scipt will do the following:
1. Creating the subfolder structure - Make subfolders for each year and put corresponding classifications files to them. 
2. Conversion of .tif files into .png files for further processing.
3. Making final classification for each year - by combining the different classification outputs of same year (max - 3).
4. It will create a results folder which will various subfolder for different kind of techniques:
  (a) Direct application results
  (b) Results after rule-based technique.
5. It will also do the temporal coorection on both kind of results and save the results in two different subfolder under results folder.
* **Optional- only_temporal_correction.py**


command line argument to be given while running the script - path of root folder for a givern area. (which you created in step 2)

This script is for experimentaion with temporal coorection technique. This performs only the temporal correction.

* **Optional- check_accuracy_2cat_landsat.py**

command line argument to be given while running the script - path of root folder for a givern area. (which you created in step 2)

This script is to check the bu/nbu accuracy when the groundtruth is available in four categories (green, water, bareland and builtup).
This script will provide four options to user to check accuracy of outputs from four different methods/techniques. The output of this script will be saved in a .txt file. 

  
