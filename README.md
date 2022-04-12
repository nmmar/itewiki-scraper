# Itewiki company details

BeautifulSoup based Itewiki website scraper. First, scrapes the company list listed at https://www.itewiki.fi/lista-yrityksista. Appends data to the main table `itewiki.yrityslista` including rowise company information. Tables `liiketoimintaprosessi`, `erikoisosaaminen`, `teknologia`, `toimialakokemus`, `tarjonta`, and `tagit` under `itewiki` schema contain stacked data by the column `y_tunnus` and are appended accordingly.


## Databricks notebook 

File `src/itewiki_scraper_snowflake.ipynb`. There is a dedicated Azure Data Factory pipeline build on this file that is triggered fortnightly (from 2019-11-18 on) on Monday at 03:00AM (UTC). 

Test mode (i.e. `test = True`) writes to `itewiki.temp` and `itewiki.temp_liiketoimintaprosessi` tables.
        

## Old remarks:

* About 2000 companies.
* The scheduled run takes approximately 10 minutes.
* Few broken Business IDs included. Only around 1%. For instance, FI2636051, DE 176183, Y-tunnus 1,
and HRB 179863.
