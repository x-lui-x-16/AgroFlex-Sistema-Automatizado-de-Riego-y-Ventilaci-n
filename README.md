<img width="1000" height="400" alt="Diseño sin título (7)" src="https://github.com/user-attachments/assets/6d91e361-7074-449a-9ed4-ed40957d65a1" />

## 🌱 Sobre el proyecto
AgroFlex es un proyecto de robótica y automatización agrícola que consiste en el diseño y construcción de un módulo tecnológico compacto, adaptable y autónomo, destinado a mejorar el cuidado de los cultivos mediante el monitoreo de variables ambientales y la ejecución automática de acciones de mantenimiento.

El sistema utiliza un **Arduino Nano Every** como unidad de control, encargado de procesar las lecturas de los sensores y gestionar el funcionamiento de los actuadores. Mediante un sensor de humedad del suelo y un sensor ambiental DHT22, el módulo supervisa las condiciones del entorno y responde a las necesidades detectadas: activa el sistema de riego cuando la tierra presenta un nivel de humedad inferior al umbral establecido y pone en funcionamiento un mini ventilador cuando la temperatura ambiental supera el límite configurado. Además, incorpora una **pantalla LCD con interfaz I2C** que permite visualizar información recopilada durante el monitoreo.

### 🎯 El problema que buscamos resolver
EEl cuidado de las plantas y los cultivos requiere atención constante, especialmente en lo relacionado con el suministro de agua y las condiciones ambientales. Sin embargo, muchas personas no siempre disponen del tiempo necesario para atender sus plantas debido a sus responsabilidades diarias, sus horarios de trabajo o estudio y otras actividades.

Esta situación es frecuente en hogares y apartamentos, donde las personas pueden pasar varias horas fuera de casa sin supervisar sus plantas o ausentarse durante varios días por viajes, vacaciones u otros compromisos. Cuando no existe un sistema de riego programado o una persona que se encargue de su cuidado, las plantas pueden permanecer demasiado tiempo sin recibir agua, lo que favorece la deshidratación del suelo y puede afectar su crecimiento e incluso provocar que se sequen.

Por otro lado, también existe el problema del riego excesivo. Algunas personas, al intentar asegurarse de que sus plantas reciban suficiente agua, riegan repetidamente hasta que toda la tierra parece estar mojada, sin comprobar previamente su nivel de humedad. Esta práctica puede desperdiciar agua y, dependiendo del drenaje y las necesidades de la planta, provocar un exceso de humedad perjudicial para sus raíces.

A estas dificultades se suman las variaciones de temperatura, que pueden generar condiciones desfavorables para las plantas cuando no se detectan a tiempo y no se dispone de una ventilación adecuada.

AgroFlex surge como una alternativa para afrontar estas situaciones mediante un sistema que monitorea la humedad del suelo y la temperatura ambiental, y responde automáticamente cuando las mediciones alcanzan las condiciones establecidas. De esta manera, busca reducir la dependencia del cuidado manual, evitar riegos innecesarios y facilitar el mantenimiento de las plantas incluso cuando sus propietarios no se encuentran en casa.

El propósito no es sustituir por completo la atención humana, sino proporcionar una herramienta que ayude a mantener un cuidado más constante, controlado y eficiente.

### 🌿 Una solución adaptable
A diferencia de las propuestas que requieren construir un invernadero automatizado desde cero, AgroFlex está concebido como un módulo independiente que puede incorporarse a un espacio de cultivo ya existente. Su diseño busca facilitar la instalación y permitir que el mismo concepto pueda adaptarse a diferentes entornos mediante ajustes en los parámetros de control y en la disposición de sus componentes.

Esta característica permite explorar su aplicación en macetas, huertos domésticos, camas de cultivo y pequeños invernaderos, siempre que se disponga de las condiciones necesarias para instalar los sensores, alimentar el sistema y suministrar agua para el riego.

