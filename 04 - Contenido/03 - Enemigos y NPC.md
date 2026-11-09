# Enemigos y NPC

Las dos amenazas se resuelven mediante el escenario. Los valores de percepción y tiempos son propuestas de prototipo.

## El Nahual

| Campo | Diseño |
| --- | --- |
| Rol | Amenaza principal de la Selva. Enseña a combinar cobertura y distracción. |
| Comportamiento | Acecha desde rutas terrestres y puntos elevados previstos. Investiga el impacto audible de una piedra y persigue a Iktan si confirma que lo ha visto. |
| Vida y daño | Encuentro resuelto por un derrumbe. El contacto con el Nahual activo causa captura. |
| Defensas | Los impactos de piedra solo generan ruido. |
| Velocidad | Acecho más lento que persecución. Valores de movimiento pendientes de ajustar al probar las rutas de escape. |
| Detección | Visión propuesta de 12 m y 80°, con 0,8 s de visión continua para confirmar. El impacto de una piedra se oye dentro de 8 m. |
| Ataque | Persigue y captura por contacto. Si pierde de vista a Iktan durante 2 s, busca durante 5 s en la última posición conocida. |
| Debilidad | La cobertura y la hierba alta con Iktan agachado dificultan que lo vea. Puede atraerse bajo el techo dañado para confirmar la trampa. |
| Recompensa | La derrota habilita la mesa espectral. |

**Estados de IA.** Acecho → sospecha → persecución → búsqueda → acecho. Un impacto audible inicia investigación cuando la prioridad de percepción lo permite. Tras llegar al impacto investiga durante 5 segundos. El derrumbe válido cambia su estado a neutralizado.

## El Diablo

| Campo | Diseño |
| --- | --- |
| Rol | Amenaza final de la Iglesia. Pone a prueba el cruce entre coberturas y el cálculo de las ventanas de distracción. |
| Comportamiento | Permanece en un punto central y barre la nave con dos haces rojos. Gira hacia impactos audibles. |
| Vida y daño | Encuentro resuelto por la luz del tercer vitral. Un haz que alcance a Iktan sin una cobertura interpuesta produce captura inmediata. |
| Defensas | Los impactos de piedra modifican su orientación. El jugador despeja las tablas mediante interacción directa. |
| Velocidad | Giro máximo propuesto de 35° por segundo. |
| Detección | Alcance propuesto de 20 m y apertura de 12° por haz. Los obstáculos opacos bloquean la detección. El impacto de piedra se oye dentro de 8 m. |
| Ataque | Barrido con dos haces activos, incluso durante el giro hacia una distracción. |
| Debilidad | Mantiene su orientación durante 5 segundos tras el giro. La luz acumulada al despejar los tres vitrales disuelve la sombra. |
| Recompensa | El pedestal se transforma en altar. Iktan puede tomar su fotografía y descubrir la verdad. |

**Estados de IA.** Barrido → giro hacia el impacto → atención → barrido. El contacto con un haz inicia captura. El tercer vitral confirmado desactiva los haces y cambia el estado a disuelto.

## NPC · Abbi

| Campo | Diseño |
| --- | --- |
| Nombre y función | Abbi, xoloitzcuintle espiritual de calaverita de azúcar. Acompaña y orienta a Iktan. |
| Ubicación | Ambos niveles, desde el despertar hasta el umbral del sendero final. |
| Interacción | Sigue, espera, alerta con su postura y señala rutas u objetos con la mirada. |
| Diálogos | Comunicación mediante gestos y sonidos suaves, con una señal visual o un subtítulo cuando la pista lo requiere. |
| Condiciones | Sus pistas dependen del peligro cercano y del objetivo actual. Las amenazas ignoran su presencia y sus sonidos. |
| Información | Señala una cobertura, las ruinas, la mesa o un elemento relevante de la Iglesia. El jugador decide cuándo cruzar y cómo resolver cada objetivo. |

> **Navegación:** [[00 - Índice]] · ← [[02 - Niveles]] · [[04 - Objetos y Coleccionables]] →
