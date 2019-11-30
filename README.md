# Turbid-reefs-moderate-coral-bleaching-under-climate-related-temperature-stress

The code is run in the order numbered 01 through 10. All input and output files are included as well, 
except for the files that are too large for GitHub. Most of these sections can be skipped if you want to examine 
just a particular section. If you need to use the global mean turbidity raster, "turbidity_raster_mean.nc", 
please run code sections 01 and 02 to create the raster. It is too large to fit in GitHub.


01_Get_Turbidity_Data_final

Input= the kd490 data (available from https://oceandata.sci.gsfc.nasa.gov/MODIS-Aqua/Mapped/Monthly/4km/Kd_490/) 
and a csv file with the SST CoRTAD data "Reef_Check_with_cortad_variables_with_annual_rate_of_SST_change.csv"

Output = a csv with the Reef Check, SST, and kd490 data "Reef_Check_with_turbidity_kd490.csv"


02_Turbidity_Rasters_Mean_Final

Input = the kd490 data (/Lab Data/Global/Kd490/Monthly/4km/MODIS_Aqua/netcdf)

Output = a raster of mean turbidity globally "turbidity_raster_mean.nc"


03_Plot_Mean_Turbidity_Globally_Final

Input = "turbidity_raster_mean.nc"

Output = Figure1 - a tiff of turbidity globally


04_Ordinal_Regression_Final

Input = The csv we made in code 01_Get_Turbidity_Data_Final "Reef_Check_with_turbidity_kd490.csv",  
the "MyBUGSOutput.R" code to format the jags output, Ecoregion shapefiles (in the /ecoregion_exportPolygon folder)

Output = Figure2 - the coefficient plot. and a csv of the coefficients so we don't need to run the model every time 
we want to access the coefficients 'ordinal_coeffs_sst_turbidity_and_interaction.csv'


05_Gamma_Plots_Final

Input = The csv we made in code 01_Get_Turbidity_Data_Final "Reef_Check_with_turbidity_kd490.csv".

Output = Figure3 - the probability densities of kd490 at different bleaching levels.


06_Australia_Turbidity_Final

Input = a csv of the lat/lon coordinates for each Australia reef and the width of the reef flat, 
and the raster "turbidity_raster_mean.nc"

Output = a csv of the Australia reefs with the corresponding kd490 value 'Australia_Turbidity_Final.csv', 
and FigureS4 - the nls() analysis of the kd490 and reef flat size.


07_All_Reefs_Turbidity_Sampling_Final (takes 2-3 days to run this code)

Input = mean turbidity globally raster "turbidity_raster_mean.nc", ReefBASE shapefiles of all reefs globally (http://www.reefbase.org/main.aspx), the Ecoregions shapefiles (in the /ecoregion_exportPolygon folder).

Output = a csv of the reef area in each ecoregion that falls within the 'moderating turbidity' range
"Ecoregion_turbidity_probabilities_080_to_127.csv', which is Supplementary Table 2.


08_Proportion_of_Reefs_in_Moderating_Turbidity_Range_Final

Input = the Ecoregions shapefiles (in the /shapefiles folder), the csv of the reef area in each ecoregion 
that falls within the moderating turbidity range "Ecoregion_turbidity_probabilities_080_to_127.csv".

Output = Figure4 - a map showing the percentage of reefs in each ecoregion that fall within the moderating turbidity range.


09_Reef_Check_Map_Severity_Final

Input = wlrd.p shapefiles (in the /ecoregion_exportPolygon folder), and a csv with the Reef Check bleaching 
data "Reef_Check_with_turbidity_kd490.csv".

Output = FigureS1 - image of percent bleaching globally, FigureS3 - image of bleaching severity globally.


10_Turbidity_Boxplots_Final

Input = a csv of the Reef Check turbidity data "Reef_Check_with_turbidity_kd490.csv", the Ecoregion shapefiles  
(in the /ecoregion_exportPolygon folder).

Output = FigureS2 - boxplots of turbidity in each ecoregion arranged by longitude.

