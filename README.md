# Generate Interactive Map of Fake Convenience Stores

## Used in the motion picture Remote

This code was used to create an interactive map using the Google API.

### get_stop_n_grab.py

Uses the Maps API to search for a list of stores. 
For privacy reasons, the API key and the names of the stores used have been redacted.

GPS_coords were found manually to define the search area that I was interested in. The Maps
API uses those as center points for a search within a certain radius (also user defined).

Since I was primaily interested in a fictional visualization, there are no checks
for whether the results returned are accurate or complete, so be cautioned if
that is what you want to use it for.

The results are checked for duplicates and then written as a dictionary to a .json file

### stop_n_grab_locations.html

This file creates the actual map. You have to create a local server using:

python3 -m http.server 3000

and then navigate to

http://localhost:3000/[your_file_location]

### load_map.js

The map as currently configured uses this file to load markers for each location found
with get_stop_n_grab.py and stored in stop_n_grab_list.json.

For reasons having to do with the plot of the film, when you click once on the map, 
all stores that are not in Pennsylvania disappear. A second click removes most of the
Pennsylvania stores, and a third click resets the markes to their original state.