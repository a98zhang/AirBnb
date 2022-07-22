```

import geopandas
import geopy

geocodes = listings_by_neighbourhood.neighbourhood.apply(lambda query: geopandas.tools.geocode("%s, Seattle WA" % query))
listings_by_neighbourhood['geometry'] = geocodes.apply(lambda loc: loc.geometry)

gdf = geopandas.GeoDataFrame(listings_by_neighbourhood, crs="EPSG:4326")
gdf.plot()


```