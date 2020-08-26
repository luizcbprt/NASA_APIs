# 🤖 [NASA Space Apps CR 2020](https://nasaspaceappscr.globalhackathons.co/) 🛰️ 
### Intro a los APIs de la NASA: Crear una Web con Imágenes Satelitales & Datos de Observación de la Tierra
###### Organizado por Global Hackathons con apoyo de Comisión Aeroespacial CFIA
###### ||Fuente de Datos: [NASA GIBS API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers) ||
###### ||Competencia Mundial 🌎 || Desafíos Globales 2020: Observar, Informar, Un Futuro Sostenible, Confrontar, Crear o Crea tu propio reto! ||

#### En este Taller aprenderemos sobre el uso de APIs de la NASA para visualizar datos como: Imágenes Satelitales y de Observación de la Tierra, entre muchos otros más! 

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


Este proyecto muestra cómo utilizar GIBS API para visualizas capas de datos de imágenes satelitales a bordo del 🛰️ Sátelite Terra & Aqua, para su uso en análisis y comprensión del Clima, Terrenos, Agricultura, Océanos, entre muchos otros, mediante los datos generados por el instrumento MODIS que rastrea una gama amplia de signos vitales de la tierra 🌎

Este proyecto muestra cómo utilizar GIBS como fuente del mosaico  (en inglés tile source) de Imágenes Satelitales en OpenLayers. 
Usamos los servicios de Exploración de Imágenes Globales de la NASA [API de GIBS(https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers) como proveedor de una pirámide de mosaicos de imágenes satélitales (de la especificación OGC WMTS 1.0.0) y visualizar las capas de datos del ***Servicio de mosaicos de mapas web (WMTS)*** en base a parametros como:

- URL: https://gibs.earthdata.nasa.gov/wmts/
- Layer: (e.g. "MODIS / Terra")
- Matrix Set:'EPSG_(n)m'
- Origin:[Lat, Long]
- Resolution:[0...2]
- Tile: Open Layers

> Crear función Layer (Capa de Datos):

```
 function createLayer() {
    var source = new ol.source.WMTS({
      url: 'https://gibs.earthdata.nasa.gov/wmts/epsg4326/best/wmts.cgi?SERVICE='
      layer: 'MODIS_Terra_SurfaceReflectance_Bands121',
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

Términos Clave:

***MODIS (or Moderate Resolution Imaging Spectroradiometer)***: es un instrumento clave a bordo de los satélites Terra (originalmente conocido como EOS AM-1) y Aqua (originalmente conocido como EOS PM-1). 

***Imagery API Service*** 

> What's next? El Reto!
Con acceso a estos datos, crear una Aplicación o un modelo de impacto mundial!

+Recursos:

https://terra.nasa.gov/about/terra-instruments/modis

https://modis.gsfc.nasa.gov/data/

https://openlayers.org/

https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+Available+Imagery+Products#expand-CorrectedReflectance17Products

https://earthdata.nasa.gov/earth-observation-data/near-real-time/download-nrt-data/modis-nrt

https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers#GIBSAPIforDevelopers-ImageryAPI/Services


Terms of Use:
This workshop hosted by Space Apps CR relies on a publicly accessible service web map service from NASA GIBS and is subject to its availability. GIBS is asking end users of this imagery to include the following acknowledgment in written and oral presentations:

We acknowledge the use of imagery from the Land Atmosphere Near real-time Capability for EOS (LANCE) system and services from the Global Imagery Browse Services (GIBS), both operated by the NASA/GSFC/Earth Science Data and Information System (ESDIS, https://earthdata.nasa.gov) with funding provided by NASA/HQ.
