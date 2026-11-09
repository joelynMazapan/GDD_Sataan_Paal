# Estructura del Contenido

## 1.1. Estructura

```text
Saatan Paal
├── Introducción (cinemática: el diablo y el cocol)
├── Capítulo 1 — La Selva
│   ├── Despertar (tutorial)
│   ├── Sendero de la hierba alta
│   ├── El claro
│   ├── Las ruinas — Jefe: el Nahual
│   └── Recompensa: plato de molletes → mesa espectral y recuerdo familiar → paso abierto
├── Capítulo 2 — La Iglesia
│   ├── Ascenso
│   ├── El atrio y la bruma roja
│   ├── Interior de la iglesia — Jefe final: El Diablo
│   └── Recompensa: altar y fotografía de Iktan → revelación
└── Final
    ├── Desenlace: Camino de cempasúchil y despedida de Abbi
    └── Mensaje final y créditos
```

## 1.2. Cantidad estimada


| TIPO                                   | CANTIDAD | DETALLE                                                                                             |
| -------------------------------------- | -------: | --------------------------------------------------------------------------------------------------- |
| **Mundos**                             |        2 | La selva y la iglesia.                                                                              |
| **Niveles**                            |        2 | Uno por capítulo.                                                                                  |
| **Misiones**                           |        6 | Tres en la Selva y tres en la Iglesia.                                                              |
| **Enemigos**                           |        0 | La amenaza de cada nivel es su jefe.                                                                |
| **Jefes**                              |        2 | El nahual y el diablo.                                                                              |
| **NPC**                                |        1 | Abbi (acompañante).                                                                                |
| **Objetos clave**                      |        2 | Plato de molletas tras derrotar al nahual;Fotografía de Iktan, disponible tras derrotar al Diablo. |
| **Objetos del altar no recolectables** |       — | Velas y flores como elementos de escenografía.                                                     |
| **Herramientas de distracción**       |        1 | Piedras disponibles desde el inicio, con recarga entre lanzamientos.                                |
| **Cinemáticas**                       |        5 | Introducción, recuerdo de la mesa, derrota del Diablo, revelación y desenlace                     |

## 1.3. Dependencias

> Dependencias de progresión


| CONTENIDO                        | REQUIERE                                                                             |
| -------------------------------- | ------------------------------------------------------------------------------------ |
| **Capítulo 1 — Sendero**       | Completar el tutorial del despertar. Las piedras están disponibles desde el inicio. |
| **Enfrentamiento con el nahual** | Llegar a las ruinas.                                                                 |
| **Plato de molletes y mesa espectral** | Derrotar al Nahual con el derrumbe. |
| **Capítulo 2 — La iglesia**    | Colocar el plato en la mesa espectral y completar el recuerdo.                                          |
| **Revelación en el altar**      | Derrotar al Diablo y obtener la fotografía.                                         |
| **Enfrentamiento con el diablo** | Cruzar el atrio y entrar en la nave.                                                 |
| **Fotografía de Iktan**         | Derrotar al Diablo. El pedestal se transforma en altar y aparece la fotografía.     |
| **Final**                        | Obtener la fotografía y completar la revelación.                                   |

> Dependencias de producción

1. **Controlador de Iktan y cámara en tercera persona:** Base de todas las demás mecánicas.
2. **Sistema de ruido y lanzamiento de piedras:** Necesario antes de programar la reacción de los enemigos.
3. **IA de detección (patrulla, sospecha, alerta y búsqueda):** Necesaria para ambos jefes.
4. **Puntos de control y sistema de guardado:** necesarios antes de las pruebas de juego completas.
5. **Hitos narrativos:** Mesa espectral, transformación del pedestal, obtención de la fotografía y apertura de la salida.
6. **Nivel 1 y nahual:** Primer nivel jugable completo, usado como prototipo y vertical slice.
7. **Mecánicas exclusivas del Nivel 2:** Haces de luz, retirada de tablas y revelación tras la victoria.
8. **Nivel 2, diablo y escena Final.**
9. **Cinemáticas, audio y pulido visual.**

> **Navegación:** [[00 - Índice]] · ← [[04 - Diálogos y Narrativa]] · [[02 - Niveles]] →
