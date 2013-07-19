producing this model:
- grab srtm data and unzip it (`cd srtm && wget http://dds.cr.usgs.gov/srtm/version2_1/SRTM1/Region_01/N45W122.hgt.zip`)
- build an image with gdal -- `gdaldem color-relief srtm/N45W122.hgt srtm/colormap.txt hood.tiff`
- crop it a little (just to hood)
- `sudo apt-get install png23d`
- `png23d -v -t x -f surface -o stl -l 128 -d 99.6 -w 100 hood-cropped-mtnonly.png hood-cropped-mtnonly.stl`
