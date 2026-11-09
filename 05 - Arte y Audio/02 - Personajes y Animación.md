# Personajes y Animación

## Descripción de la sección

Documenta cómo deben verse y comportarse visualmente los personajes.

## Requisitos por personaje

| Personaje | Modelo/Sprite                                                                                                                  | Animaciones                                                        | VFX                                                        | Estado                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------ | ---------------------------------------------------------- | --------------------------------------------- |
| Iktan     | Niño voxel de silueta compacta, ropa tradicional blanca, sombrero de paja, lentes y tonos cálidos en el rostro.                | Reposo, caminar, correr, agacharse, apuntar, lanzar e interactuar. | Trayectoria de apuntado e impacto de piedra.               | Especificación visual.                        |
| Abbi      | Xoloitzcuintle espiritual y de calaverita de azucar.                                                                           | Seguir, esperar, orientar la mirada, alertar y despedirse.         | Brillo sutil en los ojos.                                  | Especificación visual.                        |
| El Nahual | Sombra animal de proporciones irregulares con rasgos de jaguar y lobo.                                                         | Acechar, investigar, perseguir, buscar y reaccionar al derrumbe.   | Polvo y fragmentos de piedra durante el derrumbe.          | Adaptación visual al encuentro de la Selva.   |
| El Diablo | Sombra alta sin rostro definido. La Figura Maliciosa sirve de referencia para proporciones alargadas, garras y acentos rojos.  | Barrer, orientar la mirada hacia un impacto y disolverse.          | Dos haces rojos y disolución al despejar el último vitral. | Adaptación visual al encuentro de la Iglesia. |

Leroy es una referencia visual para las amenazas de los dos niveles.

## Animaciones

### Movimiento

- **Idle:** Postura de reposo y movimiento sutil de cabeza.
- **Caminar y correr:** Balanceo angular de brazos y piernas con articulaciones procedimentales en Unity. La cadencia acompaña la velocidad real.
- **Agacharse:** Interpolar la altura de la cámara y la inclinación del torso mediante *lerp*. La postura debe leerse desde tercera persona y corresponder al estado de cobertura.
- **Saltar y caer:** Contemplar la caída como reacción cuando corresponda. El salto queda fuera de los movimientos requeridos para completar los niveles.

### Interacción

Preparar y lanzar la piedra, empujar la columna, activar la mesa, retirar tablas y tomar la fotografía tras derrotar al Diablo. Las animaciones de acción mantenida deben distinguir inicio, interrupción y confirmación.

### Combate

La presentación de los encuentros se centra en acecho, persecución, barrido de haces y respuestas del escenario. Iktan actúa mediante sigilo, distracciones e interacciones ambientales.

### Daño

La captura se comunica con una reacción breve y una transición a la pantalla de reintento. La posición del enemigo o el haz visible debe permitir identificar la causa.

### Muerte 

El Nahual queda oculto por el derrumbe. El Diablo se disuelve al entrar la luz del último vitral. La captura de Iktan devuelve al jugador al punto de control al reintentar.

## Convenciones

- Modelar en Blender y exportar los modelos con pivotes y escalas coherentes. Usar nombres descriptivos, como `CHR_Iktan`, `CHR_Abbi` y `CHR_Nahual`.
- Separar cabeza, torso y extremidades en articulaciones adecuadas al movimiento por bloques. Usar `VoxelWalkAnimator` o el componente equivalente para el balanceo procedimental.
- Comprobar que los pies acompañen el desplazamiento, que el cambio de postura sea suave y que la cámara conserve la lectura de la cobertura.

> **Navegación:** [[00 - Índice]] · ← [[01 - Dirección de Arte]] · [[03 - Entornos]] →