### 🎯 Objetivo del proyecto
Desarrollar y validar un prototipo de automatización agrícola capaz de monitorear la humedad del suelo y la temperatura ambiental, controlar el riego y la ventilación de acuerdo con umbrales configurados y proporcionar información al usuario mediante una pantalla LCD, manteniendo un diseño compacto y adaptable a diferentes espacios de cultivo.

### ✨ Beneficios esperados
- **Cuidado durante las ausencias:** ayudar a mantener el riego y la ventilación cuando el propietario se encuentra fuera de casa durante varias horas o días, siempre que el sistema disponga de alimentación, agua y condiciones adecuadas de funcionamiento.
- **Uso más eficiente del agua:** activar el riego según las lecturas del sensor y los umbrales configurados, evitando suministrar agua innecesariamente cuando el suelo todavía presenta suficiente humedad.
- **Prevención de la falta de riego:** reducir el riesgo de que las plantas permanezcan demasiado tiempo sin recibir agua debido a olvidos o falta de supervisión.
- **Control de la temperatura:** activar la ventilación cuando se superen los límites establecidos para el sistema.
- **Menor supervisión manual:** automatizar determinadas tareas del cuidado cotidiano de las plantas.
- **Adaptabilidad:** incorporar el módulo a macetas, huertos y otros espacios de cultivo existentes sin requerir una estructura agrícola nueva.
- **Monitoreo accesible:** consultar información de los sensores directamente en la pantalla LCD con interfaz I2C.
- **Potencial de replicación:** servir como base para futuras aplicaciones en hogares, apartamentos, huertos escolares y comunitarios.

AgroFlex integra electrónica, programación y automatización en una solución práctica orientada a explorar cómo la tecnología puede contribuir al cuidado de los cultivos. Su desarrollo también permite evaluar el comportamiento de los sensores y actuadores en condiciones reales, identificar oportunidades de mejora y establecer una base para futuras ampliaciones del sistema.

## ⚙️ Funcionamiento del sistema
AgroFlex funciona mediante un ciclo continuo de monitoreo, procesamiento de datos y respuesta automatizada. El Arduino Nano Every recibe información de los sensores, compara las lecturas con los umbrales configurados y determina si es necesario activar alguno de los actuadores. Al mismo tiempo, la pantalla LCD con interfaz I2C proporciona información visual sobre el estado del sistema.

### 🌡️ Monitoreo de las condiciones ambientales 
El sistema obtiene información de dos variables principales:
- **Humedad del suelo:** un sensor instalado en la tierra permite identificar si el sustrato presenta condiciones de humedad adecuadas o si necesita riego, de acuerdo con la calibración y los parámetros definidos.
- **Temperatura ambiental:** el sensor DHT22 mide la temperatura del entorno y proporciona información para determinar cuándo puede ser necesaria la ventilación.

Las lecturas se envían al Arduino Nano Every, que las procesa para evaluar las condiciones del cultivo. La frecuencia de lectura y el tratamiento de los valores dependerán de la programación implementada.

### 🧠 Procesamiento de las lecturas 
El Arduino Nano Every actúa como la unidad central de control. Su programa compara las mediciones obtenidas con los umbrales establecidos para el cultivo de prueba y decide qué acciones ejecutar.

Para el prototipo se contempla un umbral de referencia de **50 % de humedad del suelo para el cultivo de tomate**. Cuando la lectura se encuentra por debajo de ese valor, el sistema puede activar el riego, siempre que se cumplan las condiciones previstas en el programa.

En el caso de la temperatura, el controlador compara la medición del DHT22 con el límite configurado para activar la ventilación. Ambos parámetros pueden requerir ajustes según el cultivo, las condiciones ambientales y la calibración de los sensores.

### 💧 Activación automática del riego 
Cuando el sistema identifica que la humedad del suelo ha descendido por debajo del umbral establecido, el Arduino Nano Every activa el mecanismo de riego mediante una mini bomba de agua o una electroválvula. El agua se distribuye hacia la planta mediante una manguera u otro mecanismo de conducción.

