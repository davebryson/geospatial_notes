
# Image/Tiling Refresher

Image Pixels: 2d with an orthogonal coordinate system.

    (0.0)
      -------------------> X
      |
      |
      |
      |
      |
      |
      |

      Y

Lossy: (JPEG) Compression by throwing some bits away.  But many lossy algorithms can make an almosy identical looking image

Lossless: (GIF, PNG) Compression without losing bits

Georeferences Imagery: Usually bounding rectangle or single coordinate with resolution per pixel.  Stored *somewhere* with imagery

Orthorectified Imagery: Geometrically corrected to accurately represent the Earth. Often involves adjusting the image for Topo relief and Camera tilt.


## Creating multi-resolution tiles from a single image

General process:

* geolocate: find the pixel in the source we need

* interpolate: calc new target pixel from source


Interpolation uses one of the approaches below:

* Nearest Neighbor: Simplest, computationally efficient. Find the source pixel closet (distance) to the target pixel

* Bilinear: Uses weighted average of 4 neighbor pixels.

* Bicubic: Weighted average of 16 neighbors


## Build a Tile Pyramid

Degree Per Pixel: 

    DPP = (360.0 / 2^i) * p

    where:
    i = zoom level
    p = number of pixels per tile

* Choose a base level that closely matches the resolution of the imagery.  The base level is the highest zoom level - most detailed view.  You can use Degree Per Pixel
* With a base level you can derive lower resolution tiles. 4 base tiles become 1 lower tile












