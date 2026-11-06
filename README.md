# Ferromapas

**Mapas Ferroviarios Electrónicos**: un mapa georreferenciado, de libre acceso, de la infraestructura ferroviaria argentina, construido en formato KML/KMZ para Google Earth y otras aplicaciones GIS.

Sitio web: <http://www.ferromapas.com.ar/> · Contacto: ferromapas@gmail.com

- **Versión:** 1.1.0 (publicada el 6 de noviembre de 2026)
- **Autores:** Pablo Anglat (Mendoza), Gino Nuñez (Buenos Aires) y Rodrigo Respini (Córdoba)
- **Licencia:** [CC BY-NC-ND 2.5 AR](http://creativecommons.org/licenses/by-nc-nd/2.5/ar/)

## Contenido

El mapa muestra las líneas ferroviarias sobre el relieve, con nombres de estaciones y kilómetros. Incluye las seis líneas troncales que parten de Buenos Aires (Mitre, Belgrano, San Martín, Sarmiento, Roca y Urquiza), sus ramales, otros ferrocarriles y trazados de Chile.

| Ferrocarril            | Archivos KML |
| ---------------------- | -----------: |
| Belgrano               |          127 |
| Roca                   |           97 |
| Mitre                  |           84 |
| San Martín             |           73 |
| Urquiza                |           66 |
| Sarmiento              |           48 |
| Metrotranvía de Mendoza |            2 |
| Otros ferrocarriles    |           14 |
| Proyectos              |            1 |
| Ferrocarriles de Chile |            1 |
| **Total**              |      **513** |

## Novedades de la versión 1.1.0

Publicada el 6 de noviembre de 2026. El detalle completo está en [`changelog/1.1.0.yaml`](changelog/1.1.0.yaml).

- **Metrotranvía de Mendoza:** nueva sección con las líneas Gutiérrez - Mendoza - Aeropuerto y Pellegrini - Benegas - Luján de Cuyo, con todos sus paradores. Reemplaza al antiguo Metrotranvía Urbano Mendoza.
- **Ferrocarril San Martín:** se completa el Div 41 (Fray Luis Beltrán - Tropero Sosa) con sus paradas y los desvíos a las bodegas Santa Ana y Tomba. Se ajusta la ubicación de la estación Gustavo André.
- **Ferrocarril Belgrano:** en el ramal A12 (Guaymallén - Las Cuevas) se dibuja la traza que quedó bajo el dique Potrerillos y se corrigen algunas ubicaciones. También se reordena el ramal A13.
- **Reubicación de vías del Ferrocarril Trasandino (proyecto):** traza proyectada en Potrerillos por la construcción del dique, que nunca se llevó a cabo, con puentes, túneles, estaciones y kilometrajes.
- **Otros:** nuevo ramal La Plata - 19 de Noviembre (Sarmiento) y Divisadero Pinamar (Roca).
- **Ferrocarril Trasandino Central Chileno:** se agregan túneles, puentes y estaciones del tramo entre Los Andes y Río Blanco, y se ajusta la traza.

## Descargas

| Formato                         | Archivo                                                                         | Estado    |
| ------------------------------- | ------------------------------------------------------------------------------- | --------- |
| Google Earth (KMZ) 1.1.0        | [`releases/ferromapas_v01.1.0.kmz`](releases/ferromapas_v01.1.0.kmz)            | Vigente   |
| Google Earth (KMZ) 1.0.0        | [`releases/ferromapas_v01.0.0.kmz`](releases/ferromapas_v01.0.0.kmz)            | Anterior  |
| Garmin MapSource (MSI, Windows) | [`releases/ferromapas_v01.0.0.msi`](releases/ferromapas_v01.0.0.msi)            | Deprecado |

La versión para GPS Garmin está deprecada: solo existe la 1.0.0 y no recibirá actualizaciones. La 1.1.0 se distribuye únicamente como KMZ.

## Estructura del repositorio

```
.
├── releases/
│   ├── ferromapas_v01.1.0.kmz      # Mapa compilado, versión actual
│   ├── ferromapas_v01.0.0.kmz      # Versión anterior
│   └── ferromapas_v01.0.0.msi      # Instalador Garmin MapSource (deprecado)
├── changelog/                      # Historial de cambios por versión (YAML)
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
        │   ├── metrotranvia-de-mendoza/
        │   ├── otros-ferrocarriles/
        │   └── proyectos/
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