Este funcionamiento permite que el riego dependa de las condiciones medidas por el sensor y no únicamente de un horario fijo o de la decisión manual del usuario. Por ejemplo, si una persona sale de casa durante varias horas, el sistema puede detectar que el suelo necesita agua y activar el riego sin que sea necesario que el propietario esté presente.

Asimismo, el monitoreo de la humedad busca evitar que se suministre agua innecesariamente cuando el suelo todavía presenta un nivel suficiente según los parámetros configurados. Esto puede contribuir a reducir el desperdicio de agua asociado con el riego excesivo.

Para controlar el suministro, la programación debe establecer una duración de riego adecuada y permitir que el sistema vuelva a evaluar la humedad antes de iniciar otro ciclo, según la lógica implementada. De este modo, se busca proporcionar agua de manera controlada y disminuir tanto el riesgo de que la planta permanezca demasiado tiempo sin riego como el de aplicar agua en exceso.

La eficacia de este mecanismo dependerá de la calibración del sensor, de la ubicación de la sonda, de las necesidades del cultivo y de los parámetros establecidos. Por ello, el sistema debe validarse mediante pruebas para comprobar que la cantidad y la frecuencia de riego sean apropiadas.

### 🌬️ Control automático de la ventilación 
Cuando el DHT22 detecta una temperatura superior al límite configurado, el Arduino activa el mini ventilador para favorecer la circulación del aire alrededor del cultivo.

El ventilador permanece sujeto a la lógica de control implementada, que debe determinar cuándo se activa y cuándo se apaga en función de la temperatura medida. De esta manera, la ventilación se gestiona según las condiciones detectadas y no exclusivamente mediante intervención manual.

La ventilación contribuye a mejorar la circulación del aire, aunque su capacidad para reducir la temperatura dependerá de las condiciones del entorno, la ubicación del ventilador y las características del espacio de cultivo.

### 📟 Visualización de información mediante la pantalla LCD I2C 
El prototipo incorpora una pantalla LCD conectada al Arduino Nano Every mediante un módulo de comunicación I2C. Esta interfaz permite presentar información de las lecturas de los sensores y facilita la observación del comportamiento del sistema durante su funcionamiento.

La pantalla sirve como medio de retroalimentación para el usuario, que puede consultar los datos mostrados sin necesidad de mantener conectado el sistema a una computadora.

La información exacta, el formato de presentación y la frecuencia de actualización dependerán de la programación utilizada. Según la implementación, la pantalla puede mostrar valores ambientales y de humedad, así como información relacionada con el funcionamiento del riego y la ventilación.

### 🔄 Ciclo continuo de monitoreo y respuesta 
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

## 🔀 Diagrama de funcionamiento
El siguiente diagrama representa el ciclo de monitoreo, evaluación y respuesta automática de AgroFlex.
<p align="center">
  <img width="1920" height="2265" alt="DiagramadeFUNC" src="https://github.com/user-attachments/assets/996178f0-1285-4398-af0b-559664981436" />
</p>

## 🧩 Componentes y arquitectura del sistema 
AgroFlex está compuesto por un conjunto de elementos electrónicos y mecánicos que trabajan de manera coordinada para supervisar las condiciones del entorno y automatizar el cuidado de las plantas. El sistema utiliza sensores para obtener información del suelo y del ambiente, un microcontrolador para procesar las lecturas y actuadores que responden a las condiciones detectadas.

El diseño busca mantener una estructura compacta, adaptable y fácil de instalar en macetas, jardines, huertos domésticos o invernaderos existentes, sin necesidad de construir una estructura nueva.

