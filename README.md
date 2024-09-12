# Practica_2

## Integrantes
- Uriel Vladimir Alvarez Tapia 20121191
- Miguel Angel Castañeda Garcia 20120015
- Diana Alejandra Mendoza Mendoza 20121226

## Introducción 
La robótica industrial es una disciplina clave en la automatización de procesos que requieren alta precisión y eficiencia. En este contexto, los robots manipuladores como el Epson C4 desempeñan un rol crucial en la industria moderna, gracias a su capacidad para realizar tareas repetitivas con exactitud y rapidez. Este robot en particular es utilizado en una amplia gama de aplicaciones que incluyen el ensamblaje, la manipulación de materiales y el manejo de componentes delicados.
Durante esta práctica, el propósito fue familiarizarse con la programación y control de movimientos de un robot industrial mediante el entorno Epson RC+. El objetivo específico fue programar al Epson C4 para mover un fusible desde una posición inicial hacia una ubicación predeterminada, utilizando la pinza del robot para sujetar y liberar el objeto de forma precisa. La tarea consistió en diseñar y programar los movimientos que el robot debía realizar, incluyendo el control de la pinza para garantizar que el fusible fuera transportado de manera eficiente y liberado en el punto exacto.
Para lograr estos objetivos, se desarrolló una secuencia de instrucciones en el entorno Epson RC+, donde se definieron las trayectorias del robot, las posiciones de agarre y liberación, así como las velocidades y orientaciones necesarias para completar la tarea.

## Objetivos
Escribir un código en el software RC+7.0 para manipular el robot Epson que sea capas de tomar un fusible del estante asignado y éste sea colocado sobre una caja.

## Desarrollo
**Seteo del punto home**
Como primera instancia, se requirió hacer el ajuste del origen de coordenadas del robot, asignando como valores en los ejes cartesianos como “cero” en cada uno de ellos en la configuración Word, mientras que en la configuración Join se ajustaron todas las articulaciones excepto de J5 a 0°; mientras que J5 se le asignó el valor de 90°. Tal y como se muestra en la Figura 1:
![Captura de pantalla 2024-09-05 091638](https://github.com/user-attachments/assets/98850b11-6703-48b5-8896-c5016be9ff65)

Al seleccionar el menú de *home config* el programa transforma estos valores en valores numericos para las instrucciones del robot, figura 2
![Captura de pantalla 2024-09-05 091759](https://github.com/user-attachments/assets/29769186-b020-4dc9-9251-08bfc62e7b8d)

**Guardar coordenadas** 
El software ofrece la opción de mover el robot a voluntad del operador y, además, guardar la coordenada en la que se encuentra el brazo robótico en ese preciso instante mediante la seleccion del numero de movimiento se puede asignar un nombre para la posición designada y con el botón *teach* se guarda dichas coordenadas, figura 3.
![image](https://github.com/user-attachments/assets/c368d2c2-4eb5-4ec7-b316-9a49a4207f70)

De esta manera, se conectó el equipo de computo con el brazo robotico mediante el cable USB, permitiendo determinar los puntos fisicos reales en la zona de trabajo y determinar las posiciones necesarias para realizar la encomienda, mover un fusible de lugar.

De igual forma, se probo la pinza neumatica mendiante el *I/O monitor* (Figura 4) que permite encender y apagar de forma manual las salidas digitales del brazo, en este caso usando la salida 2 que corresponde a la pinza neumatica.
![Captura de pantalla 2024-09-05 094516](https://github.com/user-attachments/assets/24170739-ca5b-4780-8588-a33f4b842dfa)

Con los puntos definidos y guardados se precedió con las líneas de comandos para las trayectorias. 

**Comandos básicos de movimiento**
El software cuenta con comandos predefinidos para ejecutar diversas acciones con el robot. Los comandos empleados durante el desarrollo de la práctica en el laboratorio son los que se mencionan en seguida. 
*Home* Mueve el robot hacia la posición del origen de coordenadas previamente configurada.
*Go* Mueve el robot hacia el punto de interés.
*On* Se encarga de activar la salida digital correspondiente, en este caso, la pinza neumática del efector final.
*Off* Apaga la salida digital seleccionada.

El código mostrado en la figura 5 ejecuta el objetivo de la práctica.
![image](https://github.com/user-attachments/assets/1d128420-6a9a-4704-81a8-29b748e7bd63)

Es decir, primero posiciona el robot en el origen de coordenadas, se abre la pinza en la línea número 2 y movemos el robot hacia el punto Arriba que es donde se encuentra el fusible a tomar y bajamos hasta donde está este último en la siguiente línea de código Agarrar. Cerramos la pinza con Off 2 para agarrar el fusible y movemos el brazo hacia Arriba para evitar choques con objetos dentro del área de trabajo. Devolvemos el robot hacia la posición de Home para que, desde ahí, se mueva hacia la posición de Soltar, abrimos la pinza con on 2 para soltar la pieza sobre una cajita y; finalmente, volvemos a la posición inicial del robot (Home).

Resultados

Con lo anterior mencionado, se procedió a ejecutar el código.
En la figura 6, se observa el brazo posicionado en el punto *Arriba* listo para bajar a tomar el fusible.
![Imagen de WhatsApp 2024-09-05 a las 09 49 14_9d73af24](https://github.com/user-attachments/assets/0a4d6340-5b49-45d2-bb6e-e83b6885a676)

Por otro lado, la figura 7 muestra el momento en el que el robot está tomando el fusible del estante donde estos están ubicados tras ejecutar el punto *Agarrar* y activar el actuador neumatico. 
![Imagen de WhatsApp 2024-09-05 a las 09 49 14_1259f77a](https://github.com/user-attachments/assets/9c5d088c-926f-4e60-a5c9-27aa420e207a)

Una vez completado todo el codigo, se realizo la tarea de forma exitosa.




## Conclusiones
- **Uriel Vladimir Alvarez Tapia:** Gracias al ejercicio de esta practica fue posible conocer el principio basico de la programacion de puntos del brazo robotico Epson C4, gracias a esta herramienta y a los comandos de movimiento *Home, Go, On y Off* fue posible generar una rutina de movimientos eficiente para una tarea sencilla mediante pocas lineas de codigo demostrando y enfatizando la versatilidad, rapidez y eficacia que se pueden obtener con estos equipos. 
- **Miguel Angel Castañeda Garcia:** La finalidad de la práctica consistió en escribir un código en el software para mover el robot y que este tomada una pieza y la colocara sobre una caja, luego de haber culminado la prueba en el laboratorio el resultado fue exitoso. 
Se debe recalcar que es de vital importancia familiarizarse con el entorno tanto del robot (para evitar conflictos con los objetos cuando realice una trayectoria) y con el software (para sacar el máximo provecho del mismo).
- **Diana Alejandra Mendoza Mendoza:** La práctica permitió una comprensión sólida de los principios básicos de la programación y control de robots industriales. Al programar el Epson C4 para realizar una tarea específica, como el transporte de un fusible, se evidenció la importancia de planificar cuidadosamente los movimientos y coordinar el uso de herramientas, como la pinza. Además, se reforzó la relevancia del entorno de programación Epson RC+ como una herramienta efectiva para la automatización de procesos en entornos industriales, destacando su precisión y flexibilidad.
## Referencias
