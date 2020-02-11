---
title:  "Hong Kong Bus Data Analytics"
last_modified_at: 2018-08-05T17:35:00+08:00
---
An exploration project of bus data from Data.Gov.HK and GTFS

## Introduction
------------

Recently, I found out that Google Map does not show the best route observation and therefore, I did some digging and wrote up this project page on some of findings and work. Indeed, the Hong Kong government has grouped all transport data into their own API or database files on [Data.Gov.HK](https://data.gov.hk/en-data/dataset/hk-td-tis_3-routes-and-fares-of-public-transport). This project was in separated into 2 parts mainly.

1.  Mapping of bus route data from the Data.Gov.HK to the Google Map's GTFS format
2.  Plotting of interesting statistics from the bus data

## Part 1 - Data Mapping
----------------------

The bus data from from the Data.Gov.HK was mapped to the Google Map's GTFS format.The script used can be found from [the link](https://gist.github.com/cameronlai/3a2475e422fb1c26b74a91162a1daf54). After mapping the data to a certain, the GTFS viewer can be used to view the results and a screenshot is shown below. 

![alt text](http://cameronlai.com/wp-content/uploads/2018/08/bus_data_analytics_gtfs_viewer_screenshot-1024x570.jpg)
*Bus Data Analytics with GTFS Schedule Viewer*

From the data conversion exercise, the following points were learnt.

1.  File format
    * The file format used to store the data is \*.mdb, which is a Microsoft Access database format. In order to access the data, using Windows is much easier. In fact, a much simpler csv file format may benefit users from different operating systems.
2.  Location Coordinates
    * The data.gov.HK actually uses the HK80 coordinate system instead of the widely used WSG84 coordinate system.
3.  Lack of information from data.gov.HK
    * Bus Schedule Information, which is required in stop\_times.txt and frequencies.txt.
    * Bus Transfer Price Discount
        * For the GTFS side, I am not entirely sure whether the fare\_rules.txt can represent the required logic.
    * Bus Calendar Information
        * This represents whether the bus will only be available for certain days of the year.
4.  Bus routes handled by 2 agencies
    * In Hong Kong, there are some bus routes (e.g. 104) that are handled by 2 companies together. The only way to handle this in GTFS is to have a new agency id.

In the long term, I believe it will be highly beneficial for Hong Kong to maintain its own GTFS data format as a public data set. This will allow different applications like Google Map to have the best route information in order to advice the best travel route for customers. In addition, the experience from Google Map has established a great file format, which would include much more information that what the data.gov.HK has published at the moment.

## Part 2 - Interesting Statistics
--------------------------------

With the bus data in hand, I also plotted out some interesting statistics.

### Box plot of number of bus stops per bus route

From the graph below, it shows that the median of each company is about 30 stations per bus route. Strangely, the largest number of bus stops per bus route for KMB has about 150 stations, which means around 75 stations per trip. By checking the data, the bus route is bus 53, which has 74 stations one way already. Here is a link to bus 53 route information on [moovit](https://moovitapp.com/index/en/public_transit-line-53-Hong_Kong-2741-858000-596895-0) and [KMB](http://search.kmb.hk/KMBWebSite/?action=routesearch&route=53&lang=en) website, which validates the results.   \[caption id="attachment\_662" align="aligncenter" width="800"\][![Box plot of number of bus stops per bus route](http://cameronlai.com/wp-content/uploads/2018/08/bus_data_analytics_number_of_bus_stops_per_bus_route.png)](http://cameronlai.com/wp-content/uploads/2018/08/bus_data_analytics_number_of_bus_stops_per_bus_route.png) Box plot of number of bus stops per bus route

### Box plot of distance between bus stops

The distance between bus stops is calculated using the [inverse function](https://jswhit.github.io/pyproj/pyproj.Geod-class.html) in the [pyproj library](https://pypi.org/project/pyproj/). This already includes the correction from longitude and latitude to distance on ground. Interestingly. The median distance between bus stop for each company is about 400m. Using 10 minute per km walking speed, this would take about 4-5 minutes for a normal person to walk from one bus stop to another. 

![alt text](http://cameronlai.com/wp-content/uploads/2018/08/bus_data_analytics_distance_between_bus_stops.png)]
*Box plot of distance between bus stops*

### Box plot of price between bus stops

The fare per bus stop is calculated by the full fare divided by the number of bus stops in the trip. The discounted price is the middle is not included in the calculation. The median value is about $0.5 HKD per bus stop. This shows that each company has a very similar pricing strategy, when compared to their competitors. The most expensive fare per bus stop is [NA21](https://moovitapp.com/index/en/public_transit-line-NA21-Hong_Kong-2741-926722-514588-0), which gives about $5.35 HKD per bus stop. 

![alt text](http://cameronlai.com/wp-content/uploads/2018/08/bus_data_analytics_fare_per_bus_stop.png)
*Box plot of fare per bus stop*

Conclusion
----------

It is great that the HK government has taken the first step to open up the bus data with the data.gov.HK website and APIs. I believe the openness of data will help application developers to make better applications for building future "Smart Cities". I believe that the following points still need to be tackled.

1.  How to guarantee the correctness and completeness of the public bus data?
    - This can be done either by the public or by the government.
2.  When would Hong Kong government enforce bus companies to follow a global standard like GTFS?
3.  How to deliver real-time bus data into developers' hands with sufficient security?

For your information, [this article](https://www.hk01.com/01%E5%8D%9A%E8%A9%95-%E6%94%BF%E7%B6%93%E7%A4%BE/118154/%E6%99%BA%E6%85%A7%E5%9F%8E%E5%B8%82-%E4%BE%86%E7%A8%BF-%E9%96%8B%E6%94%BE%E5%AF%A6%E6%99%82%E4%BA%A4%E9%80%9A%E6%95%B8%E6%93%9A-%E9%A6%99%E6%B8%AF%E9%82%84%E8%A6%81%E5%A4%9A%E4%B9%85) shows that one of our legislative council members, Charles Mok has already raised the issue of following GTFS format back in 2017 already. Hope that the Hong Kong government can open up more data with the best format possible. This will enable application developers to develop applications that make people's life more convenient and more efficient.