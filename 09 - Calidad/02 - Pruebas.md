# Pruebas

### Descripción de la sección

Define cómo se comprobará que el videojuego funciona como fue diseñado.

El proyecto se verifica con pruebas manuales en el editor de Unity (`6000.6.4f1`, Play Mode) sobre la **Zona de práctica**, la **Selva** y la **Iglesia**, y con la revisión del código de los constructores de escenarios (`ConstructorTutorial`, `ConstructorSelva` y `ConstructorIglesia`) contra sus mapas PNG. Cada comprobación se registra como un caso de prueba con su resultado y su estado.

## Tipos de prueba

### Pruebas funcionales

Comprueban que una característica haga lo que debe: movimiento y cuclillas de Iktan (`Controlador`), colisiones con muros, lápidas y troncos, lanzamiento de piedras y trompos, hierba alta como escondite, derribo de tablas en los vitrales, caída del techo de roca y apertura de la salida de la selva.

### Pruebas de integración

Comprueban que varios sistemas funcionen correctamente juntos: ruido del jugador con la reacción del Nahual y del Diablo, cámara (`SeguirCamara`) con el movimiento, llamas (`LlamaViva`) con la iluminación de la escena, constructores de escenarios con sus mapas PNG y el paso de Práctica a Selva y a Iglesia.

### Pruebas de usabilidad

Comprueban si los jugadores entienden y pueden utilizar el sistema: lectura de las 9 placas de la Sala de controles y de los 7 carteles de la Zona de práctica, comprensión de los aros de ruido (`CORRIENDO` y `AGACHADO`) y claridad de los textos desde la cámara de juego. Se prueban con compañeros que no conocen el juego.

### Pruebas de rendimiento

Comprueban FPS, memoria, tiempos de carga y estabilidad: **60 FPS** en Full HD, escenarios de piso y decoración combinados en pocas mallas, iluminación sin parpadeos y cambio de escena sin cierres.

## Verificación de la revisión (`main` @ `commit`, 10 de noviembre de 2026)

Esta revisión documental contrasta las cifras, teclas y etiquetas del diseño directamente contra el código de los constructores y los mapas de los escenarios:

- **Escenarios (`ConstructorTutorial.cs`, `ConstructorSelva.cs`, `ConstructorIglesia.cs`):** verificada la generación desde `sala_controles.png`, `practica.png`, `selva_detallada.png` e `iglesia_detallada.png`, con límite invisible por colisión, piso y decoración combinados en mallas y materiales guardados en `Assets/Niveles`.
- **Tutorial:** verificadas las **9 placas** de la Sala de controles y los **7 carteles** de la Zona de práctica (`1 MOVERSE`, `2 AGACHARSE Y RUIDO`, `3 ESCONDERSE`, `4 LANZAR PIEDRAS`, `5 LANZAR TROMPOS`, `6 VITRALES`, `7 OFRENDA Y SALIDA`), y las constantes de control (`T_MOVER`, `T_AGACHAR`, `T_PIEDRA`, `T_TROMPO`, `T_INTERACTUAR`).
- **Ruido:** verificados los radios de oído `RADIO_CORRIENDO = 5,5 m` y `RADIO_AGACHADO = 2,4 m`, dibujados como aros en el suelo de la Zona de práctica.
- **Selva:** verificados el anillo de ruinas con entradas al norte y al sur, la columna agrietada, el techo de roca (`ALTURA_TECHO = 4,6 m`), los trompos de gatitos y el grupo `Puerta_Arboles` que bloquea la salida.
- **Iglesia:** verificados la alfombra roja, los vitrales con tablas, los candelabros y el altar.

## Casos de prueba

### CP-01 · Movimiento y colisiones

**Objetivo:** Comprobar que Iktan se mueve con el teclado y respeta los obstáculos.

**Precondiciones:** Zona de práctica abierta en Play Mode.

**Pasos:**

1. Presionar `W` `A` `S` `D` y luego las flechas.
2. Caminar contra un muro, una lápida y un tronco caído.
3. Soltar las teclas.

**Resultado esperado:** Iktan se mueve en las cuatro direcciones, no atraviesa muros, lápidas ni troncos y se detiene al soltar las teclas. La cámara lo sigue sin saltos.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-02 · Cuclillas

**Objetivo:** Comprobar que ir en cuclillas es más lento y menos ruidoso.

**Precondiciones:** Sala 2 de la Zona de práctica (`AGACHARSE Y RUIDO`).

**Pasos:**

1. Mantener `Ctrl` o `C` y caminar.
2. Soltar la tecla.
3. Comparar la velocidad en ambos modos.

**Resultado esperado:** En cuclillas Iktan avanza más lento y la esfera se aplasta; al soltar regresa a la marcha normal sin saltos.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-03 · Radio de ruido

