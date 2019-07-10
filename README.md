# TileServerGolang

Created a raster mbtiles server. I will probably be adding vector tiles support also in the future. The tileserver was built with golang. Currently the project is built for ubuntu but will added different version and source code in the future. I built this server mostly to serve imagery in jpg format but it will also work with png files that are better for maps with lines and text.

The server can be https or http, for https the server needs a cert.pem and key.pem to create this you will need to do the following comand:

```
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout key.pem -out cert.pem
```
when creatng the certs the "Name (e.g. server FQDN or YOUR name)" you need to enter your server ip e.g. coolmaps.com, or 127.0.0.1:2000 

## Insturctions to use tile server

Use:
```
./main -h
````
```
Nate
Usage of /tmp/go-build029234972/b001/exe/main:
  -credits string
        Built by Nate T (default "Nate")
  -dir string
        Pick dir to serve static files (default "static")
  -https
        true/false for server to be https, need cert.pem and key.pem in root directory (default true)
  -image_type string
        Pick the type of image jpg or png (default "jpg")
  -mbtiles string
        Path to sqlite mbtiles dataset (default "./control-room.mbtiles")
  -port int
        Pick port to listen on (default 2000)
```

Example:
```
./main -dir=static https=false -image_type=jpg -mbtiles=control-room.mbtiles -port=2000
```
```
Nate
Using https
./control-room.mbtiles
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
