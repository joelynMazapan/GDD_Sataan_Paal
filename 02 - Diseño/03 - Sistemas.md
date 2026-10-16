# Sistemas del Juego

## Descripción de la sección

Los sistemas son conjuntos de reglas y componentes que trabajan juntos: combate, inventario, IA, diálogo, progresión, economía, misiones, etc.

## Inventario de sistemas

| Sistema                | Propósito                                                                                                   | Dependencias                                          | Estado    |
| ---------------------- | ----------------------------------------------------------------------------------------------------------- | ----------------------------------------------------- | --------- |
| Sigilo y Detección     | Gestionar cuándo el jugador es invisible, cuándo hace ruido y cómo reaccionan los enemigos a su presencia.  | Sistema de Movimiento del Jugador, Gestor de Entorno. | En diseño |
| Distracción            | Permitir al jugador alterar las rutas de los enemigos usando objetos arrojadizos.                           | Sigilo y Detección.                                   | En diseño |
| Movimiento del Jugador | Controlar el desplazamiento, la velocidad y el estado de Iktan.                                             | Entradas del Usuario.                                 | En diseño |
| Pánico / Cordura       | Limitar la visión y movilidad del jugador en zonas de alto estrés, obligándolo a interactuar con Abbi.      | Movimiento del Jugador.                               | En diseño |
| Gestor de Entorno      | Controlar las interacciones que permiten derrotar a los jefes usando elementos del escenario.               | Distracción, Movimiento del Jefe.                     | En diseño |
| Progresión y Guardado  | Gestionar la recolección de ofrendas y el avance de nivel a través de la construcción del Altar de Muertos. | Ninguna                                               | En diseño |

## Plantilla de sistema

### Sigilo y Detección

**Objetivo:** Determinar de forma justa y predecible si los enemigos pueden ver o escuchar a Iktan.

**Entradas:** Posición de Iktan, estado de movimiento de Iktan (agachado/corriendo), estado de iluminación/cobertura, radio de sonido emitido.

**Procesamiento / reglas:**
- Si Iktan está dentro del Cono de Visión enemigo y NO está detrás de una cobertura, es detectado.
- Si Iktan emite un sonido dentro de la _Esfera Auditiva_ del enemigo, el enemigo entra en estado de Alerta.

**Salidas:** Cambio de estado de la IA enemiga. Activación de señales visuales.

**Estados posibles:**
- _Patrulla:_ Movimiento en ruta predefinida.
- _Investigación:_ Se desplaza hacia el origen de un sonido.
- _Persecución:_ Sigue directamente la posición del jugador.

**Dependencias:** Sistema de Movimiento del Jugador.

**Interacciones:** Si el Sistema de Distracción genera un sonido más fuerte, la IA prioriza ese nuevo sonido.

**Datos que necesita:** Coordenadas (X,Y) del jugador y del enemigo, estado de ruido del jugador.

**Datos que genera:** Estado actual del enemigo (`enum: Patrulla, Investigacion, Persecucion`).

**Riesgos:** Que la detección sea inconsistente.

**Criterios de aceptación:** El jugador solo es detectado si está visiblemente dentro del cono o hace ruido en el radio auditivo. La IA vuelve a su patrulla tras 5 segundos de no ver/escuchar al jugador.

### Distracción

**Objetivo:** Proveer una herramienta táctica para alejar a los enemigos de zonas bloqueadas.
**Entradas:** _Input_ del jugador , posición objetivo.

**Procesamiento / reglas:**
- Al impactar el suelo, se genera un _Trigger_ esférico invisible que simula el sonido.
- Si este Trigger colisiona con el área auditiva de un enemigo, se envía la coordenada de impacto al Sistema de IA.

**Salidas:** Alteración en la ruta del enemigo más cercano.

**Estados posibles:** Cargando lanzamiento, Roca en vuelo, Impacto/Sonido activo, Enfriamiento.

**Dependencias:** Sigilo y Detección.

**Interacciones:** Invalida temporalmente la ruta de patrulla del enemigo. Si golpea una Trampa de Entorno, activa el Sistema de Entorno.

**Datos que necesita:** Coordenadas de impacto, radio de sonido predefinido de la roca.

**Datos que genera:** Coordenadas del punto de interés para la IA enemiga.

**Riesgos:** Que el jugador abuse de la mecánica rompiendo el flujo del juego.

**Criterios de aceptación:** Las rocas siempre atraen al enemigo más cercano al punto de impacto, nunca directamente al jugador, con un tiempo de recarga funcional.

### Cordura

**Objetivo:** Aumentar la tensión limitando las capacidades del jugador y forzando la interacción narrativa con Abbi.

**Entradas:** Tiempo de exposición en zonas de estrés, _Input_ del jugador (interactuar con Abbi).

**Procesamiento / reglas:**
- Mientras Iktan esté en una "Zona Oscura", el medidor de Pánico sube constantemente.
- Al llegar al 50%, la velocidad de movimiento baja. Al 100%, Iktan no puede moverse (Game Over virtual por detección inminente).
- Mantener el botón de interacción con Abbi en una "Zona Segura" reduce el Pánico a cero.

**Salidas:** Oscurecimiento gradual de la interfaz/cámara (Vignette), reducción de velocidad.

**Estados posibles:** Seguro (0% Pánico), Estresado (50% Pánico), Paralizado (100% Pánico), Consuelo (interactuando con Abbi).

**Dependencias:** Sistema de Movimiento del Jugador.
 
**Interacciones:** Detiene el movimiento del jugador si llega al máximo.

**Datos que necesita:** Variable _float_ de Pánico (0 a 100), estado de posición (Zona Oscura vs. Zona Segura).

**Datos que genera:** Multiplicador de velocidad de movimiento, opacidad de la interfaz de oscurecimiento.

 **Riesgos:** Que la subida de Pánico sea tan rápida que el nivel se vuelva injusto o imposible de superar.

**Criterios de aceptación:** El jugador siente la urgencia visual de buscar cobertura y la recompensa calmante al interactuar con Abbi.
## Relaciones entre sistemas

Describe qué sistemas dependen de otros y qué información intercambian.

El núcleo del juego recae en la constante comunicación entre el Sistema de Movimiento del Jugador y el Sistema de Sigilo y Detección . La posición y las acciones del jugador (correr, agacharse) envían datos constantemente a la IA. A su vez, el jugador utiliza el Sistema de Distracción (Rocas) para inyectar información falsa a la IA, alterando temporalmente sus decisiones.

Durante los enfrentamientos contra jefes, la IA interactúa con el Gestor de Entorno; el jugador no daña al enemigo directamente, sino que coordina el Movimiento y la Distracción para que la IA enemiga colisione con los activadores del Entorno, resolviendo la situación y enviando una señal al sistema de Progresión y Guardado para avanzar de nivel. En las zonas de alto estrés, el sistema de Pánico / Cordura actúa como un filtro sobre el Movimiento, alterando las variables físicas (velocidad) y visuales de la experiencia.

> **Navegación:** [[00 - Índice]] · ← [[02 - Mecánicas]] · [[04 - Controles]] →
