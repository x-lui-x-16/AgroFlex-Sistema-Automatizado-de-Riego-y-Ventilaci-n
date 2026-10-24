# 🔌 Componentes de AgroFlex
Esta carpeta contiene las fotografías de referencia de los componentes electrónicos y dispositivos que forman parte del sistema automatizado de riego y ventilación AgroFlex.

Las imágenes permiten identificar visualmente los elementos del montaje y complementan la descripción técnica presentada en el `README.md` principal.

## 🧩 Inventario visual
| Archivo | Componente | Función principal |
|---|---|---|
| `arduino-nano-every.jpg` | 🧠 Arduino Nano Every | Procesar las lecturas de los sensores y controlar las acciones automáticas del sistema. |
| `sensor-humedad.jpg` | 💧 Sensor de humedad del suelo | Medir la humedad del sustrato para determinar cuándo se necesita riego. |
| `dht22.jpg` | 🌡️ Sensor DHT22 | Medir la temperatura ambiental para gestionar la ventilación. |
| `bomba-agua.jpg` | 🚿 Mini bomba de agua | Suministrar agua a la planta cuando se cumplen las condiciones de riego. |
| `ventilador.jpg` | 🌬️ Mini ventilador | Favorecer la circulación del aire cuando se supera el límite de temperatura configurado. |
| `pantalla-lcd-i2c.jpg` | 📟 Pantalla LCD con interfaz I2C | Mostrar información de las lecturas y del estado del sistema. |
| `alimentacion.jpg` | 🔋 Sistema de alimentación | Proporcionar la energía necesaria para el funcionamiento del prototipo. |
| `circuito-control.jpg` | 🔌 Circuito de control de actuadores | Permitir el accionamiento de los dispositivos de riego y ventilación. |

## ⚙️ Relación con el sistema
Los componentes documentados trabajan de manera coordinada: los sensores recopilan información del entorno, el Arduino Nano Every procesa las lecturas y el circuito de control permite ejecutar las acciones programadas. La pantalla LCD facilita la consulta de información durante el funcionamiento.

**Nota:** La presencia de un componente en este inventario no implica que todas sus funciones hayan sido validadas. La configuración final debe corresponder al montaje real de AgroFlex.

---

*AgroFlex — Componentes electrónicos y arquitectura del sistema.* 🌱
