

## Criterios de Calidad

### Descripción de la sección

Define qué significa que una característica esté correctamente terminada.

El diseño de _Saatan Historia_ se revisa junto con el control, la interfaz y la persistencia. El jugador debe entender en todo momento cómo se mueve, cuándo hacer ruido y dónde esconderse; los avisos de peligro (aros de ruido, haces de luz, patrullas) deben preceder al daño, y cada recompensa recogida debe reflejarse de inmediato en el altar de ofrenda.

|Aspecto|Comprobación|
|---|---|
|Preparación y guía en tutorial|El jugador aprende los controles en la **Sala de controles** (9 placas: movimiento, cuclillas, piedra, trompo, interacción, sigilo, ruido y ofrenda) y los practica en la **Zona de práctica** (7 salas con carteles numerados: `1 MOVERSE`, `2 AGACHARSE Y RUIDO`, `3 ESCONDERSE`, `4 LANZAR PIEDRAS`, `5 LANZAR TROMPOS`, `6 VITRALES` y `7 OFRENDA Y SALIDA`). Cada sala se recorre siguiendo el camino de cempasúchil hasta la puerta de salida.|
|Control y cámara|Iktan responde a `W` `A` `S` `D` o flechas y respeta los obstáculos (muros, lápidas, troncos y árboles); mantener `Ctrl` o `C` lo pone en cuclillas, más lento y casi sin ruido, y soltarlo regresa a la marcha normal sin saltos. La cámara (`SeguirCamara`) lo sigue de forma suave y nunca lo deja fuera de encuadre. `Controlador` no atraviesa colisiones.|
|Sigilo y ruido|El radio de ruido es legible y coherente: **5,5 m** corriendo y **2,4 m** en cuclillas (aros `rojo` y `amarillo` de la práctica). Las piedras (`clic izquierdo`) y los trompos (`clic derecho`) atraen a los enemigos al punto de impacto; la hierba alta, los troncos caídos y las lápidas rompen la línea de visión.|
|Enemigos y jefes|Solo hay dos enemigos: el **Nahual** y el **Diablo**. Nahual (selva): patrulla las ramas por waypoints, salta al origen del ruido y queda bajo el techo de roca al caer la columna agrietada. Diablo (iglesia): barre el suelo con **2 haces de luz roja**, desvía la mirada hacia el ruido de piedras y trompos y recibe daño al derribar cada vitral. Ambos reaccionan al ruido según el radio de oído (**5,5 m** corriendo, **2,4 m** en cuclillas) y anuncian su alerta o ataque antes de causar daño.|
|Niveles y progresión|El juego se completa de inicio a fin en tres escenarios: **Práctica** (Sala de controles y Zona de práctica), **Selva** e **Iglesia**. Cada uno tiene inicio y salida propios, y la transición entre ellos es coherente (Práctica → Selva → Iglesia). En la selva la salida solo se abre al recoger la recompensa (los trompos de gatitos) y los árboles de la puerta se apartan; la iglesia termina al derribar los vitrales y vencer al Diablo, con el mensaje final.|
|Altar y narrativa|Cada recompensa recogida agrega un piso al altar de muertos (en la selva, los trompos de gatitos con papel picado) y se refleja de inmediato. En el atrio de la iglesia el altar aparece con las ofrendas reunidas; la revelación (fotografía de Iktan con lirios blancos) y el mensaje final sobre el secuestro se muestran completos, legibles y con tono respetuoso.|
|Escenarios y rendimiento|Cada escenario se genera desde su mapa PNG con los constructores del editor (`ConstructorSelva`, `ConstructorIglesia`, `ConstructorTutorial`) sin errores ni objetos duplicados; el piso y la decoración se combinan en pocas mallas y el límite invisible bloquea el paso. Rendimiento estable de **60 FPS** en Full HD en una PC de gama media y sin parpadeos de iluminación.|
|Interfaz y legibilidad|Textos en español con acentos y `ñ` correctos; placas y carteles legibles desde la cámara de juego; contraste suficiente en la niebla verde de la selva y la penumbra de la iglesia; las llamas (`LlamaViva`) parpadean sin afectar el rendimiento.|
|Guardado|El progreso (nivel alcanzado y recompensas del altar) se conserva al cerrar el juego y se restaura al continuar sin duplicar recompensas.|
|Estabilidad y compilación|El juego compila y se ejecuta en Unity `6000.6.4f1` sin errores en la consola; los materiales, mallas y scripts de cada escenario cargan completos (sin objetos rosas ni componentes faltantes). Las tres escenas están en `Build Settings` y el paso de Práctica a Selva y a Iglesia ocurre sin cierres ni objetos duplicados. La compilación para PC se abre y se juega de inicio a fin.|


> **Navegación:** [[00 - Índice]] · ← [[05 - Gestión de Cambios]] · [[02 - Pruebas]] →