# Reglas y Estados del Juego

## Descripción de la sección

Esta sección define la arquitectura global del software del juego, documentando los diferentes estados que experimenta el usuario desde que abre la aplicación hasta que la cierra, las condiciones para transicionar entre estos estados y las reglas universales inquebrantables que rigen el mundo de Iktan.
## Estados principales

- **Menú principal:** Pantalla inicial con estética de un altar de muertos en penumbras. Opciones: Nueva Partida, Continuar, Opciones, Salir.
- **Carga (Loading):** Pantalla de transición donde se muestra una pequeña vela iluminando datos curiosos sobre la cultura del Día de Muertos o pistas de controles.
- **Jugando (Gameplay):** El estado central. El jugador tiene control total sobre Iktan en los niveles.
- **Pausa:** El tiempo del juego se congela (TimeScale = 0). Permite ajustar volumen, controles o slir al menú.
- **Victoria (Interludio de Altar):** Estado narrativo al final de cada nivel donde Iktan coloca el objeto recolectado (molletes, trompos, mandarinas) en el Altar espectral.
- **Derrota / Game Over:** Se activa cuando un enemigo atrapa a Iktan o la barra de Pánico llega al 100%. Pantalla en negro con la opción de volver a intentar desde el último punto de control (Checkpoint).
- **Créditos:** Pantalla final tras el clímax, donde se lee el mensaje de concientización sobre el secuestro mientras suben los nombres del equipo de desarrollo.

## Transiciones

| Estado origen    | Evento                                       | Estado destino | Condición                                                  |
| ---------------- | -------------------------------------------- | -------------- | ---------------------------------------------------------- |
| Carga            | Carga de _assets_ completada al 100%         | Jugando        | El nivel está completamente instanciado en memoria.        |
| Jugando          | Presionar botón Pausa.                       | Pausa          | El jugador no está en medio de una cinemática de historia. |
| Pausa            | Seleccionar "Reanudar"                       | Jugando        | Ninguna                                                    |
| Pausa            | Seleccionar "Volver al Menú"                 | Menú principal | Confirmación en ventana emergente.                         |
| Jugando          | Hitbox del enemigo choca con hitbox de Iktan | Game Over      | El enemigo alcanza a Iktan.                                |
| Jugando          | Medidor de Pánico llega al 100%              | Game Over      | Estar fuera de cobertura demasiado tiempo en el Cap 4.     |
| Derrota Jugando  | Seleccionar "Reintentar"                     | Carga          | Ninguna.                                                   |
| Victoria (Altar) | Animación de colocar objeto terminada        | Carga          | Iktan cruza la puerta hacia el siguiente capítulo.         |
| Jugando (Cap 4)  | Romper último vitral e Iktan cruza la luz    | Créditos       | Cinématica final concluida.                                |
| Menú principal   | Seleccionar "Nueva Partida" o "Continuar"    | Carga          | Presionar botón de confirmación.                           |
|                  |                                              |                |                                                            |

## Reglas globales

1. **Regla Pacifista (Sin Combate):** Iktan NO puede infligir daño directo a ningún enemigo bajo ninguna circunstancia. Cualquier intento de contacto físico directo con un enemigo resulta en Derrota inmediata.
2. **Regla de Letalidad :** Iktan no tiene barra de salud. Si un enemigo lo toca una sola vez, o si es alcanzado por un obstáculo letal del entorno, el jugador pierde instantáneamente y vuelve al último punto de control.
3. **Prioridad de Sonido :** Los enemigos siempre priorizarán investigar el sonido de una distracción (roca, trompo/entorno) por encima de su ruta de patrulla habitual, a menos que ya estén en estado de "Persecución" persiguiendo visualmente a Iktan.
4. **Inmunidad de Zonas Seguras:** Los puntos de guardado y las "Zonas Seguras" (donde Iktan abraza a Abbi para reducir el pánico) son espacios inalcanzables para la IA enemiga. Los enemigos no pueden patrullar ni ser atraídos dentro de estas zonas.
5. **Masa Mística de Abbi:** Al ser un espíritu de azúcar, la inteligencia artificial enemiga NO puede detectar a Abbi. La perrita puede ladrar, correr o moverse libremente sin alertar a los guardias; el sigilo depende única y exclusivamente de las acciones y el posicionamiento de Iktan.
## Casos especiales

Documenta excepciones importantes para evitar interpretaciones diferentes durante la implementación.

Documentación de excepciones importantes para los programadores del motor:

- **Impacto de roca sobre enemigo:** ¿Qué pasa si el jugador le lanza la roca directamente al cuerpo de un guardia en lugar de al piso?
    
    - _Excepción:_ La roca no le hace daño. Al chocar con el modelo del enemigo, se destruye y el radio de sonido se genera a los pies del guardia. Esto hace que el enemigo se quede quieto mirando al suelo confundido por 2 segundos antes de volver a patrullar.
    - 
- **Parálisis en el aire:** ¿Qué pasa si el medidor de pánico llega al 100% justo cuando el jugador presiona el botón de "Esquivar"?
    
    - _Excepción:_ El juego permitirá que la animación de rodar termine para evitar bugs visuales de físicas (clipping), y en el exacto instante en que Iktan se ponga de pie, se activará el estado de "Game Over" por parálisis.
    
- **Detección en la puerta (Transición de nivel):** ¿Qué pasa si un guardia detecta a Iktan exactamente en el frame en que este interactúa con la puerta para acabar el nivel?
    
    - _Excepción:_ La interacción con objetos de fin de nivel o recompensas otorga "Frames de Invencibilidad" (I-Frames). La animación de Iktan recogiendo los molletes o abriendo la puerta tiene prioridad absoluta, cancelando el aggro (enojo) del enemigo y forzando la Victoria.

> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
