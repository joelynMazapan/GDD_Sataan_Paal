# Mecánicas


### 01. Movimiento, sigilo y cobertura

**Propósito:** permitir desplazamientos tácticos comprensibles en un escenario 3D.

**Activación y entrada:** WASD mueve respecto a la orientación horizontal de la cámara; Ctrl alterna agacharse y Mayús permite correr mientras se mantiene pulsado.

**Estado inicial:** Iktan está de pie o agachado, con control disponible. **Estado final:** alcanza una nueva posición o cambia de postura.

**Reglas:**

* Velocidades propuestas: caminar 2,5 m/s; agachado 1,25 m/s; correr 4 m/s.
* Radios de ruido de pasos: 3 m al caminar, 1 m agachado y 8 m al correr. Se emite un evento por paso, no cada fotograma.
* La hierba alta oculta visualmente al personaje agachado que se encuentre dentro de su volumen. Caminar de pie en ella no activa ese beneficio.
* Troncos, muros y mobiliario sólido bloquean visión mediante geometría; una etiqueta de cobertura por sí sola no concede invisibilidad.
* En la Iglesia solo las coberturas opacas detienen los haces. La decoración vegetal no garantiza protección frente a ellos.
* Correr desde la postura agachada exige espacio para ponerse de pie; al soltar Mayús se vuelve a caminar de pie. Si falta altura, Iktan permanece agachado.
* El lanzamiento conserva la postura y no levanta automáticamente a Iktan.
* El recorrido se resuelve caminando, corriendo o agachándose; no requiere salto, voltereta ni esquiva.

**Recursos:** tiempo y posición. **Recompensa:** avanzar sin ser visto. **Penalización:** una mala posición permite investigación, persecución o captura.

**Interacciones:** determina la emisión de ruido, la validez de las coberturas y el acceso a objetivos.

**Casos límite:** no se puede atravesar el escenario con el cambio de postura. El contacto con el Nahual en estado activo causa captura incluso dentro de la hierba. Abbi no bloquea físicamente a Iktan.

### 02. Apuntar y lanzar piedras

**Propósito:** crear una ventana breve para cruzar o preparar una interacción.

**Activación y entrada:** mantener botón derecho muestra la trayectoria; pulsar botón izquierdo lanza. Soltar el derecho sin lanzar cancela.

**Estado inicial:** piedra disponible y recarga terminada. **Estado final:** impacto sonoro y recarga de 2 s desde el lanzamiento.

**Reglas:** alcance máximo propuesto de 12 m; radio de impacto sonoro de 8 m. El Nahual investiga un impacto audible durante 5 s tras llegar. El Diablo gira hacia el impacto y mantiene la mirada 5 s después de completar el giro. El movimiento y el giro se respetan: la distracción no teletransporta al enemigo.

Las piedras son ilimitadas, no requieren recolección y no causan daño ni aturdimiento. Su trayectoria colisiona con paredes y obstáculos. El sonido se genera en el primer impacto real, aunque la predicción del apuntado quedara desactualizada. La piedra no activa la columna ni retira tablas.

**Recursos:** recarga y tiempo de exposición. **Recompensa:** desviar temporalmente la amenaza. **Penalización:** un impacto junto a Iktan puede atraerla a su cobertura.

**Interacciones:** el avistamiento confirmado tiene prioridad sobre cualquier sonido. Un nuevo impacto audible actualiza el punto de interés; una vez alcanzado ese punto o completado el giro, comienza de nuevo la atención de 5 s. El giro respeta su velocidad máxima: lanzar otra piedra no crea una abertura instantánea.

**Casos límite:** una pared cercana interrumpe el tiro; la vista previa marca la colisión. Un impacto sobre el enemigo genera sonido en el punto de contacto sin alterar la prioridad de persecución ni infligir daño. Un segundo lanzamiento es rechazado durante la recarga.

### 03. Derribar la columna de las ruinas

**Propósito:** cerrar la Selva utilizando posición, señuelo y escenario.

**Activación y entrada:** atraer al Nahual bajo el techo marcado por grietas; acercarse al lateral accesible de la columna y mantener E durante 2 s.

