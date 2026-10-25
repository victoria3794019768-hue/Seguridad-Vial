# Dashboard de siniestros viales — Corrientes (2018–2025)

Dashboard estático e interactivo preparado para Vercel. No requiere instalar paquetes ni compilar: `index.html` carga los registros de `data.json`.

## Publicarlo en Vercel (método más simple)

1. Entrá a https://vercel.com/drop e iniciá sesión.
2. Arrastrá el archivo `dashboard_siniestros_vercel.zip` a la página (o elegí el archivo con el selector).
3. Seleccioná tu equipo/cuenta, poné un nombre al proyecto y hacé clic en **Deploy**.
4. Cuando termine, abrí la URL publicada. La página necesita conexión a internet para cargar el mapa de OpenStreetMap, Leaflet y Chart.js desde sus CDNs.

También podés descomprimir el ZIP y desplegar la carpeta mediante Vercel CLI o importándola desde un repositorio Git. Si te pide configuración de framework, elegí un sitio estático/Other; no hace falta un comando de build.

## Archivos

- `index.html`: visualizaciones, filtros cruzados, mapa, tabla y metodología.
- `data.json`: versión preparada de los 3.781 registros de la hoja `Base_Limpia`.
- `vercel.json`: configuración mínima de sitio estático.
- `audit.json`: resumen de validación realizado sobre el archivo entregado.

## Validaciones sobre esta versión

- 3.781 registros; los 3.781 identificadores son únicos.
- Datos entre 2018 y 2025; 3 registros no tienen año informado.
- 2.294 coordenadas interpretadas como válidas dentro del encuadre aproximado de Corrientes.
- 1.478 registros no tienen coordenadas; otros 9 tienen coordenadas fuera del encuadre o valores centinela. En total, 1.487 registros no se muestran en el mapa.
- Los campos de semáforo vacíos (394) y `S/D` (198) se muestran como `Sin dato`, sumando 592.
- `12` y variantes directas de Ruta Nacional 12 se muestran como `Ruta Nacional 12`.

## Límites metodológicos

Este archivo contiene el estado del semáforo asociado a cada siniestro, pero no el padrón de ubicaciones y cantidades de semáforos. La tasa de siniestros por semáforo y la comparación de tasas entre cruces señalizados y no señalizados quedan pendientes hasta incorporar y vincular ese segundo dataset. El ranking por vía usa `heridos + 10 × fallecidos` y no está normalizado por longitud de calle ni volumen de tránsito.
