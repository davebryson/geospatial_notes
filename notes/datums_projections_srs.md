
# Geographic Coordinate System (GCS)

A GCS is formed by 3 pieces of information: Datum, Coordinate System, and Projection.

## Datum

Datum defines the reference frame (origin) used to measure locations on Earth.  The shape of the Earth is a factor
when determining the reference frame.  Earth is commonly depicted as either a Sphere or Ellipsoid (Spheroid).  Using 
a Sphere makes calculations easier but is not the best appoximation because of flattening at the poles.

> The assumption that the earth is a sphere is possible for small-scale maps (smaller than 1:5,000,000). 
> At this scale, the difference between a sphere and a spheroid is not detectable on a map. 
> However, to maintain accuracy for larger-scale maps (scales of 1:1,000,000 or larger), 
> a spheroid is necessary to represent the shape of the earth. Between those scales, choosing to use a 
> sphere or spheroid will depend on the map's purpose and the accuracy of the data.
>
> In the last 15 years, satellite data has provided geodesists with new measurements to define the 
> best earth-fitting spheroid, which relates coordinates to the earth's center of mass. An earth-centered, 
> or geocentric, datum uses the earth's center of mass as the origin. The most recently developed and 
> widely used datum is WGS 1984. It serves as the framework for locational measurement worldwide. 
> [ESRI](http://webhelp.esri.com/arcgisdesktop/9.2/index.cfm?TopicName=Spheroids_and_spheres)

With a reference frame for the shape of the earth, a coordinate system is also needed to define locations.  There
are 3 common coordinate systems

* Geocentric (X,Y,Z): An X,Y,Z coordinate system with it's origin at the center of the Earth [ECEF](). This is the coordinate system
used by GPS systems today (and is the underpinnings of WGS84?) .  But is often converted to Geographic coordinates for users (easier to understand). 

* Geographic (latitude/longitude): Geographic (Spherical) coordinates are angular measurements used to identify locations on earth.  The latitude is the anglular measurement North and South from the Equator in the range [-90, 90]. Longitude is the anglular measurement East and West starting from the Greenwich meridian in the range [-180, 180]

* Rectangular Coordinates (X, Y):  A cartesian coordinate system using X and Y values to represent vertical and horizontal positions usually in meters.  Rectangular coordinates are best fitted for 2d maps


![Coordinate Systems](../images/coordinate_systems.png "Coordinate Systems")
[Source](http://www.sharpgis.net/post/2007/05/05/Spatial-references2c-coordinate-systems2c-projections2c-datums2c-ellipsoids-e28093-confusing.aspx)

The most common Datum used today is [WGS84 aka EPSG:4326](http://spatialreference.org/ref/epsg/4326/)

It defines the Earth as an Ellipsoid with the following information:

    GEOGCS["WGS 84",
    DATUM["WGS_1984",
        SPHEROID["WGS 84",6378137,298.257223563,
            AUTHORITY["EPSG","7030"]],
        AUTHORITY["EPSG","6326"]],
    PRIMEM["Greenwich",0,
        AUTHORITY["EPSG","8901"]],
    UNIT["degree",0.01745329251994328,
        AUTHORITY["EPSG","9122"]],
    AUTHORITY["EPSG","4326"]]

Where:
  6378137 is the Earth's radius in meters and 
  298.257223563 is the flattening factor to the shape of the Ellipsoid

WGS84 is used by most GPS systems today.

GPS calculate positions using the [ECEF]() system.  Position is then converted to WGS coordinates for readability.  Actually WGS84 is based on ECEF with the exception the coordinate system is lat/lng.  However the orgin is still at 0,0,0.


## Projection

















