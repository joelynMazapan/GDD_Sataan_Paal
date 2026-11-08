# Reglas y Estados del Juego

## Estados principales


| Estado              | Control y presentación                                     | Salidas posibles                              |
| ------------------- | ----------------------------------------------------------- | --------------------------------------------- |
| Menú principal     | Nueva partida, Continuar, Opciones y Salir                  | Carga, Opciones o cierre                      |
| Opciones            | Audio, controles y accesibilidad                            | Menú o Pausa, según origen                  |
| Carga               | Preparación del nivel y restauración; sin control jugable | Jugando o mensaje de error                    |
| Jugando             | Control de Iktan, cámara, herramientas e IA                | Pausa, Secuencia narrativa, Derrota o Carga   |
| Pausa               | Simulación congelada y menú accesible                     | Estado previo, Opciones, Carga o Menú        |
| Secuencia narrativa | Cámara y acciones guionizadas; entrada limitada            | Estado previo tras pausa, Jugando o Desenlace |
| Derrota             | Transición breve y opciones Reintentar / Menú             | Carga o Menú                                 |
| Desenlace           | Camino final controlable, sin amenazas activas              | Créditos o Pausa                             |
| Créditos           | Mensaje social y nombres del equipo                         | Menú principal                               |

La secuencia narrativa puede pausarse. Al reanudar se vuelve a la misma secuencia, sin reactivar IA prematuramente. Si se permite omitir una secuencia ya vista, sus hitos y cambios de entorno se aplican antes de devolver el control.

## Transiciones


| Origen                          | Evento                     | Destino             | Condición y resultado                                                   |
| ------------------------------- | -------------------------- | ------------------- | ------------------------------------------------------------------------ |
| Menú                           | Nueva partida              | Carga               | Si existe progreso previo, confirmar su sustitución                     |
| Menú                           | Continuar                  | Carga               | Guardado válido; si no existe, opción deshabilitada                    |
| Carga                           | Nivel preparado            | Jugando o Desenlace | Restaurar punto y objetivos antes de habilitar entradas                  |
| Jugando / Secuencia / Desenlace | Esc                        | Pausa               | Guardar estado de retorno y congelar simulación                         |
| Pausa                           | Reanudar                   | Estado anterior     | Sin repetir entradas mantenidas del menú                                |
| Pausa                           | Reiniciar punto            | Carga               | Confirmación; descartar avances desde el último guardado               |
| Pausa                           | Volver al menú            | Menú               | Confirmar pérdida de avance no guardado                                 |
| Jugando                         | Captura válida            | Derrota             | Bloquear interacción y detener amenazas                                 |
| Derrota                         | Reintentar                 | Carga               | Restaurar último punto coherente                                        |
| Jugando                         | Columna completada         | Secuencia narrativa | Nahual dentro de la trampa; neutralizar y guardar S3                     |
| Secuencia de derrumbe           | Fin                        | Jugando             | Hacer aparecer la mesa espectral                                         |
| Jugando                         | Interactuar con la mesa    | Secuencia narrativa | Al terminar, abrir árboles y guardar S4; las piedras siguen disponibles |
| Jugando                         | Cruzar acceso a la Iglesia | Carga               | Recuerdo de la mesa completado; destino único: Iglesia                  |
| Jugando                         | Llegar al altar            | Secuencia narrativa | Transformación del pedestal y fotografía                               |
| Secuencia de revelación        | Fin                        | Jugando             | Guardar I1 y habilitar acceso al desafío                                |
| Jugando                         | Entrar en la nave          | Jugando             | Activar barrido del Diablo y contador de vitrales                        |
| Jugando                         | Confirmar tercer vitral    | Secuencia narrativa | Desactivar amenaza, mostrar luz y guardar I2                             |
| Secuencia final                 | Fin                        | Desenlace           | Habilitar sendero de cempasúchil                                        |
| Desenlace                       | Cruzar salida de luz       | Créditos           | Marcar partida completada                                                |

## Reglas globales

