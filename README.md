# Los Angeles County Fires: Vegetation Health and EJI

This repository contains analyses exploring the Eaton and Palisades Fires that took place in Los Angeles County during January 2025. Using Python, I highlight the vegetation damage through false color imagery (notebook: false_color_imagery.ipynb) and explore internet availability of census blocks affected by the fires (notebook: fire_eji.ipynb).

These tasks were completed as part of my [MEDS](https://bren.ucsb.edu/masters-programs/master-environmental-data-science) coursework for [EDS220](https://meds-eds-220.github.io/MEDS-eds-220-course/). Part 1 was adapted from [Homework Assignment 4](https://meds-eds-220.github.io/MEDS-eds-220-course/assignments/assignment4-palisades-eaton-fires.html) and Part 2 a [discussion section activity](https://meds-eds-220.github.io/MEDS-eds-220-course/discussion-sections/ds8-eji-eaton-palisades.html). I compiled these notebooks in a single repository not only because they correspond to the same subject area, but also because they are both included in a single [blog post](https://sofiasarak.github.io/blog/la-fire-analysis/) on my personal website. Storing them in one place felt like a good choice for ease of accessibility!

## Analysis Overview

The Eaton and Palisades fires occurred nearly simultaneously, inflicting both ecological and infrastructural damage on Los Angeles. Together, they destroyed more than 16,000 structures and displaced thousands of households. Understanding the specifics of the impact – such as which populations were most affected as well as the extent of vegetation damage – is vital for recovery efforts, as well as informing future fire safety and policy.

In this repository, fire perimeters are overlayed with remote sensing and Environmental Justice Index (EJI) data to explore the patterns within in. 

`false_color_imagery.ipynb`:

By using remote sensing data and assigning infrared bands to visible colors, we are able to highlight vegetation health, burn severity, and the extent of fire scars remnant after the fire. 

`fire_eji.ipynb`:

Clipping EJI census block data to the fire perimeters gives us a summary of the internet availability in each area. Internet availability is an important aspect of fire safety response as communities that lack availability to natural disaster information have less time to respond.

## Data Sources

**Landsat/remote sensing**

The dataset used in this analysis is a simplified collection of bands (red, green, blue, near-infrared and shortwave infrared) from the Landsat Collection 2 Level-2 atmospherically corrected surface reflectance data, collected by the Landsat 8 satellite. Landsat data is provided by a series of Earth-observing satellites jointly managed by NASA and the U.S. Geological Survey (USGS), and stores a significant amount of reflectance information about the Earth's surface.

The data was retrieved from the [Microsoft Planetary Computer data catalogue](https://planetarycomputer.microsoft.com/dataset/landsat-c2-l2) catalogue and clipped to an area surrounding the fire perimeters by the [EDS220](https://meds-eds-220.github.io/MEDS-eds-220-course/) course team. 

**Palisades and Eaton fire perimeter**

Palisades and Eaton fire perimeter data were sourced from [LA County's GIS hub](https://egis-lacounty.hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about). It contains dissolved fire boundaries for Eaton and Palisades fires. It is a public data set, published January 21, 2025 and last updated on February 26, 2025. 

**Environmental Justice Index (EJI)**

EJI aims to summarize the cumulative impacts of environmental injustice by census tract in the United States. The index considers 36 different environmental, social, and health factors, with data from a variety of sources (including but not limited to the U.S. Census Bureau, the U.S. Environmental Protection Agency, U.S. Geological Survey, and OpenStreetMap). The data in this analysis was sourced from [Centers for Disease Control and Prevention and Agency for Toxic Substances Disease Registry](https://www.atsdr.cdc.gov/place-health/php/eji/eji-data-download.html).

## Repository Structure

```
├── data
│   ├── EJI_2024_California
│   │   ├── EJI_2024_California.gdb
│   │   ├── EJI_DATADICTIONARY_2024.csv
│   │   └── EJI_DATADICTIONARY_2024.xlsx
│   ├── landsat8-2025-02-23-palisades-eaton.nc
│   ├── Eaton_Perimeter_20250121
│   └── Palisades_Perimeter_20250121
├── false_color_imagery.ipynb
├── fire_eji.ipynb
└── README.md
```

## References

**Data:**

Centers for Disease Control and Prevention and Agency for Toxic Substances Disease Registry. (2024). Environmental Justice Index. Accessed November 21, 2025. https://atsdr.cdc.gov/place-health/php/eji/eji-data-download.html 

Earth Resources Observation and Science (EROS) Center. (2020). Landsat 8–9 Operational Land Imager / Thermal Infrared Sensor Level-2, Collection 2 [Dataset]. U.S. Geological Survey. https://doi.org/10.5066/P9OGBGM6

Los Angeles County Enterprise GIS. (2025). Palisades and Eaton Dissolved Fire Perimeters [Dataset]. Los Angeles County. https://egis-lacounty.hub.arcgis.com/maps/ad51845ea5fb4eb483bc2a7c38b2370c/about

Phillips, S. (2025, February). The Palisades and Eaton Fires: Neighborhood Data and Potential Housing Market Effects. UCLA Lewis Center for Regional Policy Studies.

**Educational Resources (used for understanding):**
- [Band designations for the Landsat satellites (USGS)](https://www.usgs.gov/faqs/what-are-band-designations-landsat-satellites)
- [Common Landsat Band Combinations (USGS)](https://www.usgs.gov/media/images/common-landsat-band-combinations)
- [How to Interpret a False-Color Satellite Image (NASA)](https://earthobservatory.nasa.gov/features/FalseColor)
- [True Color Imagery (NOAA)](https://coastwatch.noaa.gov/cwn/product-families/true-color-imagery.html)


*As mentioned above, this repository was created for the purposes of the EDS220 curriculum. Credit must be given to [Carmen Galaz García](https://github.com/carmengg) (Instructor) and [Annie Adams](https://github.com/annieradams) (Co-Instructor), who helped me develop my workflow!*
