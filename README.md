# 🤖 [NASA Space Apps 2020](https://nasaspaceappscr.globalhackathons.co/) 🛰️ 
### Intro a los APIs de la NASA: Datos de Observación de la Tierra, Imágenes Satelitales, Clima, Misión Rover en Marte.
###### Organizado por Global Hackathons con apoyo de Comisión Aeroespacial y Local Leads de Space Apps en México, Costa Rica.
###### ||Fuente de Datos: [NASA API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers), [GIBS API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers). ||

###### ||Competencia Mundial 🌎 || Desafíos Globales 2020: Observar, Informar, Un Futuro Sostenible, Confrontar, Crear o Crea tu propio reto! ||

#### En este Taller aprenderemos sobre el uso de APIs de la NASA para visualizar datos como: Imágenes Satelitales y de Observación de la Tierra, entre muchos otros más! 

![Test Image 4](https://github.com/leoaiassistant/NASA_GIBS/blob/master/IMG/model.png)

#### Manos a la obra!

> Paso 1: Crear una cuenta en NASA Open APIs: https://api.nasa.gov/

> Paso 2: Genera los credenciales de tu API Key:

```
 https://api.nasa.gov/planetary/apod?api_key=YOUR_API_KEY
```
Prueba el API de Observación de la Tierra:
```
https://api.nasa.gov/planetary/earth/assets?lon=-98.83&lat=19.70&date=2020-01-01&&dim=0.10&api_key=DEMO_KEY
```

Prueba el API de Misión Rover en Marte:
```
https://api.nasa.gov/mars-photos/api/v1/rovers/curiosity/photos?earth_date=2020-1-1&api_key=DEMO_KEY
```

> Paso 3: [Bienvenid@](sM9dReXlARhfcp9ctZGxUt8wItACbqJTLMCW3YiI) al servicio de Imágenes Satelitales: Este API se utiliza para construir modelos y aplicar Machine Learning en Imágenes Satelitales: https://earthdata.nasa.gov/eosdis/science-system-description/eosdis-components/gibs


> Paso 4: Integrar el GIBS API:
Este proyecto muestra cómo utilizar GIBS API para visualizar capas de datos de imágenes satelitales a bordo del 🛰️ Sátelite Terra & Aqua, para su uso en análisis y comprensión del Clima, Terrenos, Agricultura, Océanos, entre muchos otros, mediante los datos generados por el instrumento MODIS que rastrea una gama amplia de signos vitales de la tierra 🌎

Este proyecto muestra cómo utilizar GIBS como fuente del mosaico  (en inglés tile source) de Imágenes Satelitales en OpenLayers. 
Usamos los servicios de Exploración de Imágenes Globales de la NASA [API de GIBS](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers) como proveedor de una pirámide de mosaicos de imágenes satélitales (de la especificación OGC WMTS 1.0.0) y visualizar las capas de datos del ***Servicio de mosaicos de mapas web (WMTS)*** en base a parametros como:

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


> What's next? El Reto!
Con acceso a estos datos, crea una Aplicación o un modelo de impacto mundial!

+Tutoriales:
- Intro to Web Development & NASA API: Mars Rover Photos!
- Creado por Brandon Escamilla, Space Apps Lead en México

[![Brandon Escamilla](https://img.youtube.com/vi/KcyGr_onNiM/1.jpg)](https://youtu.be/KcyGr_onNiM)

+Recursos:

[Satelite Terra](https://terra.nasa.gov/about/terra-instruments/modis)

[MODIS](https://modis.gsfc.nasa.gov/data/)
 
[Open Layers](https://openlayers.org/)

[Earth Data Layers](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+Available+Imagery+Products#expand-CorrectedReflectance17Products)
 
[Earth Observation](https://earthdata.nasa.gov/earth-observation-data/near-real-time/download-nrt-data/modis-nrt
)
[GIBS API](https://wiki.earthdata.nasa.gov/display/GIBS/GIBS+API+for+Developers#GIBSAPIforDevelopers-ImageryAPI/Services)


### Terms of Use:
This workshop hosted by Space Apps Local Lead relies on a publicly accessible service web map service from NASA GIBS and is subject to its availability. GIBS is asking end users of this imagery to include the following acknowledgment in written and oral presentations:

We acknowledge the use of imagery from the Land Atmosphere Near real-time Capability for EOS (LANCE) system and services from the Global Imagery Browse Services (GIBS), both operated by the NASA/GSFC/Earth Science Data and Information System (ESDIS, https://earthdata.nasa.gov) with funding provided by NASA/HQ.
