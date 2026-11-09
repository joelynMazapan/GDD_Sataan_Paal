# Sistemas del Juego

## Inventario de sistemas


| Sistema               | Propósito                                     | Dependencias                            | Estado     |
| --------------------- | ---------------------------------------------- | --------------------------------------- | ---------- |
| Entrada y movimiento  | Desplazar, agachar, correr y orientar cámara  | Geometría y configuración             | En diseño |
| Percepción e IA      | Visión, audición y respuesta de cada amenaza | Movimiento, coberturas, eventos sonoros | En diseño |
| Herramientas          | Apuntado, piedras y recarga                    | Entrada, colisiones                     | En diseño |
| Entorno interactivo   | Columna, plato de molletes, mesa, árboles y vitrales             | Objetivos, percepción                  | En diseño |
| Guía de Abbi         | Seguimiento y pistas                           | Navegación, objetivos                  | En diseño |
| Objetivos y narrativa | Secuencia de los dos niveles y revelación     | Entorno, interfaz                       | En diseño |
| Persistencia          | Puntos de control y restauración              | Objetivos, estado del nivel             | En diseño |
| Presentación         | Interfaz, audio, animación y cámara          | Eventos de todos los sistemas           | En diseño |

## Especificación de sistemas

### Entrada y movimiento

**Objetivo:** controlar un personaje 3D con respuesta consistente.

**Entradas:** dirección de movimiento, orientación de cámara, postura y carrera. **Procesamiento:** aplicar velocidad por estado, resolver colisiones y emitir pasos. **Salidas:** posición, postura, ruido y animación.

**Estados:** quieto, caminar, agachado, correr e interacción. **Datos necesarios:** velocidades, dimensiones del personaje y distancias al suelo. **Dependencias:** un controlador de personaje y acciones de entrada configurables.

**Riesgo:** que la animación muestre protección cuando el volumen del personaje sigue expuesto. **Aceptación:** el volumen vulnerable se adapta a la postura y nunca atraviesa una cobertura al agacharse o incorporarse.

### Percepción e inteligencia artificial

**Entradas:** posición tridimensional de Iktan, postura, cobertura, eventos sonoros y objetivos activos. **Salidas:** estado enemigo, destino u orientación y señales de alerta.

**Visión del Nahual:** propuesta inicial de 12 m y cono horizontal de 80°. Se comprueba geometría entre el observador y puntos del torso/cabeza; basta un punto visible fuera de ocultamiento vegetal válido para acumular sospecha. Se confirma detección tras 0,8 s de visibilidad continua. Al ocultarse, la sospecha baja hasta cero en 1,5 s. El contacto físico activo causa captura inmediata.

**Audición:** un evento contiene origen, radio, categoría y momento. Se escucha si el receptor está dentro del radio; como simplificación inicial, las paredes no atenúan el sonido. Esta regla debe probarse para que las distracciones sean comprensibles en cada espacio.


|     |     |     |     |
| --- | --- | --- | --- |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |
|     |     |     |     |

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
