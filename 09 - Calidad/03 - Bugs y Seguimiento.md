
# Bugs y Seguimiento

## Descripción de la sección

Registra problemas encontrados durante las pruebas y permite darles seguimiento. En _Saatan Historia_ cubre únicamente lo que se detectó en **Unity** (versión `6000.6.4f1`): las herramientas del editor (`Assets/Editor`) y los niveles (Nivel 1 · La iglesia). La PWA se documenta aparte. Los identificadores llevan el prefijo del ámbito: `TOOL` (herramientas del editor), `LVL` (niveles) e `INPUT` (controles).

## Registro

|ID|Bug|Severidad|Responsable|Estado|
|---|---|---|---|---|
|`TOOL-01`|Error CS8803 / CS1001 / CS1002 en `ConstructorNiveles.cs`|Alta|Yoel|Resuelto|
|`TOOL-02`|Advertencia CS0618 por `FindObjectsSortMode` (Unity 6.6)|Baja|Yoel|Resuelto|
|`TOOL-03`|Advertencia de URP por mapas de sombra (12 en un atlas de 2048)|Baja|Yoel|Abierto|
|`TOOL-04`|Archivo suelto llamado `}` en `Assets/Mapas`|Baja|Yoel|Abierto|
|`LVL-01`|Vitrales flotando sin paredes (Nivel 1)|Media|Yoel|En verificación|
|`LVL-02`|Borde del nivel visible como barras negras|Media|Yoel|Resuelto|
|`LVL-03`|Candelabros lejos de los altares|Baja|Yoel|En verificación|
|`INPUT-01`|Las interacciones del nivel no tienen controles definidos|Media|Yoel|Abierto|

## Error de compilación en `ConstructorNiveles.cs` (`TOOL-01` — Resuelto en `<hash>`)

**Estado:** resuelto. Unity marcaba tres errores en la línea `201`: `CS8803` (_Top-level statements must precede namespace and type declarations_), `CS1001` (_Identifier expected_) y `CS1002` (_; expected_). El archivo original termina en la línea `199`; la copia traía texto sobrante después de la última `}`. Mientras existía el error no aparecía el menú `Saatan`. Se resolvió borrando todo lo que seguía a la llave final de la clase.

- **Versión:** Unity 6.6 (`6000.6.4f1`)
- **Nivel / escena:** `SampleScene`
- **Pasos para reproducir:**
    1. Guardar el script en `Assets/Editor`.
    2. Esperar a que Unity compile.
    3. Abrir la pestaña Console.
- **Resultado esperado:** 0 errores y menú `Saatan` en la barra superior.
- **Resultado actual:** 3 errores y sin menú.
- **Frecuencia:** Siempre
- **Severidad:** Alta
- **Evidencia:** captura de la Console de Unity.
- **Estado:** Resuelto

## Ambientación de la iglesia (`LVL-01`, `LVL-02`, `LVL-03`)

**Estado:** `LVL-02` resuelto; `LVL-01` y `LVL-03` integrados en `ConstructorIglesia.cs`, pendientes de verificar en Unity. En el código actual se resolvieron mediante tres elementos:

1. **Vitrales sin pared (`LVL-01`):** los vitrales parecían flotar. Ahora el constructor genera un muro curvo de `120` segmentos con caras solo hacia el interior, `6` pilastras y los vitrales dentro de huecos del muro, con tablas podridas y guirnalda de cempasúchil.
2. **Borde visible (`LVL-02`):** el límite se veía como barras negras. Ahora es un objeto `Limite_Invisible` (solo colisión) y los bordes se pierden en la oscuridad ambiental.
3. **Candelabros lejos del altar (`LVL-03`):** ahora se generan a cada lado del altar mayor y de cada ofrenda lateral de Hanal Pixán.

- **Nivel / escena:** Nivel 1 · La iglesia
- **Resultado esperado:** vitrales apoyados en una pared, sin bordes a la vista y con candelabros junto a cada altar.
- **Resultado actual (antes del cambio):** vitrales flotando, borde negro visible y candelabros sueltos.
- **Severidad:** Media (`LVL-01`, `LVL-02`) y Baja (`LVL-03`)
- **Evidencia:** capturas de la vista Game de Unity.
- **Estado:** `LVL-02` Resuelto · `LVL-01` y `LVL-03` En verificación

## Controles de las interacciones del nivel (`INPUT-01`)

El movimiento de Iktan admite teclado (`WASD` o flechas) y mando (palanca izquierda); agacharse (sigilo) usa `Ctrl` izquierdo o `C`, o el botón `B` del mando. Las interacciones por implementar (derribar las tablas del vitral, lanzar piedras y trompos para distraer, recoger la recompensa) todavía no tienen controles definidos, y el vitral solo cuenta con el área `Meta_Vitral` sin lógica asociada. Queda registrado para el cierre de cobertura de controles.

- **Severidad:** Media
- **Estado:** Abierto

## Otros ajustes menores

- `TOOL-02` — **`FindObjectsSortMode` obsoleto en Unity 6.6:** se sustituyó por `FindObjectsByType<Light>()` en `ConstructorIglesia.cs`.
- `TOOL-03` — **Advertencia de URP:** _Reduced additional punctual light shadows resolution by 2 to make 12 shadow maps fit in the 2048x2048 shadow atlas_. Abierto: las luces generadas por los constructores tienen las sombras desactivadas; falta revisar las luces de la escena de personajes o subir el tamaño del atlas en el asset de URP.
- `TOOL-04` — **Archivo `}` en `Assets/Mapas`:** aparece un asset llamado `}` junto a `iglesia_detallada`, probablemente creado por accidente al copiar código. Abierto: borrarlo desde la ventana Project.

## Comportamiento de la cámara y las paredes

- **Cámara fija:** mantiene un ángulo de `65°` y sigue a Iktan con un desfase de `(0, 20, -9)` (`SeguirCamara`).
- **Muros cercanos a la cámara:** no se dibujan; es intencional para no tapar al personaje. Solo se ve el interior de los muros del fondo y de los lados.
- **Vitrales:** se colocan en el ángulo de la mancha amarilla del mapa; los pintados en la mitad sur quedan en muros que la cámara no muestra.
- **Fuego:** las llamas (`LlamaViva`) se inclinan y se agitan cuando Iktan pasa a menos de `3` unidades.
- **Reconstruir el nivel:** `ConstructorIglesia` elimina la `Iglesia_Detallada` anterior antes de crear la nueva, pero `Iktan_Jugador` no se borra: hay que volver a ejecutar _Crear jugador de prueba_ para que quede en el inicio. `ConstructorNiveles` no elimina el nivel anterior; hay que borrarlo a mano antes de reconstruir.


> **Navegación:** [[00 - Índice]] · ← [[02 - Pruebas]] · [[04 - Criterios de Aceptación]] →
