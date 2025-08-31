## Sistema de Clasificación de Enfermedades Avícolas con Redes Neuronales

Este repositorio contiene el código del trabajo de titulación para la
Maestría en Ciencia de Datos, que implementa un sistema de diagnóstico
de enfermedades avícolas basado en Deep Learning, enfocado en granjas de
Portoviejo, Ecuador.

## 📝 Descripción del Proyecto

El proyecto desarrolla un sistema de dos etapas para la detección y
clasificación de enfermedades avícolas (Coccidiosis, Newcastle y
Salmonella) a partir de imágenes de heces. El objetivo es proporcionar
una herramienta de alerta temprana de bajo costo y alta precisión para
los productores avícolas.

1. **Etapa 1 (Detección):** Se utiliza un modelo **YOLOv8n**
para detectar y localizar cada muestra fecal en una imagen, incluso en
fondos complejos y condiciones de iluminación variables. 
2. **Etapa 2 (Clasificación):** Cada muestra detectada es recortada y analizada por
una Red Neuronal Convolucional (CNN) optimizada, **MobileNetV2**,
que la clasifica en una de las cuatro categorías: Sana, Coccidiosis,
Newcastle o Salmonella.

## 📊 Resultados Clave

-   El detector de objetos **YOLOv8n** alcanzó un **mAP@0.5 de 95.6%**, demostrando una alta eficacia para localizar las muestras.
-   El clasificador **MobileNetV2** fue seleccionado como el modelo óptimo, logrando una **exactitud del 97.7%** con un tamaño de solo 8.7 MB, lo que lo hace ideal para su despliegue en dispositivos móviles.
-   El sistema integrado fue validado funcionalmente con imágenes de campo recolectadas en granjas de Portoviejo, demostrando su robustez en un entorno real.

## Estructura del Repositorio

-   `/notebooks`: Contiene los cuadernos de Jupyter para el entrenamiento y la ejecución del pipeline.
    -   `01_entrenamiento_detector_yolo.ipynb`: Entrenamiento del detector de objetos YOLOv8n.
    -   `02_entrenamiento_clasificadores_cnn.ipynb`: Entrenamiento y evaluación comparativa de cuatro arquitecturas CNN.
    -   `03_pipeline_diagnostico_integrado.ipynb`: Script final que integra el detector y el clasificador para el diagnóstico en imágenes locales.
-   `README.md`: Esta guía.
-   `requirements.txt`: Dependencias del proyecto.

## 🚀 Configuración y Uso

Sigue estos pasos para configurar el entorno y ejecutar el proyecto.

### 1. Clonar el Repositorio
En tu terminal, clona este repositorio en tu máquina local. Reemplaza `TU_USUARIO` con tu nombre de usuario de GitHub.

```bash
git clone https://github.com/TU_USUARIO/Clasificacion-Enfermedades-Avicolas-CNN.git
cd Clasificacion-Enfermedades-Avicolas-CNN
```

### 2. Crear un Entorno Virtual e Instalar Dependencias
```bash
python -m venv venv
source venv/bin/activate  # En Windows: venv\Scripts\activate
pip install -r requirements.txt```
```
### 3. Descargar Datasets y Modelos Entrenados

Debido a su gran tamaño, los datasets y los pesos de los modelos (.pt) no están en este repositorio. Descárgalos de los siguientes enlaces y colócalos en las rutas correspondientes especificadas dentro de cada notebook.

-    Dataset de Detección (YOLO): [https://universe.roboflow.com/datasets-uxi8b/do_an_tot_nghiep_phung_duy_manh]

-    Dataset de Clasificación (CNN): [https://zenodo.org/records/4628934]

-    Pesos del Modelo YOLOv8n entrenado: [https://drive.google.com/file/d/1l7eNRZMfwMiWoxffOyuHi-pCV09tjehZ/view?usp=sharing]

-   Pesos del Modelo MobileNetV2 entrenado: [https://drive.google.com/file/d/1kYqKX_S8Ppwv0P7KTSQebiUZMsPp8jIn/view?usp=sharing]

### 4. Ejecutar los Notebooks

Para replicar los resultados o utilizar el sistema:

Entrenamiento (Opcional):

-   Abre 01_entrenamiento_detector_yolo.ipynb para entrenar el modelo de detección.

-   Abre 02_entrenamiento_clasificadores_cnn.ipynb para entrenar los modelos de clasificación.

Diagnóstico (Uso final):

-   Abre 03_pipeline_diagnostico_integrado.ipynb.

Asegúrate de modificar las rutas de los modelos y de la carpeta de imágenes que deseas analizar, tal como se indica en las celdas de configuración del notebook.

Ejecuta las celdas para ver el diagnóstico en tus propias imágenes.

### Autor

Jordi Delgado Lucas

