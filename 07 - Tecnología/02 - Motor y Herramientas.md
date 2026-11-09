# Motor y Herramientas

| Tecnología | Uso en el proyecto actual |
| --- | --- |
| Unity 6 (6000.6.0f1) | Integración de escenas, física 3D, animación, interfaz y pruebas en Play Mode. |
| URP 17.6.0 | Renderizado de los entornos voxel, iluminación, materiales y efectos de niebla, haces y vitrales. |
| Input System 1.20.1 | Acciones de teclado y ratón para mover a Iktan, controlar la cámara, lanzar piedras, interactuar y navegar por los menús. |
| Cinemachine 6.6.0 | Cámara en tercera persona y seguimiento de Iktan. Permite ajustar el encuadre y suavizar los cambios al agacharse. |
| C# | Movimiento, animación procedimental, distracciones con piedras, IA, objetivos y guardado. |
| TextMeshPro | Textos de interfaz, como objetivos, indicaciones de interacción, subtítulos y menús. |
| Blender | Modelado Voxel Art 3D de personajes, escenarios y objetos. |
| FL Studio | Producción de música y efectos sonoros. |
| Obsidian / Markdown | Edición del GDD y navegación entre notas del proyecto. |

## Organización

Los recursos del juego están agrupados en `Assets/Project`. El código va en `Scripts`, las escenas en `Scenes` y los objetos reutilizables en `Prefabs`. Los ajustes generales y los recursos de TextMeshPro se mantienen en carpetas propias dentro de `Assets`.

```text
Assets/
├── Project/
│   ├── Animations/
│   ├── Audio/
│   ├── Input/
│   ├── Materials/
│   ├── Prefabs/
│   │   ├── Characters/
│   │   ├── Core/
│   │   ├── Environment/
│   │   ├── Items/
│   │   └── UI/
│   ├── Scenes/
│   └── Scripts/
├── Settings/
├── TextMeshPro/
└── TutorialInfo/
```

Los prefabs se agrupan por función. `Characters` reúne personajes, `Core` componentes comunes, `Environment` piezas de escenario, `Items` objetos y `UI` elementos de interfaz. Se conservan nombres descriptivos y los metadatos de Unity junto a cada recurso en el control de versiones.

> **Navegación:** [[00 - Índice]] · ← [[01 - Arquitectura Técnica]] · [[03 - Requisitos Técnicos]] →
