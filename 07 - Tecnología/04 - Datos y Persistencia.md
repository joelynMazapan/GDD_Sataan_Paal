# Datos y Persistencia

## Descripción de la sección

Define qué información necesita conservar el juego y cómo se estructura.

## Datos persistentes

- **Progreso.** Nivel, punto de control y estado de partida completada.
- **Configuración.** Audio, video, controles y accesibilidad en un archivo separado.
- **Inventario.** El plato de molletes y la fotografía se registran mediante hitos. Las piedras están disponibles desde el inicio.
- **Estadísticas.** La primera versión solo necesita el registro de finalización.
- **Desbloqueos.** Paso a la Iglesia, altar disponible y acceso al sendero final.
- **Otros.** Versión del formato de guardado.

## Modelo de datos

| Entidad | Campos principales |
| --- | --- |
| Partida | Versión, nivel, punto de control y finalización. |
| Hitos de la Selva | Derrumbe confirmado, plato colocado y recuerdo de la mesa completado. |
| Hitos de la Iglesia | Diablo derrotado, fotografía obtenida y revelación completada. |
| Preferencias | Volúmenes, resolución, teclas, sensibilidad y opciones de accesibilidad. |
 
I1 restaura el enfrentamiento con los tres vitrales cubiertos. I2 restaura al Diablo derrotado y el altar con la fotografía disponible si la revelación aún no se ha completado. Tras la revelación, I2 habilita el sendero. Al cargar se reconstruye el escenario a partir de hitos confirmados.

## Formato

**Formato de guardado:** JSON local como propuesta. Escribir primero un archivo temporal, validarlo y sustituir el guardado principal conservando una copia válida anterior.

**Ubicación:** Carpeta de datos persistentes de la aplicación, obtenida en Unity mediante `Application.persistentDataPath`.

**Versionado de datos:** Campo entero de versión del formato en cada archivo.

## Migraciones

Las versiones anteriores compatibles se convierten antes de cargar y se validan antes de reemplazar el archivo. Si la conversión falla o el formato es desconocido, se conserva el archivo original, se muestra un aviso y se intenta recuperar la última copia compatible.


> **Navegación:** [[00 - Índice]] · ← [[03 - Requisitos Técnicos]] · [[05 - Seguridad y Riesgos Técnicos]] →
