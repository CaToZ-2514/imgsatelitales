## Instrucciones

### 1. Ingresar al sitio

Abre el navegador y ve a la página oficial:
[https://browser.dataspace.copernicus.eu/](https://browser.dataspace.copernicus.eu/)

Es recomendable registrarse antes de comenzar la descarga. La cuenta es gratuita y permite acceder a todas las funcionalidades y productos satelitales.

---

### 2. Buscar la zona de interés

Usa el cuadro de búsqueda ubicado en la parte superior izquierda para escribir el nombre del lugar (por ejemplo: *La Paz, Cesar, Colombia*).
Ajusta el mapa hasta que el área quede centrada y visible.

---

### 3. Filtrar las imágenes disponibles

En el panel izquierdo:

1. En **Dataset**, selecciona **Sentinel-2 L2A (Surface Reflectance)**.
2. En **Cloud coverage**, elige un valor menor al 20 % para evitar nubes.
3. Define un rango de fechas reciente.
4. Presiona **Search** para mostrar las escenas disponibles.

---

### 4. Seleccionar una imagen

Haz clic en una de las escenas que aparecen sobre el mapa.
Revisa la vista previa y el porcentaje de nubes. Si la imagen está despejada, presiona **Download** en la esquina superior derecha.

---

### 5. Configurar la descarga

En la ventana que aparece:

1. Elige la pestaña **Analytical**.
2. Configura las opciones:

   * **Image format:** TIFF (8-bit)
   * **Image resolution:** MEDIUM
   * **Coordinate system:** WGS 84 (EPSG:4326)
3. En **Layers → Raw**, marca:

   * B04 (banda roja)
   * B08 (banda infrarroja cercana, NIR)
4. En **Layers → Visualised**, marca:

   * True color (imagen en color natural)
5. Haz clic en **Download** para iniciar la descarga.

---

### 6. Organizar los archivos

1. Descomprime el archivo descargado.
2. Renombra los archivos y colócalos en la carpeta `data/` donde está el cuaderno de Jupyter:

   ```
   data/S2A_B04_10m.tif
   data/S2A_B08_10m.tif
   data/S2A_TRUE_COLOR.tif
   ```

---

### 7. Preparar el análisis

Con estas tres imágenes podrás visualizar la escena en color natural y calcular el índice de vegetación NDVI en el cuaderno interactivo.

### 8. Tarea

Realiza la tarea de acuerdo a lo que se indica al final del cuaderno interactivo
