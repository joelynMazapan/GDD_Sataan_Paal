# UI y Menús

## Descripción de la sección

Define la estructura funcional de las interfaces y menús.

## Mapa de navegación

```text
Menú principal
├── Nueva partida
├── Continuar
├── Configuración
│   ├── Audio
│   ├── Video
│   ├── Controles
│   └── Accesibilidad
└── Salir
```

## Pantallas

| Pantalla | Propósito y elementos | Acciones y estados | Transición |
| --- | --- | --- | --- |
| Menú principal | Presentar Nueva partida, Continuar, Configuración y Salir. | Continuar se habilita con un guardado válido. | Abre el nivel, Configuración o el cierre del juego. |
| HUD de partida | Mostrar objetivo, piedra disponible o en recarga, indicación contextual y señales de sigilo. En la nave añade el contador de vitrales. | Permite leer disponibilidad, alerta y progreso. | Esc abre la pausa. La captura abre Derrota. |
| Pausa | Detener la simulación y ofrecer Reanudar, Configuración, Reiniciar punto y Volver al menú. | El foco inicial queda en Reanudar. | Vuelve a la partida, abre ajustes o carga el último punto de control. |
| Configuración | Organizar Audio, Video, Controles y Accesibilidad. | Cambiar ajustes, reasignar teclas y restablecer valores por categoría. | Regresa al menú desde el que se abrió. |
| Derrota | Dar una salida clara tras la captura. | Reintentar o volver al menú principal. | Restaura el último punto de control o vuelve al menú. |
| Cierre | Mostrar el mensaje de concientización y los créditos tras recorrer el sendero. | Volver al menú al terminar. | Regresa al menú principal. |

Los menús se pueden recorrer con teclado o ratón. El foco se distingue visualmente y Esc vuelve al nivel anterior. Los clics y teclas usados en menús se consumen antes de volver al control de Iktan.

## Confirmaciones

- **Nueva partida con progreso previo.** El aviso explica que se reemplazará la partida existente. Ofrece «Iniciar nueva partida» y «Cancelar».
- **Reiniciar punto de control o volver al menú durante la partida.** El aviso indica que se perderá el avance posterior al último guardado.
- **Salir o restablecer una categoría.** Confirmar la acción y devolver el foco a la opción anterior al cancelar.


> **Navegación:** [[00 - Índice]] · ← [[01 - UX y Flujo del Jugador]] · [[03 - Accesibilidad]] →
