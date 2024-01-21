## citibike-tableau-challenge
**Module 18 Challenge - Citibike**

In this scenario, as a new lead analyst for the New York Citi Bike program, my responsibility was to construct an interactive Tableau Public Workbook and provide valuable insights into the program. 

I opted to concentrate on Jersey City data from July 2022 to July 2023, inclusive. The data was provided in the form of zipped CSV files, sourced from: https://citibikenyc.com/system-data.

Using Jupyter Notebook, I appended and cleaned the data files to create a single, consolidated source for uploading to Tableau Public. Once uploaded, I populated worksheets with various measures and views to extract insights. This allowed me to construct a narrative by creating four dashboards. Finally, I designed a dashboard to display data outliers and explained the rationale behind their exclusion from the analysis.

**The url to my Tableau Public Workbook:**
https://public.tableau.com/app/profile/katharine.tamas/viz/NewYorkCitiBikeAnalysis_16953918404890/JerseyCityBikesStory?publish=yes


**Repository Folders and Contents:**
- Data:
  - JC-202207-citbike-tripdata.csv
  - JC-202208-citibike-tripdata.csv
  - JC-202209-citibike-tripdata.csv
  - JC-202210-citibike-tripdata.csv
  - JC-202211-citibike-tripdata.csv
  - JC-202212-citibike-tripdata.csv
  - JC-202301-citibike-tripdata.csv
  - JC-202302-citibike-tripdata.csv
  - JC-202303-citibike-tripdata.csv
  - JC-202304-citibike-tripdata.csv
  - JC-202305-citibike-tripdata.csv
  - JC-202306-citibike-tripdata.csv
  - JC-202307-citibike-tripdata.csv
- Images:
  - Citibike Logo.png
  - bike icon.png
  - cycling icon.png
  - distance icon.png
  - docked bike icon.png
  - finish icon.png
  - outlier icon.png
  - time icon.png
- Append and Clean Citibike Data.ipynb


## Table of Contents

