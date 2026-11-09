# Interfaz Visual

## Descripción de la sección

Documenta la información que el juego muestra al jugador y las reglas visuales de la interfaz.

## HUD

- **Piedras:** Icono de la única herramienta de distracción. Indica si el lanzamiento está disponible o en recarga.
- **Apuntado:** Trayectoria prevista y marca del primer impacto estimado mientras se mantiene la acción.
- **Objetivo:** Texto breve que se actualiza al completar un hito. En la nave se añade el contador de vitrales.
- **Indicadores contextuales:** Tecla configurada, nombre de la acción y barra cuando la interacción debe mantenerse.
- **Estado de sigilo:** Icono de ocultamiento o alerta acompañado de una viñeta leve en los bordes. La viñeta responde a la situación actual y conserva visibles los haces y las indicaciones.

La captura se comunica mediante el estado de derrota. Las rutas se leen en el escenario y con las señales del acompañante.

## Jerarquía visual

1. Peligro inmediato e interacción activa.
2. Objetivo actual y avance de vitrales.
3. Disponibilidad de piedras y ayudas de orientación.

## Estados

| Estado | Respuesta visual |
|---|---|
| Normal | HUD reducido e indicación de piedra disponible. |
| Oculto | Icono reconocible y viñeta suave cuando la cobertura protege a Iktan. |
| Advertencia | Indicador visible de sospecha o amenaza, acompañado de la señal del enemigo. |
| Acción bloqueada | Texto breve si la columna carece de una condición válida. El icono de piedra indica la recarga cuando procede. |
| Éxito | Confirmación breve, actualización del objetivo o del contador y cambio visible en el escenario. |
| Derrota | Transición breve y menú con «Reintentar» y «Menú principal». |

## Convenciones

**Tipografía:** Letras pixeladas o de bloques en títulos. Usar una variante legible en textos de objetivos y menús.

**Iconografía:** Siluetas geométricas consistentes. Acompañar los estados críticos con forma o texto, además del color.

**Tamaños mínimos:** Propuesta para 1080p de 18 px en avisos, 22 px en subtítulos y escalado proporcional según la resolución.

**Contraste:** Fondos tierra y neutros en menús, incluido el panel de configuración. Colocar texto marfil sobre panel oscuro cuando el escenario dificulte la lectura.

**Animaciones:** Transiciones cortas y discretas. Mantener estables los textos y permitir que la viñeta se reduzca si dificulta la lectura.

## Pantallas

- **Menú principal:** Nueva partida, Continuar, Opciones y Salir.
- **Pausa:** Reanudar, Opciones, Reiniciar punto de control y Volver al menú.
- **Configuración:** Paneles con paleta tierra y foco visible para navegación por teclado.
- **Victoria:** Sendero final, mensaje de concientización y créditos.
- **Derrota:** Reintentar desde el último punto de control o volver al menú.

> **Navegación:** [[00 - Índice]] · ← [[03 - Entornos]] · [[05 - Audio y Música]] →
