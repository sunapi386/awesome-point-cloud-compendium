# awesome-point-cloud-compendium
compendium for dealing with point cloud data

## Software

- [**PDAL - Point Data Abstraction Library**](http://www.pdal.io/) is a C++ BSD library for translating and manipulating point cloud data.

- [**Potree - Visualization in thge browser**](http://www.potree.org/) Popular tool for visualizing point cloud data.

- [**MeshLab**](http://meshlab.sourceforge.net/). Open source, portable, and extensible system for the processing and editing of unstructured 3D triangular meshes

- [**CloudCompare**](http://www.danielgm.net/cc/). 3D point cloud and mesh processing software 
Open Source Project

- [**PCL - Point Cloud Library**](http://pointclouds.org/) is a standalone, large scale, open project for 2D/3D image and point cloud processing.

- [**libLAS**](http://www.liblas.org/) is a C/C++ library for reading and writing the very common LAS LiDAR format. 


## Algorithms

- [Pose Optimization]() Simultaneous Localization and Mapping (SLAM) problems can be posed as a pose graph optimization problem. We have developed a nonlinear optimization algorithm that solves this problem quickly, even when the initial estimate (e.g., robot odometry) is very poor. [MIT’s Graph Based SLAM](http://rvsn.csail.mit.edu/graphoptim/).

- [Point Set Registration](https://en.wikipedia.org/wiki/Point_set_registration) The Orthogonal Procrustes Problem and Kabsch Algorithm requires correspondence between point sets as an input whereas Iterative Closest Point treats correspondence as a variable to be estimated. 

- [Photogrammetry](https://en.wikipedia.org/wiki/Photogrammetry) Well known method since the geographical survey days where photographs were used. Matches interest points and calculates the angles to approximate their locations using triangulation. 

- [Pose Graph Optimization]() To optimize a set of poses, given relative pose between those poses. The difference is that point set registration problems only are moving "model" point set such that the difference between and the static "scene" set is minimized - without taking into consideration that the points in the model set may be captured while moving. During a single lidar scan rotation, the lidar may be moved (as mounted on a vehicle), so the points that are captured first and last differ with respect to their point of origin. In other words, using point cloud from a rotating laser scanner involves recovery of motion and correction of motion distortion in the lidar cloud.

## Databases

CMU Databases group maintains a [Database of Databases](https://dbdb.io/) and it’s mostly well populated. It’s missing the geospatial databases like GeoMesa/GeoWave, but you can find other info. 

A spatial data warehouse system is necessary for the effective handling of large-scale geospatial data. 

- [Accumulo]()
- [GeoMesa]() Both are based on large key-value stores where large data can be partitioned automatically.
- [GeoWave]() developed in part by US National Geospatial-Intelligence Agency.

## Formats

### Point Cloud

I'll numerically order these in approximate ordering of what I commonly see, and leave bullets for those I've not personally used.

1. [LAS](https://www.asprs.org/divisions-committees/lidar-division/laser-las-file-format-exchange-activities) The most common open file format for the interchange of 3-dimensional point cloud data from aerial imaging. Developed primarily for lidar point cloud data this format supports the exchange of any 3-dimensional x,y,z tuplet. The columns are quite fixed (well defined) so using it for terrestrial applications can be challenging.

2. [EPT](https://entwine.io/entwine-point-tile.html) Entwine Point Tile (EPT) is a simple and flexible octree-based storage format for point cloud data, used in the Entwine and read/writable in PDAL. 

3. [PLY](https://en.wikipedia.org/wiki/PLY_(file_format)) Uncompressed text based, and easily read, can export to text or binary file. Can also save the camera pose.

- [PCD](http://www.pointclouds.org/about/) The format used in Point Cloud Library (or PCL) is a large scale 2D/3D image and point cloud processing, free for commercial and research use. Supports viewpoint information.

- [ROS PointCloud2](http://docs.ros.org/api/sensor_msgs/html/msg/PointCloud2.html) In robotics, ROS format is common and point clouds messages are defined in sensor_msgs/PointCloud2. Most likely they will convert it to .pcd because PCL is the de facto library for working with point clouds in ROS.

- [XYZ](https://en.wikipedia.org/wiki/XYZ_file_format) This is a popular chemical format for describing atomic coordinates, used in computational chemistry, but it can be used for point cloud.

- [E57](http://www.libe57.org/) A compact, vendor-neutral format for storing point clouds, images, and metadata produced by 3D imaging systems, such as laser scanners. The file format is specified by the ASTM, an international standards organization, and it is documented in the ASTM E2807 standard. E57 files do not have a projection. The E57 specification uses a subset of XML that has been extended to support efficient storage of large amounts of binary data. An E57 file is encoded as a hierarchical tree structure, some of which is encoded in XML, and some of which is encoded in a binary format that is not XML. The bulk of the data, including point data and images, is encoded in the binary sections for efficiency. Metadata, such as sensor pose information, is encoded in XML. The binary sections are not embedded in the XML section. Instead, they are located in separate sections of the file and referenced from the XML section.


### Binary
- [TIFF]() is lossless and can store arbitrary data, commonly used in digital terrain models and ground labeling. See [PDAL tutorial for point cloud ground classification](https://pdal.io/workshop/exercises/analysis/ground/ground.html#workshop-ground)
- [PNG]() is com- [KML]() (Keyhole Markup Language) is an XML-based language schema for expressing geographic data in an Earth browser, such as Google Earth or Google Maps. KML uses a tag-based structure with nested elements and attributes. For GeoServer, KML files are distributed as a KMZ, which is a zipped KML file.
- [JPEG]() The JPEG is a compressed graphic file format, with some loss of quality due to compression. It is best used for photos and not recommended for exact reproduction of data.
- [GIF]() The GIF (Graphics Interchange Format) is a bitmap image format best suited for sharp-edged line art with a limited number of colors. This takes advantage of the format’s lossless compression, which favors flat areas of uniform color with well defined edges (in contrast to JPEG, which favors smooth gradients and softer images). GIF is limited to an 8-bit palette, or 256 colors.
- [SVG]() SVG (Scalable Vector Graphics) is a language for modeling two-dimensional graphics in XML. It differs from the GIF and JPEG in that it uses graphic objects rather than individual points.
- [TIFF]() TIFF (Tagged Image File Format) is a flexible, adaptable format for handling multiple data in a single file. GeoTIFF contains geographic data embedded as tags within the TIFF file.
- [PNG]() The PNG (Portable Network Graphics) file format was created as the free, open-source successor to the GIF. The PNG file format supports truecolor (16 million colors) while the GIF supports only 256 colors. The PNG file excels when the image has large, uniformly coloured areas.
- [OpenLayers]() is an open source JavaScript library for displaying map data in web browsers. The OpenLayers output has some advanced filters that are not available when using a standalone version of OpenLayers. Further, the generated preview contains a header with easy configuration options for display. Version 3 of the OpenLayers library is used by default. Version 3 can be disabled with the ENABLE_OL3 (true/false) format option or system property. For older browsers not supported by OpenLayers 3, version 2 is used regardless of the setting.
- [PDF]() (Portable Document Format) encapsulates a complete description of a fixed-layout 2D document,including any text, fonts, raster images, and 2D vector graphics.
- [GEOTIFF]() Georeferencing information to be embedded within a TIFF file. May include: coordinate transforms, map projection, coordinate systems, ellipsoids, datums, and anything else necessary to establish the exact spatial reference for the file.
monly used for rastering large map tiles.
- [KML]() (Keyhole Markup Language) is an XML-based language schema for expressing geographic data in an Earth browser, such as Google Earth or Google Maps. KML uses a tag-based structure with nested elements and attributes. For GeoServer, KML files are distributed as a KMZ, which is a zipped KML file.
- [JPEG]() The JPEG is a compressed graphic file format, with some loss of quality due to compression. It is best used for photos and not recommended for exact reproduction of data.
- [GIF]() The GIF (Graphics Interchange Format) is a bitmap image format best suited for sharp-edged line art with a limited number of colors. This takes advantage of the format’s lossless compression, which favors flat areas of uniform color with well defined edges (in contrast to JPEG, which favors smooth gradients and softer images). GIF is limited to an 8-bit palette, or 256 colors.
- [SVG]() SVG (Scalable Vector Graphics) is a language for modeling two-dimensional graphics in XML. It differs from the GIF and JPEG in that it uses graphic objects rather than individual points.
- [TIFF]() TIFF (Tagged Image File Format) is a flexible, adaptable format for handling multiple data in a single file. GeoTIFF contains geographic data embedded as tags within the TIFF file.
- [PNG]() The PNG (Portable Network Graphics) file format was created as the free, open-source successor to the GIF. The PNG file format supports truecolor (16 million colors) while the GIF supports only 256 colors. The PNG file excels when the image has large, uniformly coloured areas.
- [OpenLayers]() is an open source JavaScript library for displaying map data in web browsers. The OpenLayers output has some advanced filters that are not available when using a standalone version of OpenLayers. Further, the generated preview contains a header with easy configuration options for display. Version 3 of the OpenLayers library is used by default. Version 3 can be disabled with the ENABLE_OL3 (true/false) format option or system property. For older browsers not supported by OpenLayers 3, version 2 is used regardless of the setting.
- [PDF]() (Portable Document Format) encapsulates a complete description of a fixed-layout 2D document,including any text, fonts, raster images, and 2D vector graphics.
- [GEOTIFF]() Georeferencing information to be embedded within a TIFF file. May include: coordinate transforms, map projection, coordinate systems, ellipsoids, datums, and anything else necessary to establish the exact spatial reference for the file.

### Text

- [AtomPub]() (Atom Publishing Protocol) is an application-level protocol for publishing and editing Web Resources using HTTP and XML. Developed as a replacement for the RSS family of standards for content syndication, Atom allows subscription of geo data.
- [GeoRss]() RSS (Rich Site Summary) is an XML format for delivering regularly changing web content. GeoRss is a standard for encoding location as part of a RSS feed.supports Layers Preview produces a RSS 2.0 documents, with GeoRSS Simple geometries using Atom.
- [GeoJSON]() is a lightweight data-interchange format based on the JavaScript programming language. This makes it an ideal interchange format for browser based applications since it can be parsed directly and easily in to javascript. GeoJSON is a plain text output format that add geographic types to JSON.
- [CSV]() (Comma Separated Values) files are text files containing rows of data. Data values in each row are separated by commas. CSV files also contain a comma-separated header row explaining each row’s value ordering. GeoServer’s CSVs are fully streaming, with no limitation on the amount of data that can be outputted.

## Papers 

