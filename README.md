# Proyecto-2--Monitor-de-Paciente-Dual
Proyecto desarrollado para el curso de Electrónica Digital 1 en la Universidad del Valle de Guatemala.
El sistema simula un monitor biomédico utilizando un Arduino, un servomotor, un LED RGB, un display de 7 segmentos, botones y un potenciómetro.


## Integrantes
- Stephany Mejía — 24037
- Camila Tello — 24404

---

# Componentes utilizados
- Arduino Uno/Nano
- Servomotor
- LED RGB
- Display de 7 segmentos
- Potenciómetro
- 2 botones
- Buzzer
- Resistencias
- Protoboard y jumpers

---

# Funcionalidades del sistema

## Modo 0 — Reposo
En este modo el sistema permanece en estado de reposo.

- LED RGB apagado
- Buzzer apagado
- Servo en 0°
- Display muestra “0”

---

## Modo 1 — Monitor de Frecuencia Cardíaca

El potenciómetro simula la frecuencia cardíaca en un rango de 0 a 200 lpm.

El servomotor representa el valor medido en tiempo real:
- 0 lpm = 0°
- 200 lpm = 180°

El LED RGB cambia según el estado:

- Menor a 60 lpm → Amarillo (Bradicardia)
- Entre 60 y 100 lpm → Verde (Normal)
- Mayor a 100 lpm → Rojo (Taquicardia)
- Mayor a 150 lpm → Rojo parpadeante (Taquicardia severa)

El display muestra el número 1 y los valores pueden visualizarse en el Monitor Serial.

---

## Modo 2 — Monitor de Temperatura Corporal

El potenciómetro simula temperaturas entre 20°C y 45°C.

Dependiendo del rango:

- Menor a 35°C → Hipotermia
  - LED morado
  - Servo a 0°

- Entre 35°C y 37°C → Estado normal
  - LED cyan
  - Servo a 45°

- Entre 37°C y 38°C → Febrícula
  - LED amarillo
  - Servo a 90°

- Entre 38°C y 39°C → Fiebre
  - LED rojo/naranja aproximado
  - Servo a 135°

- Mayor a 39°C → Fiebre alta
  - LED blanco
  - Servo a 180°

En condiciones críticas se activa el buzzer como alarma y el botón 2 permite silenciarla.

El display muestra el número 2.

---

# Características del código

- Uso de funciones para modularidad
- Implementación de antirebote lógico
- Reutilización de código mediante `setRGB()`
- Conversión de rangos utilizando `map()`
- Comunicación serial mediante `Serial.print()`

---

# Pines utilizados

- Servo → Pin 7
- LED RGB Rojo → Pin 2
- LED RGB Verde → Pin 4
- LED RGB Azul → Pin 3
- Botón de cambio de modo → Pin 5
- Buzzer → Pin 6
- Potenciómetro → A0
- Botón de alarma → A4

---

# Librerías utilizadas

```cpp
#include <Servo.h>


Objetivo del proyecto
```
#Objetivo del proyecto
Desarrollar un sistema biomédico básico capaz de monitorear variables simuladas de frecuencia cardíaca y temperatura corporal utilizando componentes electrónicos y programación en Arduino.
