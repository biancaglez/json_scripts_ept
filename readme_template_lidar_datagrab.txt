template_lidar_datagrab.json 
was auto generated on the USGS website is: http://usgs-lidar-public.s3.amazonaws.com/NM_NorthCentral-B3_2017/ept.json
the boundary was defined by a mouse-click drawn rectangular AOI 


The updated link was on Howard?s github page is: http://usgs-lidar-public.s3.amazonaws.com/USGS_LPC_NM_NorthCentral_B3_2017_LAS_2018/ept.json 
& on the Entwine website https://usgs.entwine.io/ (zoom into desired spot)

Multiple footprints can be located on https://usgs.entwine.io/

Foorprints within the White Peak AOI: 
USGS_LPC_NM_NorthCentral_B3_2017_LAS_2018
NM_Northeast_B3_2018
NM_Northeast_B4_2018

Two ways of selecting ground points: 
{"type":"filters.returns","groups":"last"},
{"type":"filters.range","limits":"Classification[2:2]"}


on anaconda once pipeline is established:
Open Anaconda, launch command prompt and myenv. 

conda activate myenv
pdal --drivers
pdal pipeline V:\Field\B_Gonzalez\scripts\json_scripts\template_lidar_datagrab.json

useful tutorials / docs:
https://pdal.io/tutorial/iowa-entwine.html 
https://pdal.io/stages/filters.range.html 
https://nmfwri.org/uncategorized/intro-to-lidar-in-arcpro/

To grab rectangle for AOI go bbbox finder -- change to same projection USGS uses: EPSG:3857 - WGS 84 / Pseudo-Mercator. just be aware it uses the more standard bounding box format of [minx,miny,maxx,maxy] - so you'll have to rearrange into the PDAL format of ([minx,maxx],[miny,maxy])

http://bboxfinder.com/#36.098609,-105.295944,36.389780,-104.594192
-11721490.8769,4314198.3638,-11643372.2340,4354387.8415


So this workflow would skip LAS, bring DEM (.5m) into pro, then create a hillshade (so one step in pro) 

things to think about  
1. can I download multiple DEMs?
2. can i auto generate multiple hillshades? 
3. how do the usgs bulk download website compare? 
4. 



edge detection:
https://pro.arcgis.com/en/pro-app/latest/help/analysis/raster-functions/convolution-function.htm
https://developers.arcgis.com/python/guide/edge-detection-with-arcgis-learn/
https://community.esri.com/t5/imagery-and-remote-sensing-questions/how-to-carry-out-edge-detection-on-dem/td-p/188094





