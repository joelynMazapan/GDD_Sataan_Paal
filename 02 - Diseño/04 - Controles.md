# Controles

## Descripción de la sección

Define la relación entre las acciones del jugador y las entradas físicas del dispositivo.

## Mapa de controles


| Acción                           | Teclado                             | Mouse                  | Control   | Táctil   |
| --------------------------------- | ----------------------------------- | ---------------------- | --------- | --------- |
| Movimiento                        | Teclas W, A, S, D                   | No aplica              | No aplica | No Aplica |
| Camara                            | Movimiento del ratón               | No aplica              | No Aplica | No Aplica |
| Agacharse                         | Ctrl izquierdo                      | Mantener Click derecho | No Aplica | No Aplica |
| Correr                            | Mantener Mayús izquierdo           | Click izquierdo        | No Aplica | No Aplica |
| <br>Apuntar                       | Mantener botón derecho             | No aplica              | No Aplica | No Aplica |
| Lanzar                            | Botón izquierdo mientras se apunta | No aplica              | No Aplica | No Aplica |
| Recoger plato o fotografía / colocar plato / avanzar diálogo | E                                   | No aplica              | No aplica | No Aplica |
| Derribar columna / retirar tablas | Mantener E durante 2 s              | No aplica              | No aplica | No aplica |
| Pausa / volver                    | Esc                                 | No aplica              | No aplica | No aplica |
| Confirmar menú                   | Enter o botón izquierdo            | No aplica              | No aplica | No aplica |
| Navegar menú                     | Flechas, WASD o ratón              | No aplica              | No aplica | No aplica |

## Principios de control

* El desplazamiento y la cámara conservan una respuesta consistente en ambos niveles.
* Se permite mover a Iktan mientras apunta a velocidad de caminar o agachado; iniciar apuntado cancela la carrera.
* La cámara retrocede ante paredes sin atravesarlas ni permitir que el modelo desaparezca dentro de ellas.
* Mantener E ocupa la interacción; mover al personaje o iniciar apuntado la cancela antes de ejecutar la nueva acción.
* El centro de la pantalla prioriza un único objetivo válido situado a un máximo de 1,5 m y sin obstrucción.
* Las interfaces capturan la entrada del ratón: pulsar una opción nunca dispara una piedra al cerrar el menú.

## Reasignación

Se propone permitir reasignar acciones, restaurar valores iniciales y guardar preferencias. Si una asignación entra en conflicto con otra del mismo contexto, se informa antes de aplicarla. Se puede elegir entre alternar o mantener para agacharse y para apuntar. La carrera puede alternarse como opción de accesibilidad y se cancela al detenerse, agacharse o apuntar.

La interacción prolongada ofrece una alternativa de pulsar para iniciar y volver a pulsar para cancelar; mantiene los mismos 2 s de exposición. También se proponen sensibilidad, inversión vertical, subtítulos y reducción del movimiento de cámara. La interfaz debe poder operarse sin ratón.

## Entrada y retroalimentación


| Entrada              | Respuesta visual                                                  | Respuesta sonora                                |
| -------------------- | ----------------------------------------------------------------- | ----------------------------------------------- |
| Agacharse            | Cambio de postura; icono de ocultamiento si se cumplen las reglas | Breve transición a derrota sin escena gráfica |
| Apuntar              | Trayectoria e impacto previsto; señal de obstrucción            | Señal discreta al preparar                     |
| Lanzar               | Animación en la postura actual e indicador de recarga            | Impacto en la posición real                    |
| Interacción válida | Nombre de acción, tecla actual y progreso cuando corresponde     | Confirmación al completar                      |
| Nahual sospecha      | Símbolo de alerta en crecimiento                                 | Vocalización y cambio musical                  |
| Haz del Diablo       | Borde visible, dirección de barrido y contraste con el fondo     | Motivo direccional de la amenaza                |
| Captura              | Breve transición a derrota sin escena gráfica                   | Corte sonoro controlado                         |

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
