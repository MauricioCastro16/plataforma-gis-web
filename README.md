[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/MauricioCastro16/plataforma-gis-web)

# Plataforma Gis Web

![React](https://img.shields.io/badge/react-19.2.0-blue)

Aplicación web de Sistema de Información Geográfica (SIG) para visualizar, consultar y editar más de 50 capas temáticas de Argentina. Integrada con GeoServer y PostGIS mediante servicios OGC, con herramientas de dibujo, medición y exportación.

## Características Principales
- Visualización interactiva de capas WMS con control de opacidad y orden.
- Consulta espacial por punto y rectángulo con cálculo de distancias geodésicas.
- Dibujo de geometrías (punto, línea, polígono) y guardado vía WFS-T.
- Medición de distancias y áreas en el mapa.
- Exportación del mapa actual a PDF mediante html2canvas y jsPDF.

## Stack Tecnológico
| Área                | Tecnologías                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| Frontend            | React, OpenLayers, html2canvas, jsPDF                                       |
| Backend             | GeoServer (WMS, WFS, REST API)                                              |
| Base de Datos       | PostGIS (PostgreSQL)                                                         |
| Herramientas        | Docker, Docker Compose, Node.js, npm, Python (script de importación)        |

## Arquitectura / Flujo
El sistema adopta una arquitectura de tres capas: el frontend en React consume servicios OGC (WMS/WFS/REST) expuestos por GeoServer, el cual accede a datos espaciales almacenados en PostGIS. En desarrollo, react-scripts proxyea las peticiones a GeoServer; en producción, el navegador se conecta directamente.

## Instalación y Uso
```bash
# Clonar el repositorio
git clone <URL_DEL_REPOSITORIO>
cd <NOMBRE_DEL_DIRECTORIO>

# Instalar dependencias de Node.js
npm install

# Levantar servicios Docker (PostGIS y GeoServer)
docker-compose -f docker/docker-compose.yml up -d

# Ejecutar la aplicación en modo desarrollo
npm start
```

La aplicación estará disponible en http://localhost:3000. Asegúrate de que los contenedores Docker estén corriendo para cargar las capas.
