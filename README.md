# 🤖 [NASA Space Apps CR 2020](https://nasaspaceappscr.globalhackathons.co/) 🛰️ 
### Intro a los APIs de la NASA: Creando un Web App con Imágenes Satelitales & Datos de Observación de la Tierra
###### Organizado por Global Hackathons con apoyo de Comisión Aeroespacial CFIA
###### ||Fuente de Datos: [NASA GIBS API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers) ||
###### ||Región: América Latina 🌎 ||Desafíos Globales 2020 ||

#### En este Taller aprenderemos sobre el uso de APIs de la NASA para obtener Imágenes Satelitales & Datos de Observación de la Tierras!

![Test Image 4](https://i.ibb.co/x7WMPDn/Screen-Shot-2020-07-31-at-04-04-22.png)

#### Manos a la obra!

> Paso 1: Crear una cuenta en NASA Open APIs: https://api.nasa.gov/

> Paso 2: Genera los credenciales de tu API Key:

```
 https://api.nasa.gov/planetary/apod?api_key=YOUR_API_KEY
```

> Paso 3: Bienvenid@ al servicio de Imágenes Satelitales:
https://earthdata.nasa.gov/eosdis/science-system-description/eosdis-components/gibs

> Paso 4: Integrar el GIBS API:

We use the ***NASA's Global Imagery Browse Services (GIBS) APIs*** as a Data Provider for the satellite imagery and visualize the Data Layers using  ***Web Map Title Service (WMTS)*** such as:

- URL: https://gibs.earthdata.nasa.gov/wmts/
- Layer: (e.g. "MODIS / Terra")
- Matrix Set:'EPSG_(n)m'
- Origin:[Lat, Long]
- Resolution:[0...2]
- Tile: Open Layers

> Create Layer function:

```
 function createLayer() {
    var source = new ol.source.WMTS({
      url: 'https://gibs.earthdata.nasa.gov/wmts/epsg4326/best/wmts.cgi?SERVICE='
      layer: 'MODIS_Terra_Property1_Property(n)',
      format: 'image/jpeg',
      matrixSet: 'EPSG_(N)m',
      tileGrid: new ol.tilegrid.WMTS({
        origin: [Lat, Long],
        resolutions: [
          0...(n)
        ],
        matrixIds: [0, 1, 2, 3, 4, 5, 6, 7, 8],
        tileSize: 512
      })
    });
```



> What's next? Computer Vision 
Users can send their pictures from climate events to help on the prediction model! 


![Test Image 4](https://i.ibb.co/WPMWB8r/C4C.png)