### 🔌 Componentes principales 
| Imagen | Componente y función |
|---|---|
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/fe2b7c20-2a54-4e14-8a7f-f0a9d40189d1" /> | **🧠 Arduino Nano Every — Unidad de control**<br>Es el microcontrolador encargado de recibir las lecturas de los sensores, evaluar las condiciones programadas y controlar el funcionamiento del sistema de riego y ventilación. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/b6509021-ae83-49fc-8659-abb9f295c771" /> | **💧 Sensor de humedad del suelo**<br>Mide la humedad del sustrato para determinar si la planta necesita agua. Su lectura permite activar el riego cuando la humedad desciende por debajo del umbral configurado. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/a0ef645e-5f1e-4a32-b0b5-86ea2a3df256" /> | **🌡️ Sensor DHT22 — Temperatura ambiental**<br>Registra la temperatura del ambiente para que el sistema pueda identificar cuándo se supera el límite establecido y activar la ventilación. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/7e047434-e465-420a-9f84-64f378195c78" /> | **🚿 Mini bomba de agua**<br>Permite suministrar agua a la planta cuando el sistema detecta que la humedad del suelo es inferior al valor establecido. La elección depende de la configuración hidráulica del prototipo. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/6b2eae1e-5a37-4a6e-a437-c9cef4b66b6f" /> | **🌬️ Mini ventilador**<br>Favorece la circulación del aire cuando la temperatura ambiental supera el umbral programado. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/01c7bb58-f405-4b1b-8fdc-37d354d673f3" /> | **📟 Pantalla LCD con interfaz I2C**<br>Presenta información del sistema, como las lecturas de los sensores y el estado de funcionamiento, para facilitar la supervisión del prototipo. |
| <img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/47b4fa81-af9f-48db-8f11-94693b8e9500" /> | **🔌 Modulo Relé**<br>Permite accionar la bomba y el ventilador desde las señales de control del microcontrolador. Debe utilizarse una etapa de potencia adecuada para las características eléctricas de cada actuador. |

### 🏗️ Arquitectura de funcionamiento 
El sistema sigue una secuencia de supervisión, procesamiento y respuesta automática:

1. **Captura de datos:** los sensores registran la humedad del suelo y la temperatura ambiental.
2. **Procesamiento:** el Arduino Nano Every recibe las lecturas y las compara con los umbrales configurados.
3. **Decisión:** el programa determina si es necesario activar el riego, la ventilación o mantener ambos sistemas apagados.
4. **Accionamiento:** el circuito de control activa el dispositivo correspondiente cuando se cumple una condición.
5. **Visualización:** la pantalla LCD muestra información relevante para conocer el estado del sistema.
6. **Repetición del ciclo:** el sistema vuelve a leer los sensores para actualizar las decisiones mientras permanece encendido.

### 📊 Criterios de control 
| Variable supervisada | Condición programada | Respuesta esperada |
|---|---|---|
| Humedad del suelo | La humedad cae por debajo del umbral configurado. | Activar el riego durante el tiempo definido en el programa y volver a evaluar la humedad. |
| Temperatura ambiental | La temperatura supera el límite establecido. | Activar el ventilador para favorecer la circulación del aire. |
| Condiciones normales | Los valores se mantienen dentro de los límites configurados. | Mantener los actuadores apagados cuando no sean necesarios. |

Los umbrales y tiempos de activación deben ajustarse mediante pruebas, considerando el tipo de planta, las características del sustrato, la ubicación de los sensores y las necesidades de ventilación.

## 📸 Prototipo y galería de imágenes 
En esta sección se documenta el desarrollo físico de AgroFlex mediante fotografías del montaje, la distribución de sus componentes y las pruebas realizadas. La galería permite observar cómo se integran los elementos electrónicos e hidráulicos para formar un sistema compacto de riego y ventilación automatizados.

Las imágenes también sirven como registro del progreso del proyecto y facilitan que otras personas comprendan la construcción y el funcionamiento del prototipo.

