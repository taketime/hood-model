producing this model:
- `apt-get install gdal`
- `apt-get install python-gdal`
- `sudo apt-get install png23d`
- grab srtm data and unzip it (`cd srtm && wget http://dds.cr.usgs.gov/srtm/version2_1/SRTM1/Region_01/N45W122.hgt.zip`)
- fill in data gaps -- `gdal_fillnodata.py src dst`
- build an image with gdal -- `gdaldem color-relief srtm/N45W122.hgt monday/colormap.txt hood.tiff`
- crop it a little (just to hood), save as PNG
- `png23d -v -t x -f surface -o stl -l 128 -d 90 -w 200 -h 200 hood-filled-cropped.png hood-filled-cropped-l128-d90-w200-h200.stl`
- export an x3g in makerware
