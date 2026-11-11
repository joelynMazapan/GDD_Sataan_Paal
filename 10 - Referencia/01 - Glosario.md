# Glosario

Centraliza términos técnicos, de diseño y propios del universo del videojuego. Las definiciones narrativas incluyen detalles del desenlace.

## Historia y mundo

| Término | Definición |
| --- | --- |
| **Saatan Paal** | Nombre del videojuego y del proyecto. |
| **Iktan** | Protagonista jugable que explora el entorno, se oculta y resuelve obstáculos. |
| **Abbi** | Xoloitzcuintle espiritual de calaverita de azúcar que acompaña a Iktan. Señala rutas y peligros mediante su mirada y postura. |
| **La Selva Hostil** | Primer nivel. Incluye el sendero, las ruinas y el encuentro con el Nahual. |
| **Nahual** | Amenaza de la Selva. Acecha, investiga sonidos y puede capturar a Iktan por contacto. Se derrota mediante el derrumbe. |
| **Plato de molletes** | Objeto que Iktan recoge tras derrotar al Nahual y coloca en la mesa espectral. |
| **Mesa espectral** | Elemento de la Selva donde Iktan deposita el plato de molletes. Activa el recuerdo familiar que abre el paso a la Iglesia. |
| **La Iglesia** | Segundo nivel. Incluye el atrio, la nave, el enfrentamiento con el Diablo y el desenlace. |
| **Diablo** | Amenaza de la Iglesia. Barre la nave con dos haces rojos y se disuelve con la luz del último vitral. |
| **Altar de Día de Muertos** | Forma que toma el pedestal después de derrotar al Diablo. Contiene la fotografía de Iktan. |
| **Fotografía de Iktan** | Objeto que se obtiene del altar después de la derrota del Diablo. Tomarlo activa la revelación. |
| **Revelación** | Escena en que Iktan comprende que falleció durante su secuestro. Al concluir, se habilita el sendero final. |
| **Sendero de cempasúchil** | Ruta de flores y pétalos que guía a Iktan hacia la despedida y el cierre. |

## Jugabilidad y percepción

| Término | Definición |
| --- | --- |
| **Mecánica** | Regla o interacción mediante la cual el jugador actúa, como agacharse o lanzar una piedra. |
| **Sistema** | Conjunto de componentes y reglas que trabajan juntos, como la percepción enemiga. |
| **Bucle principal** | Secuencia recurrente de observar, elegir cobertura, distraer cuando conviene, avanzar e interactuar. |
| **Sigilo** | Forma de avanzar reduciendo la exposición visual y el ruido que delata a Iktan. |
| **Cobertura** | Elemento que protege a Iktan de la visión o de los haces. La hierba alta lo oculta en la Selva cuando está agachado. |
| **Línea de visión** | Trayecto entre la amenaza e Iktan que se comprueba para determinar si hay un obstáculo interpuesto. |
| **Oclusión** | Bloqueo de la visión o del haz por una cobertura opaca. |
| **Piedras de distracción** | Única herramienta de distracción intencional. El impacto genera ruido en el punto real de colisión. |
| **Colisión** | Contacto de un objeto con la geometría u otro cuerpo. En las piedras determina dónde ocurre el impacto. |
| **Recarga** | Intervalo entre lanzamientos durante el que la piedra aparece como no disponible. |
| **Ventana de distracción** | Tiempo durante el que la amenaza presta atención al impacto, lo que puede permitir cruzar o interactuar. |
| **Sospecha** | Estado en que el Nahual muestra indicios de haber percibido a Iktan antes de confirmar la detección. |
| **Investigación** | Respuesta a un impacto audible. El Nahual se acerca a su origen y el Diablo orienta los haces hacia él. |
| **Persecución** | Respuesta del Nahual al confirmar que ha visto a Iktan. |
| **Barrido** | Movimiento de los haces del Diablo por la nave. Los haces siguen activos durante el giro. |
| **Captura** | Derrota causada por el contacto con el Nahual o por un haz que alcanza a Iktan sin cobertura interpuesta. |
| **Interacción mantenida** | Acción que requiere sostener la entrada durante un intervalo, como derribar la columna o retirar tablas. |
| **Vitral** | Ventana cubierta por tablas en la nave. La luz del tercer vitral despejado derrota al Diablo. |

