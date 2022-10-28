# location_matching
## Exploratory Data Analysis: Foursquare Location Matching

### Contents

#### 1.-Introduction
#### 2.-Train-Test-Split
#### 3.-Data-Manipulation-and-Pre-processing
#### 4.-Modelling-and-Feature-Engineering
#### Conclusion


# Introduction
## Point of Interest

A point of interest (POI) is a specific point location that someone may find useful or interesting. An example is a point on the Earth representing the location of the Eiffel Tower, or a point on Mars representing the location of its highest mountain, [Olympus Mons](https://en.wikipedia.org/wiki/Olympus_Mons). Most consumers use the term when referring to hotels, campsites, fuel stations or any other categories used in modern automotive navigation systems. Users of a mobile device can be provided with geolocation and time aware POI service that recommends geolocations nearby and with a temporal relevance (e.g. POI to special services in a ski resort are available only in winter). The notion of POI is widely used in cartography, especially in electronic variants including GIS, and GPS navigation software.

## The Problem of POI Matching

It is useful to combine POI data obtained from multiple sources for effective reusability. One issue in merging such data is that different dataset may have variations in POI name, address, and other identifying information for the same POI. It is thus important to identify observations which refer to the same POI. The process of POI matching involves finding POI pairs that refer to the same real-world entity, which is the core issue in geospatial data integration and is perhaps the most technically difficult part of multi-source POI fusion. The raw location data can contain noise, unstructured information, and incomplete or inaccurate attributes, which makes the task even more difficult. Nonetheless, to maintain the highest level of accuracy, the data must be matched and duplicate POIs must be identified and merged with timely updates from multiple sources. A combination of machine-learning algorithms and rigorous human validation methods are optimal for effective de-duplication of such data.

## About Foursquare

[Foursquare Labs Inc.](https://foursquare.com/), commonly known as Foursquare, is an American location technology company and data cloud platform. The company's location platform is the foundation of several business and consumer products, including the [Foursquare City Guide](https://en.wikipedia.org/wiki/Foursquare_City_Guide) and [Foursquare Swarm](https://en.wikipedia.org/wiki/Foursquare_Swarm) apps. Foursquare's products include Pilgrim SDK, Places, Visits, Attribution, Audience, Proximity, and Unfolded Studio. It is one of the leading independent providers of global POI data and is dedicated to building meaningful bridges between digital spaces and physical places. Trusted by leading enterprises like Apple, Microsoft, Samsung, and Uber, Foursquare's tech stack harnesses the power of places and movement to improve customer experiences and drive better business outcomes.

## Project Objective

The goal of the project is to match POIs together. Using the provided dataset of over one-and-a-half million places entries, heavily altered to include noise, duplications, extraneous, or incorrect information, the objective is to produce an algorithm that predicts which place entries represent the same POI. Each place entry in the data includes useful attributes like name, street address, and coordinates. Efficient and successful matching of POIs will make it easier to identify where new stores or businesses would benefit people the most.


## Data

**Source:** https://www.kaggle.com/competitions/foursquare-location-matching/data

The data considered in the competition comprises over one-and-a-half million place entries for hundreds of thousands of commercial Points-of-Interest (POIs) around the globe. Though the data entries may represent or resemble entries for real places, they may be contaminated with artificial information or additional noise.

The training data comprises eleven attribute fields for over one million place entries, together with:
- `id` : A unique identifier for each entry.
- `point_of_interest` : An identifier for the POI the entry represents. There may be one or many entries describing the same POI. Two entries *match* when they describe a common POI.


## Conclusion
- **XGBoost**, (*boosting algorithm*) performed slightly better than **KNN** even after hyperparameter Tuning
