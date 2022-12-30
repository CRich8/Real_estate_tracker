# Reak Estate Market Analysis: Hoboken, NJ (07030)
Due to the rise in prices of houses in New Jersey, I was interested to see if investing in real estate was still a great opportunity for those looking for passive income. I chose Hoboken, New Jersey as the market to analyze because I personally am interested in this city and because it is in high demand both on Zillow and Airbnb.  The goal is to create a dashboard for an investor to use to analyze the real estate market of interest. I collected data from multiple sources including Zillow, Airbnb, Realtor.com and FHFA in order to get an overview of the real estate market of Hoboken, NJ.

## Overview of the pipeline
The pipeline is setup on GCP to ingest each dataset and perform ddaily transformation in order to provide up-to-date data for performing analytics. The project is desiigned as per the diagram, below. Airflow, hosted by Docker, is used to orchestrate the ingestion and scraping of active listings on Zillow to Google Cloud Storage (GCS). Airbnb data is extracted from Rapid API and transformed into a CSV for ingestion to GCS. Census and Realtor.com data are downloaded as CSV files from their sites and uploaded to GCS. DBT transforms the raw data to a staging layer in BigQuery where the tables are prepared for Tableau.

![Pipeline overview](https://github.com/CRich8/Real_estate_tracker/blob/main/images/Real_Estate_Project_Overview.png)

## Data Analysis
It is no secret that the average house price in America has been on a sharp rise in the last few decades. In the last 20 years, the House Price Index in New Jersey has more than doubled.

The definition of House Price Index from the FHFA website:
> *The FHFA HPI is a broad measure of the movement of single-family house prices. The FHFA HPI is a weighted, repeat-sales index, meaning that it measures average price changes in repeat sales or refinancings on the same properties*

![NJHPI](https://github.com/CRich8/Real_estate_tracker/blob/main/images/NJHPI.png)

There are many factors which influence the housing market. Part of the reason for such a sharp increase is due to the lower volume of active listings. The supply of availble homes to purchase are decreasing while simultaneaously, the demand for houses has increased. The laws of supply and demand in this relationship clearly are responsible for the price increase. One solution to this problem is to improve the zoning laws in New Jersey. Local municipalities should focus on expanding high density zoning to increase the supply of housing.

![NJALC](https://github.com/CRich8/Real_estate_tracker/blob/main/images/NJALC.png)

To meet the needs of an investor looking to purchase a house, I scraped active listings from Zillow.com. I displayed the data in a map and table to easily identify important details of a listing.

![Active Listings](https://github.com/CRich8/Real_estate_tracker/blob/main/images/Active_Zillow_Listings_Map.png)




