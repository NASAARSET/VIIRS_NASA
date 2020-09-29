# VIIRS_NASA
This repository contains:
1. Sample VIIRS data file
2. Readme file
3. fileLists.txt file

There are five scripts: 

1) viirs_export_csv

a) Read the fileList and get the dataset/file(s) that is(are) listed.
b) Get the date and time variable and map it along the size of the data array.
c) Loop through all the sds variables and find "Aerosol_Optical_Thickness_550_Land", "Aerosol_Optical_Thickness_550_Land_Ocean_Best_Estimate", "Aerosol_Optical_Thickness_QA_Flag_Land", "Aerosol_Type_Land_Ocean" and "Angstrom_Exponent_Land_Ocean_Best_Estimate".
d) Add columns for each one and list the values.
e) Create .csv listing all the data for these variables along with the date and time when they were collected.

2) read_viirs_and_list_sds

a) Read the fileList and get the dataset/file(s) that is(are) listed.
b) The main function calls another function to print the following values:
i) nc_attrs : list
  A Python list of the NetCDF file global attributes
ii) nc_dims : list
  A Python list of the NetCDF file dimensions
iii) nc_vars : list
 A Python list of the NetCDF file variables

3) read_viirs_at_a_location

a) Read the fileList and get the dataset/file(s) that is(are) listed.
b) Calculate the mean, median, and standard deviation and display them.
c) Calculate the range of valid data and display the longitude and latitude.
d) User should input longitude and latitude that fall within the displayed range.
e) Identify points that are closest to the user input and output the value of the closest collocation, and the means of a 3x3 and 5x5 pixel square centered around the input.

4) read_and_map_viirs

a) Read the fileList and get the dataset/file(s) that is(are) listed.
b) Prompt the user to choose between "Aerosol_Optical_Thickness_550_Land", "Aerosol_Optical_Thickness_550_Land_Ocean_Best_Estimate", "Aerosol_Optical_Thickness_QA_Flag_Land", "Aerosol_Type_Land_Ocean" and "Angstrom_Exponent_Land_Ocean_Best_Estimate".
c) Calculate the range of valid data to be used to be displayed in the map.
d) Plot the variable of interest along with a color bar on the side based on the sds variable chosen and the data for that variable.

5) read_aod_and_calculate_pm25

a) Read the fileList and get the dataset/file(s) that is(are) listed.
b) Prompt the user to choose between "Aerosol_Optical_Thickness_550_Land", "Aerosol_Optical_Thickness_550_Land_Ocean_Best_Estimate", "Aerosol_Optical_Thickness_QA_Flag_Land", "Aerosol_Type_Land_Ocean" and "Angstrom_Exponent_Land_Ocean_Best_Estimate".
c) Calculate the range of valid data to be used to be displayed in the map.
d) Based on the data seperate the quality of the aerosol.
e) Prompt the user as to whether they want to input a slope.
(***NOTE: the default slope used in this code is meant for demonstrative purposes only and is not meant to be used for quantitative analyses***)
e) Plot a map of AQI along with a color bar on the side.
