<img width="1000" height="400" alt="Diseño sin título (7)" src="https://github.com/user-attachments/assets/6d91e361-7074-449a-9ed4-ed40957d65a1" />

## Sobre el proyecto
AgroFlex es un proyecto de robótica y automatización agrícola que consiste en el diseño y construcción de un módulo tecnológico compacto, adaptable y autónomo, destinado a mejorar el cuidado de los cultivos mediante el monitoreo de variables ambientales y la ejecución automática de acciones de mantenimiento.

El sistema utiliza un **Arduino Nano Every** como unidad de control, encargado de procesar las lecturas de los sensores y gestionar el funcionamiento de los actuadores. Mediante un sensor de humedad del suelo y un sensor ambiental DHT22, el módulo supervisa las condiciones del entorno y responde a las necesidades detectadas: activa el sistema de riego cuando la tierra presenta un nivel de humedad inferior al umbral establecido y pone en funcionamiento un mini ventilador cuando la temperatura ambiental supera el límite configurado. Además, incorpora una **pantalla LCD con interfaz I2C** que permite visualizar información recopilada durante el monitoreo.

### El problema que buscamos resolver
EEl cuidado de las plantas y los cultivos requiere atención constante, especialmente en lo relacionado con el suministro de agua y las condiciones ambientales. Sin embargo, muchas personas no siempre disponen del tiempo necesario para atender sus plantas debido a sus responsabilidades diarias, sus horarios de trabajo o estudio y otras actividades.

Esta situación es frecuente en hogares y apartamentos, donde las personas pueden pasar varias horas fuera de casa sin supervisar sus plantas o ausentarse durante varios días por viajes, vacaciones u otros compromisos. Cuando no existe un sistema de riego programado o una persona que se encargue de su cuidado, las plantas pueden permanecer demasiado tiempo sin recibir agua, lo que favorece la deshidratación del suelo y puede afectar su crecimiento e incluso provocar que se sequen.

Por otro lado, también existe el problema del riego excesivo. Algunas personas, al intentar asegurarse de que sus plantas reciban suficiente agua, riegan repetidamente hasta que toda la tierra parece estar mojada, sin comprobar previamente su nivel de humedad. Esta práctica puede desperdiciar agua y, dependiendo del drenaje y las necesidades de la planta, provocar un exceso de humedad perjudicial para sus raíces.

A estas dificultades se suman las variaciones de temperatura, que pueden generar condiciones desfavorables para las plantas cuando no se detectan a tiempo y no se dispone de una ventilación adecuada.

AgroFlex surge como una alternativa para afrontar estas situaciones mediante un sistema que monitorea la humedad del suelo y la temperatura ambiental, y responde automáticamente cuando las mediciones alcanzan las condiciones establecidas. De esta manera, busca reducir la dependencia del cuidado manual, evitar riegos innecesarios y facilitar el mantenimiento de las plantas incluso cuando sus propietarios no se encuentran en casa.

El propósito no es sustituir por completo la atención humana, sino proporcionar una herramienta que ayude a mantener un cuidado más constante, controlado y eficiente.

### Una solución adaptable
A diferencia de las propuestas que requieren construir un invernadero automatizado desde cero, AgroFlex está concebido como un módulo independiente que puede incorporarse a un espacio de cultivo ya existente. Su diseño busca facilitar la instalación y permitir que el mismo concepto pueda adaptarse a diferentes entornos mediante ajustes en los parámetros de control y en la disposición de sus componentes.

Esta característica permite explorar su aplicación en macetas, huertos domésticos, camas de cultivo y pequeños invernaderos, siempre que se disponga de las condiciones necesarias para instalar los sensores, alimentar el sistema y suministrar agua para el riego.

### Objetivo del proyecto
Desarrollar y validar un prototipo de automatización agrícola capaz de monitorear la humedad del suelo y la temperatura ambiental, controlar el riego y la ventilación de acuerdo con umbrales configurados y proporcionar información al usuario mediante una pantalla LCD, manteniendo un diseño compacto y adaptable a diferentes espacios de cultivo.

