# Proyecto: Uso de Roboflow y Herramientas de Visión por Computador
Este repositorio contiene código que utiliza Roboflow, Pillow, OpenCV y Matplotlib para cargar, procesar y visualizar imágenes. También incluye instrucciones para ejecutarlo en Google Colab. En el repositorio se encuentran los archivos: Proyecto_4.ipynb, Procesamiento_de_Imágenes_para_Sistemas_de_Energía_Eléctrica.pdf y Procesamiento-de-Imagenes-para-Sistemas-de-Energia-Electrica.pptx. Para ejecutar el código correctamente, se debe importar la imagen en la celda 3 del notebook Proyecto_4.ipynb.

## Requisitos
- Python 3.8 o superior
- Conexión a internet para instalación y uso de Roboflow

## Instalación de Librerías
Ejecuta en tu terminal o en Google Colab:
pip install roboflow pillow opencv-python matplotlib

## Importación de Librerías
from roboflow import Roboflow  
from PIL import Image  
from google.colab import files  
import cv2  
import matplotlib.pyplot as plt

## Ejemplo: Cargar y Mostrar una Imagen
ruta = "imagen.jpg"

# Mostrar con PIL
img_pil = Image.open(ruta)
plt.imshow(img_pil)
plt.axis('off')
plt.show()

# Mostrar con OpenCV (BGR a RGB)
img_cv = cv2.imread(ruta)
img_rgb = cv2.cvtColor(img_cv, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb)
plt.axis('off')
plt.show()

## Uso Básico con Roboflow
rf = Roboflow(api_key="TU_API_KEY")
project = rf.workspace("NOMBRE_WORKSPACE").project("NOMBRE_PROYECTO")
model = project.version(1).model

resultado = model.predict("imagen.jpg").json()
print(resultado)

## Subir Archivos en Google Colab
uploaded = files.upload()

## Archivos incluidos en el repositorio
- Proyecto_4.ipynb  
- Procesamiento_de_Imágenes_para_Sistemas_de_Energía_Eléctrica.pdf  
- Procesamiento-de-Imagenes-para-Sistemas-de-Energia-Electrica.pptx

## Estructura Sugerida del Proyecto
/
├─ README.md  
├─ requirements.txt  
├─ Proyecto_4.ipynb  
├─ Procesamiento_de_Imágenes_para_Sistemas_de_Energía_Eléctrica.pdf  
└─ Procesamiento-de-Imagenes-para-Sistemas-de-Energia-Electrica.pptx

## requirements.txt
roboflow  
pillow  
opencv-python  
matplotlib