## Experiencia y guardado

| Término | Definición |
| --- | --- |
| **UX** | Experiencia del jugador al aprender, interpretar y usar el juego. |
| **UI** | Interfaz de usuario. Incluye menús, avisos, iconos e indicaciones contextuales. |
| **HUD** | Información visible durante la partida, como el objetivo, el estado de las piedras y el contador de vitrales. |
| **Viñeta** | Efecto discreto en los bordes de la pantalla que acompaña una señal de ocultamiento o alerta. |
| **Retroalimentación** | Respuesta visual o sonora que comunica el resultado de una acción o un cambio de estado. |
| **Punto de control** | Estado que el juego guarda y puede restaurar al reintentar o continuar. |
| **S1–S4** | Puntos de control de la Selva. Inicio, acceso a las ruinas, derrota del Nahual y recuerdo de la mesa completado. |
| **I1** | Punto de control previo a la nave. Al restaurarlo, los tres vitrales están cubiertos y el Diablo sigue activo. |
| **I2** | Punto de control posterior a la derrota del Diablo. Se actualiza tras obtener la fotografía y completar la revelación. |
| **Hito de progreso** | Hecho confirmado que se conserva en el guardado y permite reconstruir el escenario, como la derrota del Diablo. |
| **Persistencia** | Conservación del progreso y las preferencias entre sesiones. |

## Arte, tecnología y producción

| Término | Definición |
| --- | --- |
| **Voxel Art 3D** | Estilo visual construido con volúmenes de apariencia cúbica. Los modelos del proyecto se crean en Blender. |
| **Cámara en tercera persona** | Perspectiva externa que muestra a Iktan y parte de su entorno mientras el jugador se mueve. |
| **Cinemachine** | Paquete de Unity utilizado para el seguimiento, encuadre y transiciones de cámara. |
| **Input System** | Paquete de Unity que organiza las acciones de teclado y ratón para partida y menús. |
| **URP** | Universal Render Pipeline, canalización de Unity que procesa la iluminación, los materiales y los efectos. |
| **Prefab** | Objeto reutilizable de Unity que puede colocarse en distintas escenas con sus componentes y ajustes. |
| **IA** | Inteligencia artificial. Conjunto de reglas que gobierna la percepción y las respuestas del Nahual y el Diablo. |
| **JSON** | Formato de texto estructurado propuesto para almacenar el guardado local. |
| **GDD** | Documento de Diseño de Videojuego. Reúne las decisiones de diseño, narrativa, arte, experiencia y tecnología. |
| **MVP** | Producto Mínimo Viable. Alcance mínimo para demostrar que el bucle principal funciona. |
| **Vertical Slice** | Muestra pequeña pero representativa de la experiencia y del nivel de calidad previsto. |
| **Criterio de aceptación** | Condición verificable que permite determinar si una característica cumple lo especificado. |
| **Demo web** | Versión de demostración prevista para ejecutarse en navegador y distribuirse en itch.io. |

## Convenciones de nombres

- Usar **Saatan Paal**, tal como figura en la ficha del proyecto.
- Escribir **Iktan** y **Abbi** en todas las notas, interfaces y guiones.
- Usar **La Selva Hostil** y **La Iglesia** como nombres de los niveles, y **Nahual** y **Diablo** para las amenazas.
- Distinguir **mesa espectral**, que recibe el plato de molletes en la Selva, de **Altar de Día de Muertos**, donde aparece la fotografía en la Iglesia.
- Usar **piedras** para la herramienta de distracción y **punto de control** para el estado que se restaura al continuar o reintentar.

> **Navegación:** [[00 - Índice]] · ← [[04 - Criterios de Aceptación]] · [[02 - Referencias e Inspiración]] →