### 🤖 Galería del prototipo 
| Imagen | Descripción |
|---|---|
| <img src="media/prototipo/prototipo-completo.jpg" width="260" alt="Vista general del prototipo AgroFlex"> | **🤖 Vista general de AgroFlex**<br>Fotografía del prototipo completo, mostrando la disposición del controlador, los sensores, la pantalla y los elementos de riego y ventilación. |
| <img src="media/prototipo/montaje-electronico.jpg" width="260" alt="Montaje electrónico de AgroFlex"> | **🔧 Montaje electrónico**<br>Vista del Arduino Nano Every y las conexiones utilizadas para integrar los sensores, la pantalla LCD y el circuito de control de los actuadores. |
| <img src="media/prototipo/sensor-suelo-instalado.jpg" width="260" alt="Sensor de humedad instalado en el sustrato"> | **🌱 Instalación del sensor de humedad**<br>Ubicación del sensor en el sustrato para obtener lecturas representativas de la humedad disponible para la planta. |
| <img src="media/prototipo/sensor-temperatura.jpg" width="260" alt="Sensor DHT22 instalado"> | **🌡️ Supervisión de la temperatura**<br>Posición del sensor DHT22 para medir la temperatura ambiental sin obstruir innecesariamente la circulación del aire. |
| <img src="media/prototipo/sistema-riego.jpg" width="260" alt="Sistema de suministro de agua"> | **💦 Sistema de riego**<br>Instalación de la bomba o válvula y la conducción del agua hacia la planta. Esta imagen permite apreciar cómo se realiza el suministro de agua. |
| <img src="media/prototipo/sistema-ventilacion.jpg" width="260" alt="Sistema de ventilación del prototipo"> | **🍃 Sistema de ventilación**<br>Montaje del ventilador y su conexión al circuito de control para responder a las condiciones de temperatura detectadas. |
| <img src="media/prototipo/pantalla-lcd.jpg" width="260" alt="Lecturas en la pantalla LCD"> | **📟 Visualización de datos**<br>Fotografía de la pantalla LCD durante el funcionamiento, mostrando las lecturas o los estados disponibles en el programa. |
| <img src="media/prototipo/prueba-funcionamiento.jpg" width="260" alt="Prueba de funcionamiento de AgroFlex"> | **🧪 Pruebas de funcionamiento**<br>Registro de una prueba en la que se comprueba la lectura de los sensores y la respuesta de los actuadores ante las condiciones configuradas. |

### 🧪 Registro de pruebas 
Además de las fotografías del montaje, se recomienda documentar las pruebas realizadas para comprobar que el sistema responde de acuerdo con su programación.

| Prueba | Procedimiento | Resultado que se debe registrar |
|---|---|---|
| Lectura de humedad | Comprobar la lectura del sensor en distintas condiciones del sustrato. | Valores obtenidos y estabilidad de las mediciones. |
| Activación del riego | Reducir la humedad por debajo del umbral configurado. | Si la bomba o válvula se activa y suministra agua correctamente. |
| Lectura de temperatura | Comparar la lectura del DHT22 con las condiciones ambientales. | Temperatura registrada y comportamiento del sensor. |
| Activación de la ventilación | Simular o esperar una temperatura superior al límite programado. | Si el ventilador se activa correctamente. |
| Pantalla LCD | Encender el sistema y observar la información presentada. | Si los datos y estados se muestran correctamente. |
| Ciclo automático | Mantener el sistema funcionando y observar sus respuestas. | Comportamiento general, posibles errores y ajustes necesarios. |

Los resultados deben completarse con las observaciones reales obtenidas durante las pruebas. No se deben presentar resultados esperados como si ya hubieran sido comprobados.

### 🚀 Evidencias y mejoras 
Las fotografías y los registros de prueba permitirán identificar oportunidades de mejora en la distribución de los componentes, la ubicación de los sensores, la conducción del agua y la respuesta de los actuadores.

Esta documentación se actualizará conforme avance el desarrollo de AgroFlex, de modo que el repositorio refleje la evolución del prototipo desde el montaje inicial hasta las pruebas finales.

