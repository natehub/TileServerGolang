# TileServerGolang

Created a raster mbtiles server. I will probably be adding vector tiles support also in the future. The tileserver was built with golang. Currently the project is built for ubuntu but will added different version and source code in the future.



Use:
```
./main -h
````
```Nate
Usage of /tmp/go-build331047171/b001/exe/main:
  -credits string
        Built by Nate T (default "Nate")
  -dir string
        Pick dir to serve static files (default "static")
  -image_type string
        Pick the type of image jpg or png (default "jpg")
  -mbtiles string
        Path to sqlite mbtiles dataset (default "./control-room.mbtiles")
  -port int
        Pick port to listen on (default 2000)
```

Example:
```
./main -dir=static -image_type=jpg -mbtiles=control-room.mbtiles -port=2000
```
```
Nate
control-room.mbtiles
File exists.
*********************
Correct image type.
***************************
static
Folder exists.
*********************************
Serving on port 2000
Serving static files from static but in the browser its :2000/static
Serving map tiles from :2000/tiles/{z}/{x}/{y}.jpg
```

To view the simple leaflet map "localhost:2000/static/

*The sample mbtiles datasets was produced quickly in tilemill
