# Coastal Bathymetry Group

## RawData
Raw data subfolders in both the vegetation and vertical displacement directories contain the needed geotiff files. In the vertical displacement raw data there are also files defining the study area, and geotiffs that have had initial clipping from the combined scenes but are not yet fully clipped to the exact study area. The folders beginning with North_ or South_ are scene pairs from the Alaska Satellite Facility, with several data files within. The North or South relates to the portion of the Outer Banks covered, the next series of numbers defines the reference scene date (yyyy_mmdd). Later in the directory name is a yyyy_mmdd format date of the second scene. The volume change csv file is taken from JABLTCX data, and shows the change in multiple parameters in areas of the outer banks, with dVol (change in volume) as the primary variable of interest. 

### Alaska Satellite Facility Data Retrieval and Processing

#### Vertical Displacement (InSAR)
Sentinel 1 InSAR data was collected from the Alaska Satellite Facility API using the process described by https://storymaps.arcgis.com/stories/68a8a3253900411185ae9eb6bb5283d3 . Two scenes were chosen from the outer banks in North Carolina, one before Hurricane Michael and one after. The later scene was chosen using the API's baseline tool based on its similarity to the initial (reference) scene. These two scenes were submitted to the Alaska Satellite Facility, which then generated an interferogram showing the vertical displacement between the two collection dates. This data is stored in the VerticalDisplacement/RawData folder. 

##### Note: There are currently 4 InSAR data folders uploaded, for both the northern and southern parts of the outer banks in 2018 (before and after Hurricane Michael) and 2016 (before and after Hurricane Matthew).

## Code

### Python Data Processing 
The Data_Processing_and_Exploration file is intended to be a rough workspace where various code fragments and visualizations are tested. It will be removed prior to the final submission of the project. The Merge_ASF_Scenes file takes northern and southern scene pairs of the outer banks over the same date range and merges them into a single geotiff file, which will be saved using the given name in the VerticalDisplacement/RawData folder. Note: this file is extremely large, so cannot be uploaded to git. Instead, directly feed into Clip_Vert_Displacement file or manually clip to isolate area in arcgis (example: partial_clipped_10_08_to_11_25_combined.tiff). The Clip_Vert_Displacement file clips the merged vertical displacement scene pair to the exact dimensions of the study area, reprojects so the crs and resolution match between vegetation and vertical displacement, and saves the resulting file in VerticalDisplacement/ProcessedData. Note: this file is also currently too large to upload to git. May need to be reprocessed at lower resolution? 

### Model train
Also in Clip_Vert_Displacement is initial code to prepare the datasets for model analysis, and examples of feeding the prepared data into models. This will be split into a new code file eventually. The data is currently a 4 column pandas dataframe with Vertical Displacement, NDVI Before, NDVI After, and NDVI Change columns. The NDVI change and Vertical Displacement are compared through a linear model.