**Objetivo:** Comprobar que los aros de ruido coinciden con lo que oye el enemigo.

**Precondiciones:** Marcador de enemigo con aros en la sala 2.

**Pasos:**

1. Correr hasta el borde del aro rojo (`5,5 m`).
2. Repetir en cuclillas hasta el aro amarillo (`2,4 m`).
3. Observar la reacción del enemigo en cada caso.

**Resultado esperado:** Corriendo, el enemigo reacciona al entrar en el aro rojo; en cuclillas, solo al entrar en el aro amarillo.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-04 · Esconderse

**Objetivo:** Comprobar que la hierba alta, los troncos y las lápidas rompen la línea de visión.

**Precondiciones:** Sala 3 de la Zona de práctica (`ESCONDERSE`).

**Pasos:**

1. Entrar en la hierba alta en cuclillas frente al enemigo.
2. Colocarse detrás de un tronco caído y de una lápida.
3. Salir de la cobertura.

**Resultado esperado:** El enemigo no detecta a Iktan mientras está cubierto y lo detecta al salir.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-05 · Lanzar una piedra

**Objetivo:** Comprobar que la piedra distrae al enemigo.

**Precondiciones:** Sala 4 de la Zona de práctica (`LANZAR PIEDRAS`), con los blancos visibles.

**Pasos:**

1. Apuntar con el ratón a un blanco y presionar `clic izquierdo`.
2. Observar al enemigo.
3. Cruzar la sala por su espalda.

**Resultado esperado:** La piedra cae en el blanco, el enemigo se dirige al ruido y Iktan cruza sin ser detectado.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-07 · Nahual y techo de roca

**Objetivo:** Comprobar la trampa de la columna agrietada en la Selva.

**Precondiciones:** Selva abierta; Nahual en su rama; Iktan cerca de las ruinas.

**Pasos:**

1. Lanzar una piedra al centro de las ruinas para atraer al Nahual.
2. Esperar a que quede debajo del techo de roca.
3. Lanzar una piedra grande a la base de la columna.

**Resultado esperado:** El Nahual salta al origen del ruido; al golpear la columna cae el techo y lo aplasta. La salida y la recompensa quedan accesibles.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-08 · Recompensa y salida de la Selva

**Objetivo:** Comprobar que la salida se abre solo al recoger los trompos de gatitos.

**Precondiciones:** Nahual derrotado; grupo `Puerta_Arboles` cerrado.

**Pasos:**

1. Intentar cruzar la puerta de árboles antes de recoger los trompos.
2. Recoger los trompos de gatitos.
3. Cruzar la puerta.

**Resultado esperado:** Antes de la recompensa la puerta bloquea el paso; después los árboles se apartan, el altar suma su piso y Iktan avanza a la Iglesia.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-09 · Diablo y vitrales

**Objetivo:** Comprobar la pelea final de la Iglesia.

**Precondiciones:** Iglesia abierta; Diablo en el centro; tablas puestas en los vitrales.

**Pasos:**

1. Lanzar piedras y trompos a los rincones para desviar los haces de luz roja.
2. Acercarse a un vitral y mantener `E` para derribar sus tablas.
3. Repetir hasta destapar el último vitral.

**Resultado esperado:** Los haces rojos siguen el ruido; cada vitral destapado hace daño al Diablo; si un haz toca a Iktan se pierde la partida; al abrir el último vitral el Diablo desaparece y aparece el mensaje final.

**Resultado obtenido:**

**Estado:** Pendiente

### CP-10 · Rendimiento y cambio de escena

**Objetivo:** Comprobar FPS, estabilidad y el flujo completo del juego.

**Precondiciones:** Compilación para PC o Play Mode con la ventana Game en Full HD.

**Pasos:**

1. Activar _Stats_ en la ventana Game y recorrer cada escenario.
2. Pasar de Práctica a Selva y a Iglesia.
3. Revisar la consola de Unity.

**Resultado esperado:** Al menos 60 FPS estables, sin errores en la consola, sin objetos duplicados al cambiar de escena y sin parpadeos de iluminación.

**Resultado obtenido:**

**Estado:** Pendiente

## Revisión de entrada pendiente

Con los carteles y las placas de los controles ya integrados en la Sala de controles y la Zona de práctica, la revisión pendiente de experiencia de entrada se centra en decidir y verificar las asignaciones definitivas de mando para las interacciones que hoy emplean `clic izquierdo` (piedra), `clic derecho` (trompo) y `E` (interactuar), y en confirmar que los textos de las placas coinciden con los controles reales del juego.

> **Navegación:** [[00 - Índice]] · ← [[01 - Criterios de Calidad]] · [[03 - Bugs y Seguimiento]] →
