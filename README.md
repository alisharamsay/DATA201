# DATA201 - Christchurch Airbnb Listings Analysis

This project analyses Christchurch Airbnb listing trends from Oct 2025-June 2026 using data 
from Inside Airbnb, combining 9 monthly snapshots into a single dataset for exploratory analysis.

**Team members:** Alice Kuo, Charlie Harris and Alisha Ramsay

## Data Dictionary
Source: Inside Airbnb - New Zealand listings.csv (monthly snapshots, Oct 2025 - June 2026)

This describes the columns in the combined dataset (all_chch), which is 
filtered to Christchurch City only and concatenated across all 9 monthly snapshots.
Descriptions below are adapted from Inside Airbnb's official Data Dictionary: 
https://docs.google.com/spreadsheets/d/1iWCNJcSutYqpULSQHlNyGInUvHg2BoUGoNRIGa6Szc4/edit?usp=sharing


id (integer): Airbnb's unique identifier for the listing
name (string): Name of the listing
host_id(integer): Airbnb's unique identifier for the host/user
host_name (string): Name of the host. Usually just the first name(s).
neighbourhood_group (string): The city/district the listing belongs to (filtered to "Christchurch City" only in this dataset)
neighbourhood (string): The neighbourhood as geocoded using the latitude and longitude against neighborhoods as defined by open or public digital shapefiles.
latitude (numeric):	Uses the World Geodetic System (WGS84) projection for latitude and longitude.
longitude (numeric): Uses the World Geodetic System (WGS84) projection for latitude and longitude.
room_type (string): Has 3 room types - entire place, private or shared
price (numeric): daily price in local currency.
minimum_nights (integer): minimum number of night stay for the listing 
number_of_reviews (integer): The number of reviews the listing has
last_review (date): The date of the last/newest review
reviews_per_month (numeric): The average number of reviews per month the listing has over the lifetime of the listing.

calculated_host_listings_count (integer): The number of listings the host has in the current scrape
availability_365 (integer): number of days listings available in 365 days
number_of_reviews_ltm (integer): The number of reviews the listing has (in the last 12 months) 
license (string): The listing's license/registration number, where required and provided. Often missing.
month_year (string): Added during processing (not part of the original Inside Airbnb data) - indicates which monthly snapshot the row came from, e.g. "2025-10"


## Datasheet

### Motivation
This dataset was created by Inside Airbnb, a mission-driven activist project 
that provides data quantifying the impact of short-term rentals on housing 
and residential communities, and supports advocacy for policies to protect 
cities from these impacts. It is run independently of Airbnb, by Murray Cox, 
and is not commercially funded - it's sustained through donations.

For this project, the New Zealand dataset was downloaded, filtered to 
Christchurch City, and combined across 9 monthly snapshots (Oct 2025 - 
June 2026) by Alice, Charlie and Alisha for DATA201, to analyse trends 
in Christchurch Airbnb listings over time.

### Composition
- Each row represents a single Airbnb listing active in Christchurch City 
  at the time of that month's scrape.
- The combined dataset (all_chch) contains 28796 rows across 9 monthly 
  snapshots.
- 19 columns, described in the data dictionary above.
- Missing data: license has the most missing values (28,795), as 
  registration numbers aren't required or provided for all listings. 
  price is missing for 10,667 rows. last_review and reviews_per_month 
  are each missing 2,627 values (listings with no reviews yet). 
  minimum_nights has 37 missing values, and host_name has 1. All other 
  columns have no missing values.
- No sensitive personal data beyond host first name and neighbourhood-level 
  location (not exact address).
- Represents Airbnb hosts and listings in Christchurch City only; excludes 
  the rest of New Zealand and any listings removed before each scrape date.

### Collection process
- Inside Airbnb collects the data by scraping Airbnb's public website 
  each month, without needing to log in.
- Exact snapshot dates used in this project: 5 Oct 2025, 7 Nov 2025, 
  11 Dec 2025, 16 Jan 2026, 13 Feb 2026, 17 Mar 2026, 16 Apr 2026, 
  23 May 2026, 19 June 2026.
- No direct consent was obtained from hosts, as the data reflects publicly 
  listed information already visible on Airbnb's site.
  
### Preprocessing, cleaning and labelling
- Each monthly file was filtered to the "Christchurch City" neighbourhood_group
- A derived column, month_year, was added to each monthly file to record 
  which snapshot it came from (e.g. "2025-10").
- The 9 filtered files were concatenated into all_chch.
- No values were imputed; missing data was left as NA.
- No manual labelling was performed - all columns are as provided, aside 
  from month_year.

### Uses
- Intended for this DATA201 coursework project, exploring trends in 
  Christchurch Airbnb listings (price, availability, room types, etc.) 
  over a 9-month period.
- Inappropriate uses: identifying or contacting individual hosts, treating 
  this as a complete record of all Airbnb activity in Christchurch, or 
  redistributing the dataset outside this coursework (per Inside Airbnb's 
  guidelines against republishing their data).
  
### Distribution
- Original source data: https://insideairbnb.com/get-the-data/, licensed 
  under CC0. Inside Airbnb states that "Murray Cox has waived all 
  copyright and related or neighboring rights to Inside Airbnb Data."
- Inside Airbnb's community guidelines ask users to "only take the data 
  you need," not to scrape the site directly, and not to republish the 
  data, since "this site provides the best context for the data."
- The combined, filtered dataset (all_chch_listings.csv) produced by this 
  project is stored in this repository's week_5_datasets folder for 
  coursework purposes only, in line with the above guidelines.
  
### Maintenance
- The original data is maintained and updated monthly by Inside Airbnb 
  (Murray Cox).
- The combined Christchurch dataset in this repository will be maintained 
  for the duration of this DATA201 project and is not planned to be 
  updated beyond the June 2026 snapshot.
  
  