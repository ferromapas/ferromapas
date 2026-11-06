# Ferromapas

**Mapas Ferroviarios Electrónicos**: un mapa georreferenciado, de libre acceso, de la infraestructura ferroviaria argentina, construido en formato KML/KMZ para Google Earth y otras aplicaciones GIS.

Sitio web: <http://www.ferromapas.com.ar/> · Contacto: ferromapas@gmail.com

- **Versión:** 1.0.0 (publicada el 27 de junio de 2013)
- **Autores:** Pablo Anglat (Mendoza), Gino Nuñez (Buenos Aires) y Rodrigo Respini (Córdoba)
- **Licencia:** [CC BY-NC-ND 2.5 AR](http://creativecommons.org/licenses/by-nc-nd/2.5/ar/)

## Contenido

El mapa muestra las líneas ferroviarias sobre el relieve, con nombres de estaciones y kilómetros. Incluye las seis líneas troncales que parten de Buenos Aires (Mitre, Belgrano, San Martín, Sarmiento, Roca y Urquiza), sus ramales, otros ferrocarriles y trazados de Chile.

| Ferrocarril            | Archivos KML |
| ---------------------- | -----------: |
| Belgrano               |          127 |
| Roca                   |           97 |
| Mitre                  |           84 |
| San Martín             |           69 |
| Urquiza                |           66 |
| Sarmiento              |           47 |
| Otros ferrocarriles    |           14 |
| Ferrocarriles de Chile |            1 |
| **Total**              |      **505** |

## Descargas

| Formato                         | Archivo                                                                         | Estado    |
| ------------------------------- | ------------------------------------------------------------------------------- | --------- |
| Google Earth (KMZ)              | [`releases/ferromapas_v01.0.0.kmz`](releases/ferromapas_v01.0.0.kmz)            | Vigente   |
| Garmin MapSource (MSI, Windows) | Disponible en la [página de descargas](http://www.ferromapas.com.ar/descargas/) | Deprecado |

La versión para GPS Garmin está deprecada: solo existe la 1.0.0 y no recibirá actualizaciones.

## Estructura del repositorio

```
.
├── releases/
│   └── ferromapas_v01.0.0.kmz      # Mapa compilado, listo para abrir
└── src/
    ├── _document.yaml              # Documento raíz
    └── ferromapas/
        ├── _folder.yaml            # Nombre y descripción general del mapa
        ├── ferrocarriles-argentinos/
        │   ├── ferrocarril-belgrano/
        │   │   ├── _folder.yaml
        │   │   ├── linea-a/
        │   │   ├── linea-c/
        │   │   └── ...
        │   ├── ferrocarril-mitre/
        │   ├── ferrocarril-roca/
        │   ├── ferrocarril-san-martin/
        │   ├── ferrocarril-sarmiento/
        │   ├── ferrocarril-urquiza/
        │   └── otros-ferrocarriles/
        └── ferrocarriles-de-chile/
```

- Cada ramal es un archivo `.kml` con sus placemarks (estaciones como polígonos o puntos, vías como líneas).
- Cada carpeta tiene un `_folder.yaml` con su nombre y el orden de sus elementos (`children`).
- `src/_document.yaml` define el punto de entrada del árbol.

El código fuente está dividido en archivos pequeños para facilitar su edición y el control de versiones. La carpeta `src` se construye con [ferromapas-toolkit](https://github.com/ferromapas/ferromapas-toolkit). El `.kmz` de `releases/` contiene un único `doc.kml` con todo el mapa.

## Cómo colaborar

1. Editá o agregá el archivo `.kml` del ramal en la carpeta del ferrocarril que corresponda.
2. Si agregás un archivo o carpeta, incluilo en la lista `children` del `_folder.yaml` de su carpeta padre.
3. Citá la fuente utilizada en el campo `description` del ramal.

## Licencia

Los mapas están licenciados bajo [Creative Commons Atribución-NoComercial-SinDerivadas 2.5 Argentina](http://creativecommons.org/licenses/by-nc-nd/2.5/ar/) (CC BY-NC-ND 2.5 AR). Deben respetarse los créditos de los autores. Más información en la [página de licencia](http://www.ferromapas.com.ar/licencia-de-ferromapas/).

## Créditos, Fuentes y Agradecimientos

Para el detalle completo de colaboraciones, consultá la [página de créditos](http://www.ferromapas.com.ar/creditos-de-ferromapas/).
