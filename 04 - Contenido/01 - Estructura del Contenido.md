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
│   └── Recompensa: plato de molletes → primera aparición del altar
├── Capítulo 2 — La Iglesia
│   ├── Ascenso
│   ├── El atrio y la bruma roja
│   ├── El altar — Evento: Revelación de la fotografía
│   ├── Interior de la iglesia — Jefe final: El Diablo
│   └── Recompensa: Fotografía de Iktan → altar completo
└── Final
    ├── Desenlace: Camino de cempasúchil y despedida de Abbi
    └── Mensaje final y créditos
```

## 1.2. Cantidad estimada

| TIPO                                   | CANTIDAD | DETALLE                                                                         |
| -------------------------------------- | -------: | ------------------------------------------------------------------------------- |
| **Mundos**                             |        2 | La selva y la iglesia.                                                          |
| **Niveles**                            |        2 | Uno por capítulo.                                                               |
| **Misiones**                           |        2 | Obtener el plato de molletes y obtener la fotografía de Iktan.                  |
| **Enemigos**                           |        0 | La amenaza de cada nivel es su jefe.                                            |
| **Jefes**                              |        2 | El nahual y el diablo.                                                          |
| **NPC**                                |        1 | Abbi (acompañante).                                                             |
| **Objetos clave**                      |        2 | Plato de molletes y fotografía de Iktan.                                        |
| **Objetos del altar no recolectables** |        2 | Naranjas y trompos de madera.                                                   |
| **Objetos consumibles**                |        1 | Piedras.                                                                        |
| **Cinemáticas**                        |        5 | Introducción, altar del Nivel 1, revelación, destrucción del Diablo y desenlace |

## 1.3. Dependencias
> Dependencias de progresión

| CONTENIDO                        | REQUIERE                                                             |
| -------------------------------- | -------------------------------------------------------------------- |
| **Capítulo 1 — Sendero**         | Completar el tutorial del despertar (obtener la bolsita de piedras). |
| **Enfrentamiento con el nahual** | Llegar a las ruinas.                                                 |
| **Plato de molletes**            | Derrotar al Nahual.                                                  |
| **Capítulo 2 — La iglesia**      | Recoger el plato de molletes.                                        |
| **Revelación en el altar**       | Cruzar el atrio.                                                     |
| **Enfrentamiento con el diablo** | Ver la revelación en el altar.                                       |
| **Fotografía de Iktan**          | Derrotar al diablo, la fotografía aparece al desintegrarse           |
| **Final**                        | Recoger la fotografía de Iktan.                                      |

 > Dependencias de producción
1. **Controlador de Iktan y cámara isométrica:** Base de todas las demás mecánicas.
2. **Sistema de ruido y lanzamiento de piedras:** Necesario antes de programar la reacción de los enemigos.
3. **IA de detección (patrulla, sospecha, alerta y búsqueda):** Necesaria para ambos jefes.
4. **Puntos de control y sistema de guardado:** necesarios antes de las pruebas de juego completas.
5. **Sistema de objetos del altar:** Recolección, secuencia del altar y desbloqueo de salida.
6. **Nivel 1 y nahual:** Primer nivel jugable completo, usado como prototipo y vertical slice.
7. **Mecánicas exclusivas del Nivel 2:** Abrazo de Abbi y haces de luz.
8. **Nivel 2, diablo y escena Final.**
9. **Cinemáticas, audio y pulido visual.**
 

> **Navegación:** [[00 - Índice]] · ← [[04 - Diálogos y Narrativa]] · [[02 - Niveles]] →