### Beneficios esperados
- **Cuidado durante las ausencias:** ayudar a mantener el riego y la ventilación cuando el propietario se encuentra fuera de casa durante varias horas o días, siempre que el sistema disponga de alimentación, agua y condiciones adecuadas de funcionamiento.
- **Uso más eficiente del agua:** activar el riego según las lecturas del sensor y los umbrales configurados, evitando suministrar agua innecesariamente cuando el suelo todavía presenta suficiente humedad.
- **Prevención de la falta de riego:** reducir el riesgo de que las plantas permanezcan demasiado tiempo sin recibir agua debido a olvidos o falta de supervisión.
- **Control de la temperatura:** activar la ventilación cuando se superen los límites establecidos para el sistema.
- **Menor supervisión manual:** automatizar determinadas tareas del cuidado cotidiano de las plantas.
- **Adaptabilidad:** incorporar el módulo a macetas, huertos y otros espacios de cultivo existentes sin requerir una estructura agrícola nueva.
- **Monitoreo accesible:** consultar información de los sensores directamente en la pantalla LCD con interfaz I2C.
- **Potencial de replicación:** servir como base para futuras aplicaciones en hogares, apartamentos, huertos escolares y comunitarios.

AgroFlex integra electrónica, programación y automatización en una solución práctica orientada a explorar cómo la tecnología puede contribuir al cuidado de los cultivos. Su desarrollo también permite evaluar el comportamiento de los sensores y actuadores en condiciones reales, identificar oportunidades de mejora y establecer una base para futuras ampliaciones del sistema.

## Funcionamiento del sistema
AgroFlex funciona mediante un ciclo continuo de monitoreo, procesamiento de datos y respuesta automatizada. El Arduino Nano Every recibe información de los sensores, compara las lecturas con los umbrales configurados y determina si es necesario activar alguno de los actuadores. Al mismo tiempo, la pantalla LCD con interfaz I2C proporciona información visual sobre el estado del sistema.

### 1. Monitoreo de las condiciones ambientales
El sistema obtiene información de dos variables principales:
- **Humedad del suelo:** un sensor instalado en la tierra permite identificar si el sustrato presenta condiciones de humedad adecuadas o si necesita riego, de acuerdo con la calibración y los parámetros definidos.
- **Temperatura ambiental:** el sensor DHT22 mide la temperatura del entorno y proporciona información para determinar cuándo puede ser necesaria la ventilación.

Las lecturas se envían al Arduino Nano Every, que las procesa para evaluar las condiciones del cultivo. La frecuencia de lectura y el tratamiento de los valores dependerán de la programación implementada.

### 2. Procesamiento de las lecturas
El Arduino Nano Every actúa como la unidad central de control. Su programa compara las mediciones obtenidas con los umbrales establecidos para el cultivo de prueba y decide qué acciones ejecutar.

Para el prototipo se contempla un umbral de referencia de **50 % de humedad del suelo para el cultivo de tomate**. Cuando la lectura se encuentra por debajo de ese valor, el sistema puede activar el riego, siempre que se cumplan las condiciones previstas en el programa.

En el caso de la temperatura, el controlador compara la medición del DHT22 con el límite configurado para activar la ventilación. Ambos parámetros pueden requerir ajustes según el cultivo, las condiciones ambientales y la calibración de los sensores.

### 3. Activación automática del riego
Cuando el sistema identifica que la humedad del suelo ha descendido por debajo del umbral establecido, el Arduino Nano Every activa el mecanismo de riego mediante una mini bomba de agua o una electroválvula. El agua se distribuye hacia la planta mediante una manguera u otro mecanismo de conducción.

Este funcionamiento permite que el riego dependa de las condiciones medidas por el sensor y no únicamente de un horario fijo o de la decisión manual del usuario. Por ejemplo, si una persona sale de casa durante varias horas, el sistema puede detectar que el suelo necesita agua y activar el riego sin que sea necesario que el propietario esté presente.

Asimismo, el monitoreo de la humedad busca evitar que se suministre agua innecesariamente cuando el suelo todavía presenta un nivel suficiente según los parámetros configurados. Esto puede contribuir a reducir el desperdicio de agua asociado con el riego excesivo.