**Estado inicial:** columna intacta y Nahual dentro del volumen de la trampa. **Estado final:** derrumbe completado, Nahual neutralizado y mesa espectral disponible.

**Reglas:** la posición de interacción está fuera de la zona del derrumbe. El juego muestra «Derribar columna» solo al cumplir las condiciones. Durante los 2 s de preparación se puede cancelar soltando E o moviéndose. Al completarse se vuelve a verificar la presencia del Nahual; si salió del volumen, la columna sigue intacta y se indica «Atrae al Nahual bajo las ruinas». Una activación válida compromete la secuencia y neutraliza la amenaza antes de reproducir la caída.

**Recursos:** oportunidad de distracción y tiempo. **Recompensa:** acceso a la escena de recuerdo familiar. **Penalización:** quedar expuesto antes de completar la interacción permite captura.

**Interacciones:** la piedra atrae, el jugador derriba y el sistema de progresión registra la resolución una sola vez.

**Casos límite:** no puede dispararse sin el Nahual ni repetirse. Si se interrumpe antes de completarse, el progreso de interacción vuelve a cero. La secuencia se muestra sin detalle gráfico y desde una posición protegida.

### 04. Activar el recuerdo de la mesa espectral

**Propósito:** enlazar la resolución de la Selva con el altar de la Iglesia sin añadir recursos ni herramientas.

**Activación y entrada:** tras el derrumbe aparece la mesa espectral; pulsar E a menos de 1,5 m inicia una breve escena de memoria familiar.

**Estado inicial:** Nahual neutralizado y mesa disponible. **Estado final:** escena completada, árboles abiertos y punto S4 guardado.

**Reglas:** no se recoge ni deposita ningún objeto. La mesa aparece en el escenario actual y no teletransporta a Iktan. Al terminar la escena se devuelve el control para caminar directamente a la Iglesia. Las piedras conservan exactamente las mismas propiedades.

**Recursos:** ninguno. **Recompensa:** avance narrativo y apertura del camino. **Penalización:** ninguna, pues la amenaza de la Selva ya está neutralizada.

**Interacciones y casos límite:** el paso permanece cerrado hasta completar la escena. Reinteractuar no duplica eventos. El guardado distingue mesa disponible y recuerdo completado; una interrupción restaura el último hito consolidado.

### 05. Retirar las tablas de los vitrales

**Propósito:** vencer al Diablo abriendo la iglesia a la luz.

**Activación y entrada:** aproximarse a cada uno de los tres vitrales y mantener E durante 2 s para derribar sus tablas podridas.

**Estado inicial:** vitral cubierto y posición de interacción accesible. **Estado final:** vitral despejado de forma irreversible dentro del intento; contador actualizado.

**Reglas:** se permite cualquier orden. Durante la interacción Iktan permanece expuesto y debe haber desviado la mirada del Diablo. Soltar E o moverse cancela y restablece el progreso parcial. Despejar un vitral reproduce un sonido de presentación que no emite eventos de distracción para la IA y abre una entrada de luz; las dos primeras entradas iluminan el entorno sin garantizar inmunidad. El tercer vitral desencadena la iluminación total y la disolución del Diablo.

**Recursos:** tiempo y ventana del señuelo. **Recompensa:** progreso visible 1/3, 2/3 y 3/3. **Penalización:** contacto con un haz antes de completar la acción causa derrota.

**Interacciones:** solo el impacto de una piedra desvía deliberadamente la mirada. La ventana de 5 s tras el giro debe cubrir acercamiento, interacción de 2 s y retirada a cobertura, con al menos 1 s de margen. Las posiciones de lanzamiento y los vitrales se distribuyen para que el desplazamiento expuesto total no supere 2 s.

**Casos límite:** las tablas retiradas no se regeneran durante el intento. Reinteractuar no añade progreso. En un mismo paso de simulación, un contacto letal previo a confirmar la retirada tiene prioridad; tras confirmar el tercer vitral, la amenaza se desactiva.


> **Navegación:** [[00 - Índice]] · ← [[01 - Jugabilidad]] · [[03 - Sistemas]] →
