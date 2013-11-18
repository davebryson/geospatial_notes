
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
used by GPS systems today.  But is often converted to Geographic coordinates for users (easier to understand). 

* Geographic (latitude/longitude): Georgaphic coordinates are angular measurements used to identify locations on earth.  The latitude is the anglular measurement North and South from the Equator in the range [-90, 90]. Longitude is the anglular measurement East and West starting from the Greenwich meridian in the range [-180, 180]

* Rectangular Coordinates (X, Y):  A cartesian coordinate system using X and Y values to represent vertical and horizontal positions usually in meters.  Rectangular coordinates are best fitted for 2d maps


![Coordinate Systems](../images/coordinate_systems.png "Coordinate Systems")

The most common Datum used today is [WGS84]()  