Para controlar el suministro, la programación debe establecer una duración de riego adecuada y permitir que el sistema vuelva a evaluar la humedad antes de iniciar otro ciclo, según la lógica implementada. De este modo, se busca proporcionar agua de manera controlada y disminuir tanto el riesgo de que la planta permanezca demasiado tiempo sin riego como el de aplicar agua en exceso.

La eficacia de este mecanismo dependerá de la calibración del sensor, de la ubicación de la sonda, de las necesidades del cultivo y de los parámetros establecidos. Por ello, el sistema debe validarse mediante pruebas para comprobar que la cantidad y la frecuencia de riego sean apropiadas.

### 4. Control automático de la ventilación
Cuando el DHT22 detecta una temperatura superior al límite configurado, el Arduino activa el mini ventilador para favorecer la circulación del aire alrededor del cultivo.

El ventilador permanece sujeto a la lógica de control implementada, que debe determinar cuándo se activa y cuándo se apaga en función de la temperatura medida. De esta manera, la ventilación se gestiona según las condiciones detectadas y no exclusivamente mediante intervención manual.

La ventilación contribuye a mejorar la circulación del aire, aunque su capacidad para reducir la temperatura dependerá de las condiciones del entorno, la ubicación del ventilador y las características del espacio de cultivo.

### 5. Visualización de información mediante la pantalla LCD I2C
El prototipo incorpora una pantalla LCD conectada al Arduino Nano Every mediante un módulo de comunicación I2C. Esta interfaz permite presentar información de las lecturas de los sensores y facilita la observación del comportamiento del sistema durante su funcionamiento.

La pantalla sirve como medio de retroalimentación para el usuario, que puede consultar los datos mostrados sin necesidad de mantener conectado el sistema a una computadora.

La información exacta, el formato de presentación y la frecuencia de actualización dependerán de la programación utilizada. Según la implementación, la pantalla puede mostrar valores ambientales y de humedad, así como información relacionada con el funcionamiento del riego y la ventilación.

### 6. Ciclo continuo de monitoreo y respuesta
Una de las finalidades de AgroFlex es facilitar el cuidado de las plantas en situaciones en las que el usuario no puede supervisarlas constantemente. Esto resulta especialmente útil para personas que viven en casas o apartamentos y pasan gran parte del día fuera, así como para quienes se ausentan durante viajes o vacaciones.

Mientras el prototipo permanezca correctamente alimentado, disponga de agua y funcione dentro de sus condiciones previstas, el sistema puede continuar leyendo los sensores y ejecutar las acciones automáticas programadas. De esta forma, no depende exclusivamente de que el propietario recuerde cuándo regar o cuándo activar la ventilación.

Este mecanismo busca mantener un cuidado más constante y contribuir a un uso más racional del agua. Sin embargo, no garantiza por sí solo que las plantas sobrevivan a cualquier ausencia: será necesario comprobar el funcionamiento del prototipo, asegurar una reserva de agua suficiente y considerar factores como la alimentación eléctrica, el drenaje, las condiciones ambientales y las necesidades particulares de cada planta.

El ciclo general comprende las siguientes etapas:

1. Leer los sensores de humedad del suelo y temperatura ambiental.
2. Procesar los valores recibidos en el Arduino Nano Every.
3. Comparar las mediciones con los umbrales configurados.
4. Activar el riego cuando se cumplan las condiciones establecidas.
5. Activar la ventilación cuando se supere el límite de temperatura.
6. Actualizar la información presentada en la pantalla LCD I2C.
7. Repetir el monitoreo para evaluar las condiciones del cultivo.

Este funcionamiento permite integrar la supervisión ambiental y el control de dos actuadores en un mismo módulo, manteniendo la posibilidad de adaptar los parámetros de funcionamiento a las necesidades del cultivo de prueba.



## Diagrama de funcionamiento
El siguiente diagrama representa el ciclo de monitoreo, evaluación y respuesta automática de AgroFlex.

<p align="center">
  
</p>
