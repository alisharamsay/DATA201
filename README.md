# DATA201

# Source: Inside Airbnb - New Zealand listings.csv (monthly snapshots, Oct 2025 - June 2026)

# This describes the columns in the combined dataset (all_chch), which is 
# filtered to Christchurch City only and concatenated across all 9 monthly snapshots

# id (integer): Airbnb's unique identifier for the listing
# name (string) : name of the listing
# host_id(integer) : Airbnb's unique identifier for the host/user
# host_name (string) : Name of the host. Usually just the first name(s).
# neighbourhood_group (string): The city/district the listing belongs to (filtered to "Christchurch City" only in this dataset)
# neighbourhood (string): The neighbourhood as geocoded using the latitude and longitude against neighborhoods as defined by open or public digital shapefiles.
# latitude (numeric) :	Uses the World Geodetic System (WGS84) projection for latitude and longitude.
# longitude (numeric) : Uses the World Geodetic System (WGS84) projection for latitude and longitude.
# room_type (string) : Has 3 room types - entire place, private or shared
# price (numeric) : daily price in local currency.
# minimum_nights (integer) : minimum number of night stay for the listing 
# number_of_reviews (integer) : The number of reviews the listing has
# last_review (date) : The date of the last/newest review
# reviews_per_month (numeric) :The average number of reviews per month the 
# calculated_hostings_count (integer) :The number of listings the host has in the current scrape
# availability/365 (integer) : number of days listings available in 365 days
# number_of_reviews_ltm (integer) : y	The number of reviews the listing has (in the last 12 months) 
# license (string) : The listing's license/registration number, where required and provided. Often missing.
# month_year (string): Added during processing (not part of the original Inside Airbnb data) - indicates which monthly snapshot the row came from, e.g. "2025-10"