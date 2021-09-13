# ANACONDA + PYTHON, CREACIÓN DE UN ENTORNO Y ACTUALIZACIÓN DE PAQUETES

## Guía de Instalación de Anaconda y Python

## Por qué Python para Data Science

Si ya conoces el lenguaje Python no hace falta que te cuente porque es el elegido en la industria para dar vida a los proyectos de Data Science. Pero si no estás familiarizado con Python estas son algunas de sus características:

- Es poderoso y sencillo
- Tiene múltiples paquetes estadísticos y de aprendizaje automático, listos para usar
- Una comunidad muy activa a la que siempre puedes consultar

Y cuenta con muchas más, pero te invito a descubrirlas junto a mi mientras exploramos el mundo del Álgebra Lineal con Python.

## Por qué Anaconda

Anaconda nos provee de una plataforma muy completa para poder desarrollar nuestros proyectos de Data Science, simplifica la tarea de instalación y configuración de las distintas aplicaciones que necesitaremos usar en nuestro viaje. Podemos utilizarlo tanto por terminal como por interfaz gráfica (GUI). Por el momento avancemos con la segunda opción, es más amigable para quien no está acostumbrado a la línea de comandos.

Algunas ventajas de utilizar Anaconda para tus proyectos son:

- Manejar los entornos de trabajo con Conda (todas las dependencias de librerías se resuelven en el momento de instalación)
- Posibilidad de compartir, colaborar y reproducir los proyectos
- Puedes pasar tu proyecto a producción solo con un click (una vez configurado)

Dentro de las variadas aplicaciones que nos ofrece Anaconda vamos a utilizar Jupyter Notebooks con Python 3.7.

### Instalación
Para realizar la instalación debes seguir los siguientes pasos:

1. Ir a  https://www.anaconda.com/distribution/
2. Selecciona tu versión de Sistema Operativo: Windows - macOS - Linux
3. Haz click en Descargar/Download “Python 3.7 version” (o click en la versión adecuada para tu CPU 64-bit o 32-bit)

[](./imagenes/img1.png)

Después de descargar el instalador gráfico, debes abrirlo y seguir las instrucciones que se presentarán en pantalla. Estas son una serie de preguntas para realizar la instalación, las opciones por defecto están bien, no hay necesidad de cambiarlas.

### Iniciando Anaconda

Una vez que finalizada la instalación debes abrir el programa Anaconda Navigator para que podamos crear el entorno en cual estaremos estudiando y actualizar los paquetes.

Haz click en Environments y despues click en +Create. Se abrirá una ventana para crear un nuevo entorno.

[](./imagenes/img2.png)

Llena los siguientes campos:

[](./imagenes/img3.png)

- Name: Platzi - FundamentosAL
- Packages: tilde en Python y del menú desplegable selecciona 3.7

[](./imagenes/img4.png)

momento para configurar el nuevo entorno y actualizarlo. Cuando termine verás una pantalla similar a esta

[](./imagenes/img5.png)

Los paquetes que ves son los que están instalados por defecto, necesitas instalar varios más. Haz click en installed y cambiarlo a not installed.

[](./imagenes/img6.png)

En el recuadro de search packages pon:

- Jupyter Notebook
- scipy (tambien instalará numpy)
- pillow (libreria para manejo de imágenes)
- imageio (lectura / escritura de imágenes)
- matplotlib (para graficar)
- seaborn (visualizaciones estadísticas)
- scikit-learn (aprendizaje automático - lo usaremos para un ejemplo de PCA)

En cada uno de los casos haz click en el recuadro y marcarlo para instalar. Una vez que los tengas seleccionados haz click en Apply. Anaconda procesa por ti todas las dependencias y abrirá una nueva ventana para que aceptemos los paquetes a instalar, haz click en Apply.

Una vez finalizada la instalacion y actualizacion de paquetes en el entorno Platzi - FundamentosAL hacemos click en Home, y Launch Jupyter Notebook. Una nueva pestaña se abrirá en nuestro navegador con Jupyter, ya estamos listos para comenzar el aprendizaje de Fundamentos de Álgebra Lineal con Python.

### Ejercicio

Instala el paquete seaborn. Es un paquete para visualizar datos.

A mi tambien me paso la primera vez no saber por dónde comenzar, así que si necesitas ayuda aqui te dejo un paso a paso.

1. Desde Anaconda Navigator, haz click en Environments
2. Selecciona el entorno donde quieres instalar el paquete (Platzi - FundamentosAL)
3. Selecciona en el menú desplegable Not Installed
4. Escribe en el recuadro de búsqueda seaborn
5. Haz click en el paquete seaborn
6. Haz click en Apply
7. Haz click en Apply, pero esta vez en el pop up que aparece para aceptar todas las dependencias.

Listo! Felicitaciones, instalaste tu primer libreria para visualización de datos en Python.

Puedes copiar y pegar en una de las celdas en Jupyter el siguiente código para ver un gráfico de la cantidad de pasajeros en avión entre 1949 y 1960 por mes.

```
import seaborn as sns
vuelos = sns.load_dataset("flights")
vuelos = vuelos.pivot("month", "year", "passengers")
ax = sns.heatmap(vuelos)
```