- [About](#about)
    - [Part 1: Clean and Append Data in Jupter Notebook](#part-1-clean-and-append-data-in-jupyter-notebook)
    - [Part 2: Create the Tableau Workbook and Perform Analysis](#part-2-create-the-tableau-workbook-and-perform-analysis)
- [Getting Started](#getting-started)
- [Installing](#installing)
- [Contributing](#contributing)
- [Sources](#sources)


## About
### Part 1: Clean and Append Data in Jupyter Notebook

Initially, I imported 13 CSV files containing Jersey City data into Jupyter Notebook. I conducted initial checks on the column data types and verified that each data file had consistent information across its columns. These 13 files were subsequently appended into a single CSV file. Further data validation was carried out to identify and address any missing or incorrect data.

It was identified that the following fields contained null values: start_station_name, start_station_id, end_station_name, end_station_id, end_lat, and end_lng. Consequently, I chose to remove the rows containing these null values from the data file.

Next, I examined the start and end station names to ensure their uniqueness. During this examination, I discovered four end stations with two names, such as 'Murray St & West St' and 'Murray St\t& West St.' To resolve this issue, I updated the end_station_name for these stations to have a single, unique name each.

Finally, I exported the cleaned and consolidated CSV file.

**Resource Files I Used:**
  - JC-202207-citbike-tripdata.csv
  - JC-202208-citibike-tripdata.csv
  - JC-202209-citibike-tripdata.csv
  - JC-202210-citibike-tripdata.csv
  - JC-202211-citibike-tripdata.csv
  - JC-202212-citibike-tripdata.csv
  - JC-202301-citibike-tripdata.csv
  - JC-202302-citibike-tripdata.csv
  - JC-202303-citibike-tripdata.csv
  - JC-202304-citibike-tripdata.csv
  - JC-202305-citibike-tripdata.csv
  - JC-202306-citibike-tripdata.csv
  - JC-202307-citibike-tripdata.csv

**My Jupyter Notebook Python Cleaning Script:**
  - Append and Clean Citibike Data.ipynb

**Consolidated Cleaned File I Created:**
  - Jul22_to_Jul23.csv (note this file was too large to upload to this repository)

**Tools/Libraries I Imported:**
   - pandas library: for data manipulation and analysis
   - pathlib library: to create and manipulate file and directory paths easily


### Part 2: Create the Tableau Workbook and Perform Analysis

In this section, I imported the cleaned consolidated CSV file into Tableau and generated multiple worksheets to explore the data and extract insights. Once I had a clear understanding of the narrative I intended to convey, I developed five dashboards. Four of these dashboards contribute to the Tableau story, while one is designed to highlight data outliers. It's important to note that the analysis below excluded rides with a duration exceeding 120 minutes.

**Tableau Story:**

**1. Summary Data:**

  Citibike Start Stations are primarily concentrated in zip codes 07302 (Kearney) and 07030 (Hoboken).
  Member rides account for 70% of total rides, with casual rides making up the remaining 30%. 
  Classic bikes are the most popular choice, representing 78% of all rides, followed by electric bikes at 21%, and docked bikes at 1%. 
  The average distance traveled per ride is 1.164 kilometers, with an average duration of 10.19 minutes.
  This aligns with the bike hire policy, which encourages rides of no more than 30 minutes for casual riders and 45 minutes for members at a time.
  ![image](https://github.com/KTamas03/citibike-tableau-challenge/assets/132874272/f70c0f00-90c0-425b-ac7f-a4732e2ed9a4)



**2. Peak Times to Ride:**

  Peak ride hours are typically around 5 pm and 6 pm, with summer being the preferred season due to favorable weather. Midweek, specifically Wednesday, Thursday, and Friday, sees the highest ridership. Daily ridership shows a seasonal pattern, with fewer rides in winter and the most in summer.
  Members primarily use bikes for commuting, with peak usage in the mornings (8 am) and evenings (5 pm, 6 pm) on weekdays, peaking on Wednesdays. Their usage follows a seasonal trend throughout the year.
  Casual riders favor evening rides, with summer and fall being their top seasons, and weekends, especially Saturdays, are popular. The yearly trend for casual riders is also seasonal, with a higher proportion during the summer, likely due to tourists visiting the city.
  ![image](https://github.com/KTamas03/citibike-tableau-challenge/assets/132874272/e8b6b541-5271-4530-9c3c-e7396dca69a4)



**3. Top 10 Stations:**

  The top 10 Start Stations by average daily rides are identical to the top 10 End Stations, and they are in the same order. Four stations (2. Hoboken Terminal - River St & Hudson Pl, 3. South Waterfront Walkway, 4. Hoboken Terminal - Hudson St & Hudson, and 5. City Hall) are located within a 300m radius in zipcode 07030. The other two stations within 200m of each other in the top 10 are Newport PATH and Newport Pkwy in zipcode 07310. Additionally, most Start and End Stations tend to be within 2 kilometers of each other and are usually located within the same zipcode.
  ![image](https://github.com/KTamas03/citibike-tableau-challenge/assets/132874272/1ec42f26-a482-41d8-8a3c-1620c2890c4b)



**4. Casual vs Member Rides:**

  Casual rides have a longer average duration and cover more distance than member rides. This also holds true for classic and electric bikes. Note. 'docked bikes' are only used in casual rides.
  Member rides tend to cover a slightly larger area of New Jersey compared to casual rides. The majority of both member and casual rides start in areas with '2018 Per Capita Income' ranging from $37,200 to $461,000, as indicated by the grey shades in the background. Interestingly, these areas coincide with the two zip codes where most rides begin, namely 07030 (Hoboken) and 07302 (Kearny).
  ![image](https://github.com/KTamas03/citibike-tableau-challenge/assets/132874272/f72bde69-91e3-460a-93e7-abd9011edaaa)


**Outliers Dashboard:**

  Citibike riders have specific ride duration allowances: Casual riders get 30 minutes per ride and are billed $0.26/minute afterward, while Members get 45 minutes per ride and are billed $0.17/minute afterward.
  Most rides fall within a 15-minute duration, as seen in the histogram of ride counts by duration. The billing structure encourages shorter rides to limit both distance and bike availability for others.
  When examining bike types, docked bikes show a longer average duration but the shortest distance. This suggests possible docking issues or faults. Note that rides by staff or during servicing have already been excluded from the data.
  Rides with durations exceeding 120 minutes were removed from the analysis to prevent skewing the results.
  ![image](https://github.com/KTamas03/citibike-tableau-challenge/assets/132874272/8db83a05-0ca2-482c-889a-53113d6811e5)



**Resource File I Used:**
  - Jul22_to_Jul23.csv

**Image Files I Used:**
  - bike icon.png
  - Citibike Logo.png
  - cycling icon.png
  - distance icon.png
  - docked bike icon.png
  - finish icon.png
  - outlier icon.png
  - time icon.png



## Getting Started

**Programs/software I used:**
 - Tableau Public: data visualisation tool, was used for creation of dashboards and stories.
 - Jupyter Notebook: python programming tool, was used for data manipulation and consolidation.

**To activate dev environment and open Jupyter Notebook:**
- Open Anaconda Prompt
- Activate dev environment, type 'conda activate dev'
- Navigate to the folder where repository is saved on local drive
- Open Jupyter Notebook, type 'Jupyter Notebook'

## Installing

**Installation Tableau Public:**
- Create a Tableau Public Account: https://public.tableau.com/app/discover
- Download and install the Tableau Public Application to your device: https://www.tableau.com/products/public/download
  
## Contributing

- How to make rounded bar charts: (https://www.bing.com/videos/riverview/relatedvideo?q=tableau%20how%20to%20make%20bar%20charts%20rounded&mid=EFC57FC28579AD2266D0EFC57FC28579AD2266D0&ajaxhist=0)

## Sources

- Icons used in tableau dashboard:
  - Citibike Logo.png (https://citibikenyc.com/system-data)
  - bike icon.png (https://www.publicdomainpictures.net/en/view-image.php?image=154290&picture=bicycle-icon)
  - cycling icon.png (https://www.iconfinder.com/icons/2659244/cycling_icon)
  - distance icon.png (https://www.vecteezy.com/vector-art/548562-distance-line-black-icon)
  - docked bike icon.png (https://thenounproject.com/icon/bicycle-parking-60650/)
  - finish icon.png (https://www.vectorstock.com/royalty-free-vector/finish-flag-icon-simple-style-vector-26752358)
  - outlier icon.png (https://thenounproject.com/icon/outliers-1503810/)
  - time icon.png (https://www.clipartkey.com/view/mwwbTm_free-time-icon-png/)

