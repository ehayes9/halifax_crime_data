### Overview

This repo contains scripts for gathering crime data from Halifax Regional Municipality's open data API. Using a get request the data is returned in a json file, upon which the key:value pairs are extracted, modelled and merged to form a dataframe. 

Only the previous 7 days of crime data are made available via [Halifax Open Data](http://catalogue-hrm.opendata.arcgis.com/).

When scheduled to run daily (or weekly at a minimum) this script connects to the Halifax Open Data API, and appends the new crime records to your dataset based on the event date. 

### Outcome

Over time, running this script will provide a rich dataset for analysis of crime in the HRM, and will make for an interesting project. 

### Files

The `main.py` script is intended to be fully automated via Google Cloud Platform (see below). The script queries the BigQuery table to determine the most recent record, and appends new records by writing to the existing table.

### Automating data gathering using Google Cloud Platform

This project is an ideal use case for automation. Fortunately this is made easy with Google Cloud Platform:

- create a project, and a dataset in BigQuery
- create a cloud function from the script, and set it to be triggered by an http request
- using cloud scheduler, schedule the cloud function created to run weekly at a minimum




 
