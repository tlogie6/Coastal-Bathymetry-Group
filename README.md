# Coastal Bathymetry Group
## Note to team: I'm not sure what to put for this writeup or how much, feel free to change/add anything about the process that you went through. Also, whoever uploads the data please put in the specifics of your query (images, dates, etc.).

## Data Processing

### Vertical Displacement (InSAR)
Sentinel 1 InSAR data was collected from the Alaska Satellite Facility API using the process described by https://storymaps.arcgis.com/stories/68a8a3253900411185ae9eb6bb5283d3 . Two scenes were chosen from the outer banks in North Carolina, one before Hurricane Michael and one after. The later scene was chosen using the API's baseline tool based on its similarity to the initial (reference) scene. These two scenes were submitted to the Alaska Satellite Facility, which then generated an interferogram showing the vertical displacement between the two collection dates. 

Reference Scene for Sentinel 1 InSAR Data: 10_03_pair - S1AA_20181003T225747_20181027T225747_VVP024_INT80_G_ueF_33F5
This scene was taken from the southern part of the outer banks in North Carolina on 10/03/2018, shortly before the arrival of Hurricane Michael. The scene features the coast on the west side of the image with the whole eastern side of the scene being the Atlantic Ocean.

Scene pair: S1A_IW_SLC__1SDV_20181027T225747_20181027T225817_024328_02A9DB_18B5
This scene has a paired image for with a perpendicular distance of +11 meter, and was collected on 10/27/2018, about 1.5 weeks after Hurricane Michael.
