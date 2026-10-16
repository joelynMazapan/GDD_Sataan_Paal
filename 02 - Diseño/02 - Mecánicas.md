# Mecánicas

## Descripción de la sección

Una mecánica es una regla o interacción mediante la cual el jugador puede actuar dentro del sistema del juego.

Documenta cada mecánica con suficiente detalle para que otro integrante pueda implementarla.

## Plantilla de mecánica

### Nombre de la mecánica

**Propósito:**  
¿Qué aporta a la experiencia?

**Activación:**  
¿Qué debe hacer el jugador?

**Reglas:**  
¿Qué puede y qué no puede ocurrir?

**Entrada:**  
¿Qué botón, gesto o acción la activa?

**Estado inicial:**

**Estado final:**

**Recursos utilizados:**

**Recompensa:**

**Penalización:**

**Interacciones con otras mecánicas:**

**Casos límite:**  
¿Qué ocurre en situaciones poco comunes?

## Mecánicas principales

#### Mecánica 01: Sigilo y Esconderse

**Propósito:** Permite al jugador evadir el campo de visión de los enemigos y reducir su nivel de ruido para avanzar por los niveles sin ser detectado. Aporta la tensión principal de la experiencia de juego.

**Activación:** El jugador debe mantener presionado (o alternar) el botón de sigilo mientras se mueve, preferentemente ubicando a Iktan detrás de objetos del entorno (cajas, muros, lápidas).

**Reglas:**

- Al activarse, la velocidad de movimiento de Iktan se reduce al 50%.
- El radio de ruido de los pasos del jugador se reduce a 0 (silencio total).
- Si Iktan está agachado detrás de un objeto con la etiqueta `Cobertura` y un enemigo proyecta su cono de visión sobre ese objeto, Iktan NO es detectado.
- Si Iktan está agachado pero NO está detrás de una cobertura y el cono de visión lo toca, es detectado inmediatamente.

**Entrada:** Botón asignado (Ej: Mantener `Ctrl` en teclado o `Gatillo L2` en control).

**Estado inicial:** Iktan camina de pie, generando un radio de sonido pequeño y siendo completamente visible a los conos de luz enemiga.

**Estado final:** Iktan está agachado, silenciado y protegido de la visión si hay un obstáculo entre él y el enemigo.

**Recursos utilizados:** Ninguno.

**Recompensa:** Superar zonas plagadas de enemigos sin iniciar una persecución.

**Penalización:** Lentitud de movimiento; si el jugador calcula mal el tiempo, el enemigo lo alcanzará fácilmente.

**Interacciones con otras mecánicas:** No se puede correr mientras se está en sigilo. Al lanzar una roca desde sigilo, Iktan se levantará brevemente durante la animación de lanzamiento.

**Casos límite:** ¿Qué ocurre si un enemigo en su ruta de patrulla camina físicamente hacia la misma cobertura donde está Iktan? El contacto físico (colisión de hitboxes) fuerza la detección inmediata, ignorando que Iktan esté agachado.
#### Mecánica 02: Lanzamiento de Rocas 
**Propósito:** Darle al jugador una herramienta táctica para manipular la inteligencia artificial de los enemigos, obligándolos a abandonar sus rutas de patrullaje para despejar un camino.

**Activación:** El jugador apunta con un indicador visual y lanza la roca hacia un punto específico del mapa.

**Reglas:**

- Las rocas tienen un radio de sonido invisible al impactar (ej. 5 metros).
- Cualquier enemigo cuyo "oído" sea tocado por el radio de sonido de la roca, cambiará su estado de `Patrulla` a `Investigación`.
- El enemigo caminará exactamente al punto de impacto de la roca, mirará a su alrededor por 3 segundos, y luego regresará a su ruta original.
- Munición infinita, pero con un tiempo de recarga de 2 segundos entre lanzamientos para evitar spam.

**Entrada:** Apuntar + Lanzar.

**Estado inicial:** El enemigo sigue su ruta de patrulla predefinida.

**Estado final:** El enemigo se encuentra fuera de su ruta, investigando el ruido, dejando un punto ciego para que Iktan avance.

**Recursos utilizados:** Tiempo.

**Recompensa:** Crear aberturas seguras en zonas donde los conos de visión enemigos bloquean el 100% del pasillo.

**Penalización:** Si el jugador lanza la roca demasiado cerca de sí mismo, el radio de sonido del impacto atraerá al enemigo directamente hacia la posición de Iktan, provocando su detección.

**Interacciones con otras mecánicas:** Es la herramienta principal para activar las Trampas del Entorn.

**Casos límite:** ¿Qué ocurre si el jugador lanza una segunda roca mientras el enemigo investiga la primera? La IA cancela la primera investigación, gira y se dirige inmediatamente al punto de impacto de la segunda roca.
## Mecánicas secundarias

Lista de mecánicas que complementan la experiencia pero no constituyen el núcleo del sigilo:

1. **Caminar :**
    
    - _Descripción:_ Desplazamiento normal con el joystick izquierdo o WASD. Genera un ruido muy leve. Sirve para recorrer zonas sin enemigos rápido y recolectar pistas (notas, vendas).

2. **Correr y Esquivar:**
    
    - _Descripción:_ Al presionar un botón, Iktan da un acelerón o una voltereta. Es vital para las secuencias de persecución, pero fuera de ellas genera un radio de sonido masivo que alerta a todos los enemigos de la sala.
    
3. **Abrazar a Abbi :**
    
    - _Descripción:_ En niveles de alta tensión (como el Capítulo 4), una neblina oscurece gradualmente la pantalla del jugador (medidor de pánico). El jugador debe buscar una cobertura segura y mantener presionado un botón para interactuar con Abbi. Esto reproduce una animación de consuelo que limpia la pantalla y restablece la visión.
    
4. **Recolectar y Colocar Ofrendas :**
    
    - _Descripción:_ Mecánica narrativa. Al final de cada nivel, el jugador interactúa con el objeto brillante (premio). Esto teletransporta al jugador brevemente frente al Altar de Muertos espectral, donde presiona un botón para colocar el objeto, guardando su progreso.


> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
