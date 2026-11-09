# UX y Flujo del Jugador


## Flujo principal

```text
Inicio → Menú principal → Nueva partida o Continuar
Nueva partida → Tutorial en la Selva → Ruinas → Mesa espectral → Iglesia
Iglesia → Tres vitrales → Derrota del Diablo → Fotografía y revelación → Sendero → Créditos
Durante el juego → Pausa → Reanudar, Opciones, Reiniciar punto o Menú principal
Captura → Reintentar desde el último punto de control o Menú principal
```

## Primeros minutos

1. Iktan despierta en una zona protegida de la Selva. El jugador aprende a moverse con WASD y a orientar la cámara con el ratón.
2. Abbi señala la primera cobertura. El jugador practica agacharse con Ctrl y observa la señal de ocultamiento.
3. Desde cobertura, el jugador observa al Nahual. Mantiene el botón derecho para apuntar y pulsa el izquierdo para lanzar una piedra.
4. El impacto desvía al Nahual. El jugador observa su reacción, cruza hacia la siguiente cobertura y avanza a las ruinas.

## Retroalimentación

Para cada acción importante define:

**Entrada → Respuesta visual → Respuesta sonora → Resultado**

| Entrada o evento | Respuesta visual | Respuesta sonora | Resultado |
| --- | --- | --- | --- |
| Agacharse | Cambio de postura. Icono de ocultamiento y viñeta leve cuando la cobertura protege a Iktan. | Pasos más suaves al moverse. | Reduce la exposición y el ruido de pasos. |
| Apuntar y lanzar | Trayectoria, marca prevista de impacto e indicador de recarga. | Impacto en la posición real. | El enemigo que lo oye puede cambiar de ruta u orientación. |
| Mantener E | Barra de progreso y nombre de la acción. | Sonido breve al completarse. | Derriba la columna si el Nahual sigue dentro de la trampa, o retira las tablas del vitral. |
| Exponerse a una amenaza | Señal de sospecha del Nahual o haz rojo visible en la Iglesia. | Señal direccional de la amenaza. | El Nahual puede perseguir. Un haz sin cobertura interpuesta causa captura inmediata. |
| Completar un objetivo | Cambio visible en el escenario y actualización del objetivo o contador. | Confirmación breve. | El jugador identifica el siguiente paso. |
| Captura | Transición a la pantalla de derrota. | Corte sonoro breve. | Reintentar restaura el último punto de control. |

## Fricción intencional

El reto consiste en esperar una abertura, calcular el ruido y exponerse durante una interacción. El diseño debe corregir capturas con causa difícil de identificar, coberturas visualmente ambiguas, indicaciones tapadas por la niebla y demoras al reintentar. En la Iglesia, cada vitral debe ofrecer una ruta que permita cruzar, retirar las tablas y volver a cobertura dentro de la distracción.

## Descubrimiento

¿Cómo sabe el jugador:

- **Qué hacer.** El HUD muestra el objetivo actual. En la nave indica el avance de los tres vitrales.
- **Dónde ir.** Las coberturas, la composición del escenario y la mirada del acompañante orientan el recorrido. El cempasúchil marca la salida después de la revelación.
- **Con qué interactuar.** La indicación contextual aparece al acercarse a una acción disponible y muestra la tecla asignada.
- **Qué ocurrió.** La reacción del enemigo, el derrumbe, la entrada de luz y la transformación del pedestal comunican los cambios de estado.
- **Por qué ganó o perdió.** La posición del Nahual o del haz permite identificar una captura. Cada vitral se confirma de inmediato. El tercero disuelve al Diablo y permite tomar la fotografía.


> **Navegación:** [[00 - Índice]] · ← [[05 - Audio y Música]] · [[02 - UI y Menús]] →
