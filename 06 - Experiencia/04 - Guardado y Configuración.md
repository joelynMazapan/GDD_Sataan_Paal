# Guardado y Configuración

## Descripción de la sección

Define cómo se conserva el progreso y qué opciones puede modificar el jugador.

## Guardado

**Tipo:** Automático por puntos de control.

**Cuándo se guarda:** En S1 al iniciar la Selva, S2 antes de las ruinas, S3 tras neutralizar al Nahual y S4 al completar el recuerdo de la mesa. En la Iglesia, I1 se registra antes de entrar en la nave. I2 se registra después de derrotar al Diablo y se actualiza al obtener la fotografía y completar la revelación. El cierre registra la partida completada.

**Qué datos se guardan:** Versión del guardado, nivel, punto de control y hitos confirmados. Incluyen derrumbe, recuerdo de la mesa, derrota del Diablo, fotografía y revelación, y finalización. Reintentar desde I1 restaura los tres vitrales cubiertos. Desde I2 se restaura la derrota del Diablo y, según el hito, la fotografía disponible o el sendero habilitado. Las preferencias se guardan aparte.

**Cantidad de ranuras:** Una ranura local de progreso como propuesta inicial. Nueva partida solicita confirmación si ya existe un guardado.

**Qué ocurre si el guardado falla:** Mostrar un aviso y conservar el último archivo válido. Si el juego se interrumpe, Continuar recupera el último hito confirmado. Si no hay un guardado válido, mostrar un mensaje claro y dejar disponible Nueva partida.

## Configuración

| Categoría | Opciones |
|---|---|
| Audio | Volumen general, música y efectos. |
| Video | Resolución, modo de pantalla y calidad gráfica. |
| Controles | Reasignación, sensibilidad, inversión vertical y opciones de mantener o alternar. |
| Accesibilidad | Subtítulos, tamaño de texto, contraste, reducción de movimiento y destellos, e indicadores visuales. |
| Jugabilidad | Pistas contextuales del acompañante y opción de reiniciar el punto de control desde Pausa. |

## Restablecimiento

Cada categoría puede volver a sus valores iniciales tras confirmación. El restablecimiento de preferencias conserva el progreso. La ranura de progreso solo se sustituye al confirmar una nueva partida.


> **Navegación:** [[00 - Índice]] · ← [[03 - Accesibilidad]] · [[01 - Arquitectura Técnica]] →
