# image-pairs-stereo-capacity
Estimate the stereoscopic capacity (B/H ratio) of a pair of images from the Pleiades or SPOT6-7 satellites

Very high resolution satellites, such as Pleiades and SPOT6-7, can acquire images in stereo or tri-stereo modes. Still, two monoscopic acquisitions can be combined to produce a digital surface model (DSM). howstereo.py can help you to choose which pairs of images offer the best configuration in terms of stereoscopic capacity.

For those agile satellites, the incidence angle, which is used to calculate the B/H ratio, is decomposed in the scan and ortho-scan directions (see the Pleiades and SPOT6-7 user guides for more details). For each acquisition, the scan, ortho-scan and scan azimuth angles are provided in the Airbus archive catalog (http://www.intelligence-airbusds.com/geostore/).

Of course, you should also look at other parameters for choosing the images, such as their common footprint, cloud and snow cover, the time difference between the two acquisitions (which induces changes between the two images and therefore potential correlation issues).

### Usage:

```
howstereo.py --incid1 scan ortho --az1 azimuth --incid2 scan ortho --az2 azimuth [-h] [--show_plot]
```
Mandatory arguments:
```
--incid1 scan ortho  incidence angles for image 1 (in degrees)
--az1 azimuth        scan azimuth for image 1 (in degrees)
--incid2 scan ortho  incidence angles for image 2 (in degrees)
--az2 azimuth        scan azimuth for image 2 (in degrees)
```
Optional arguments:
```
-h, --help           show this help message and exit
--show_plot          show a 3D, interactive plot
```

### Example:
- Image 1 has an incidence of -5.44° in the scan direction, 7.07° in the ortho-scan direction and a scan azimuth of 48.63°.
- Image 2 has an incidence of -28.34° in the scan direction, 15.28° in the ortho-scan direction and a scan azimuth of 24.34°

`howstereo.py --incid1 -5.44 7.07 --az1 48.63 --incid2 -28.34 15.28 --az2 24.34 --show_plot`


### Todo:
Allow to input more than 2 images and calculate a B/H for each pair
