# Seguridad y Riesgos Técnicos

## Descripción de la sección

Documenta riesgos técnicos y medidas para reducir fallos, pérdida de datos o abuso de sistemas.

## Riesgos

| Riesgo | Probabilidad | Impacto | Mitigación |
|---|---|---|---|
| Guardado incompleto o corrupto | Media | Alto | Escribir y validar un archivo temporal. Conservar la última copia válida. |
| Fotografía o sendero habilitados en un orden incorrecto | Media | Alto | Validar los hitos y probar el guardado antes y después de la derrota del Diablo y de la revelación. |
| Haces detectan a través de cobertura | Media | Alto | Probar oclusión y límites del haz con la geometría real de la nave. |
| Nahual atascado o trampa sin resolver | Media | Alto | Probar rutas navegables y validar su presencia al confirmar la columna. Permitir un nuevo intento si sale de la zona. |
| Caídas de rendimiento en momentos clave | Media | Medio | Medir el derrumbe, la niebla y la apertura del último vitral en el equipo de referencia. |
| Entrada de menú activa una acción de juego | Baja | Medio | Separar los contextos de entrada y consumir las pulsaciones del menú antes de reanudar. |

## Datos sensibles

La versión prevista guarda progreso y preferencias en el equipo del jugador. El diseño contempla una partida individual sin cuentas ni envío de estadísticas.

## Multijugador

El alcance es una partida individual local. La validación se concentra en la integridad del guardado y la coherencia de los hitos.

## Recuperación

Al abrir Continuar, validar la versión y los hitos antes de cargar. Si falla, recuperar la copia válida anterior y avisar al jugador. Si no existe una copia utilizable, ofrecer Nueva partida y conservar el archivo dañado. Tras un cierre inesperado, restaurar el último punto confirmado.


> **Navegación:** [[00 - Índice]] · ← [[04 - Datos y Persistencia]] · [[01 - Alcance]] →