1. **Vulnerabilidad:** un contacto físico del Nahual activo o un contacto sin oclusión con un haz del Diablo causa captura. La reacción se presenta sin violencia gráfica.
2. **Resolución ambiental:** solo las piedras desvían deliberadamente la atención. La columna y la luz resuelven los enfrentamientos; no existe daño directo con proyectiles.
3. **Cobertura verificable:** ocultamiento depende de postura, volúmenes de hierba válidos y obstáculos reales. Un icono informa el estado, no lo concede.
4. **Percepción coherente:** ningún enemigo conoce la posición actual de Iktan fuera de sus reglas de percepción. Las distracciones no cancelan un avistamiento confirmado.
5. **Papel de Abbi:** guía espiritual, no objetivo de captura ni fuente de alerta enemiga. No modifica recursos de supervivencia.
6. **Objetivos únicos:** columna, recuerdo de la mesa y cada vitral solo pueden completarse una vez por estado restaurado.
7. **Guardado definido:** reintentar conserva los hitos del punto de control y reinicia la situación táctica. Pausar o salir no crea un punto nuevo.
8. **Recorrido:** Selva e Iglesia constituyen todo el contenido jugable. La transición es directa y el final es único.
9. **Seguridad de secuencias:** solo una interacción válida ya completada desactiva la amenaza correspondiente; iniciar una animación no otorga protección anticipada.
10. **Presentación responsable:** no se premia la violencia contra víctimas ni se atribuye a ellas la responsabilidad del secuestro. Las tradiciones y figuras sobrenaturales sirven a una ficción y no se presentan como una interpretación cultural universal.

## Casos especiales


| Caso                                                       | Resolución                                                                              |
| ---------------------------------------------------------- | ---------------------------------------------------------------------------------------- |
| Captura e interacción en el mismo paso de simulación     | Primero se resuelve captura. Si ya fue confirmada, se cancela la interacción            |
| Nahual abandona las ruinas durante la preparación         | No se derriba la columna; se informa la condición faltante y se puede reintentar        |
| Sonido en una posición inaccesible para el Nahual         | Investiga el punto navegable más próximo sin atravesar paredes                         |
| Piedra impacta sobre una amenaza                           | Sin daño ni aturdimiento; sonido de impacto sujeto a las prioridades de IA              |
| Interacción repetida con mesa o vitral resuelto           | No consume objetos ni duplica avance; se oculta la acción completada                    |
| Último vitral confirmado                                  | Se desactivan los haces antes de la secuencia de luz; no se admiten capturas posteriores |
| Cerrar durante una interacción o secuencia no consolidada | Continuar recupera el último punto completo; no se guarda progreso parcial              |
| Pausa durante una investigación o recarga de piedra       | Sus temporizadores quedan congelados y continúan al reanudar                            |
| Abbi pierde la ruta                                        | Recolocación fuera de cámara sobre una superficie válida                              |
| Iktan queda fuera del área navegable por un error         | Restauración del punto con mensaje breve; sin pérdida permanente de progreso           |

## Criterios de aceptación del diseño

* Es posible terminar ambos niveles sin causar daño mediante proyectiles.
* Agacharse, cobertura y ruido producen los mismos resultados ante las mismas condiciones.
* El Nahual puede atraerse a las ruinas y la columna no genera un bloqueo irreversible.
* La escena de la mesa abre el paso sin requerir objetos; las piedras siguen siendo la única herramienta de distracción.
* Cada vitral se puede despejar con una distracción de piedra de 5 s, interacción de 2 s y margen mínimo de 1 s.
* Cada vitral cuenta una sola vez y el tercero resuelve el enfrentamiento.
* Reintentar desde cada punto reconstruye correctamente enemigos, objetos y objetivos.
* Las pistas de Abbi y los mensajes de interfaz funcionan sin depender solo del audio o del color.

## Cierre narrativo

Tras el sendero final se propone el mensaje: **«Iktan es un personaje ficticio. El secuestro deja heridas en las víctimas, sus familias y sus comunidades. Recordar con dignidad y escuchar sus historias nos invita a construir una sociedad más empática y solidaria».**

Los créditos identifican a Renata Cortés Mancilla, Yoel Alfredo Canul Gijon, Zaidy Itzamara Cruz Santiago, Juan David Lomeli Cruz y Brandon Michell Reyes del Ángel. No se asignan cargos individuales hasta que el equipo los confirme.

> **Navegación:** [[00 - Índice]] · ← [[06 - Economía y Recursos]] · [[01 - Premisa y Trama]] →
