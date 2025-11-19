# Análisis de imágenes satelitales

## Autor(es)

[Camilo Torres, Angelly Ríos, Juan Borjas]


## Descripción del Repositorio

### Procesamiento de NDVI y Análisis Multitemporal (T1–T2)

Este proyecto calcula el **NDVI** para dos fechas distintas (T1 y T2) utilizando imágenes Sentinel-2.  
Luego genera un mapa de **cambio NDVI (T2 – T1)** para estudiar variaciones de vegetación en el área de análisis.

Este repositorio contiene el desarrollo completo de un análisis de vegetación que cambia en el tiempo usando imágenes Sentinel-2.  
El objetivo principal es calcular el índice **NDVI** para dos fechas distintas (T1 y T2), comparar ambas y generar un mapa de **cambio NDVI (T2 - T1)** para identificar aumentos o pérdidas de vegetación en el área de estudio.

El flujo implementado incluye:
- Lectura y alineación de bandas espectrales (B4 y B8)
- Cálculo de NDVI por fecha
- Aplicación opcional de máscara de nubes
- Visualización de mapas e histogramas
- Generación de GeoTIFF con NDVI y cambio NDVI

---

## Configuración del entorno y requisitos

Para empezar a trabajar se recomienda la elaboración de un entrono que mantendra aislado y a salvo las dema´s dependencias de los programas de nuestro computador y evitará fluctuaciones con los mismos, para esto, primero:

1. Instalar **Miniconda** o **Anaconda**
Luego abre **Anaconda Prompt**.
2. Crear el entorno conda y activar el entorno usando el comando:

     __conda create -n satimg python=3.10 -y__

    __conda activate satimg__
3. Entrar al directorio del proyecto e instalar el resto de dependencias con:

    __pip install -r requirements.txt__
4. Verificar la instalación: 

    __python -c "import rasterio, geopandas, numpy, matplotlib; print('Todo ok')"__
5. Usar el entorno en VSC como interfaz para programción.

Se recomienda una organización local semejante a:
```
data/
    t1/
        dataS2A_B04_10m.tiff
        dataS2A_B08_10m.tiff
        dataS2A_TRUE_COLOR.tiff
    t2/
        dataS2A_B04_2_10m.tiff
        dataS2A_B08_2_10m.tiff
        dataS2A_TRUE_COLOR_2.tiff

outputs/
    (Aquí se guardarán los NDVI y el cambio NDVI en GeoTIFF, practicamente todo lo que genere esta práctica)
```

---

## Estructura de la tarea

```
├── data/
│   ├── t1/                  
│   ├── t2/      
│
├── outputs/  
│
├── notebook.ipynb           
└── README.md                # Este archivo

```
Este es el esqueleto principal de la actividad, donde se manejan o guardan las imagenes a usar y donde sale el .tif de output. Lo más dificil es organizar las imagenes al conseguirlas.
---

## Uso

1. **Colocar las bandas** en las carpetas `data/t1/` y `data/t2/`.

2. **Abrir el notebook** (`notebook.ipynb`).

3. **Configurar las rutas** en las primeras celdas:

   ```python
   PATH_B4_T1 = "data/t1/dataS2A_B04_10m.tiff"
   PATH_B8_T1 = "data/t1/dataS2A_B08_10m.tiff"

   PATH_B4_T2 = "data/t2/dataS2A_B04_2_10m.tiff"
   PATH_B8_T2 = "data/t2/dataS2A_B08_2_10m.tiff"

4. Ejecutar el notebook celda por celda.

5. Los resultados se guardan automáticamente en outputs/.
---

## Uso de Inteligencia Artificial

[Describe el nivel y tipo de uso de IA/LLMs en el desarrollo de este trabajo. Por ejemplo:
- ¿Se utilizó ChatGPT, Copilot u otras herramientas de IA para asistencia en el código?
Herramienta empleada: ChatGPT (asistencia conversacional y técnica).
- ¿Qué porcentaje aproximado del código fue asistido por IA?
25% del código y 5% del documento README
- ¿En qué aspectos específicos se utilizó IA (depuración, generación de código, documentación, etc.)?
--- Sugerencias para manejo de GeoTIFF y resampling---Explicaciones de conceptos y estructura de NDVI
- ¿Se utilizó IA para la generación de ideas o arquitectura de modelos?
- Cualquier otra información relevante sobre el uso de IA.]

---

## Resultados

Empezando por el principio se logró realizar un reconocimiento de la pagina de Copernicus para la adquisición de imagenes satelitales para su análisis y sus distintas bandas, y como distintas combinaciones de estas son muy importantes para el monitoreo de la ecología de las zonas de interés. Bajo el código que tenemos no es muy dificil de trabajar, todo se ajusta casi que solo.