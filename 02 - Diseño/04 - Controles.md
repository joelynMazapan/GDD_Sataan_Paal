# Controles

## Descripción de la sección

Define la relación entre las acciones del jugador y las entradas físicas del dispositivo.

## Mapa de controles

| Acción                                         | Teclado                                   | Mouse                  | Control   | Táctil    |
| ---------------------------------------------- | ----------------------------------------- | ---------------------- | --------- | --------- |
| Mover a Iktan                                  | Teclas W, A, S, D / Flechas direccionales | No aplica              | No aplica | No Aplica |
| Moverse en sigilo                              | Mantener Shift izquierdo                  | No aplica              | No Aplica | No Aplica |
| Apuntar Distracción                            | No aplica                                 | Mantener Click derecho | No Aplica | No Aplica |
| Lanzar Distracción                             | No aplica                                 | Click izquierdo        | No Aplica | No Aplica |
| Correr / Esquivar<br>                          | Barra EspaciadoraN                        | No aplica              | No Aplica | No Aplica |
| Interactuar (Abrazar a Abbi / Activar trampas) | Tecla E                                   | No aplica              | No Aplica | No Aplica |
| Menú / Pausa                                   | Tecla Esc                                 | No aplica              | No aplica | No Aplica |

## Principios de control

- Los controles deben ser consistentes.
- Las acciones críticas deben ser fáciles de identificar.
- Debe existir retroalimentación visual, sonora o háptica cuando corresponda.
- Evitar combinaciones innecesariamente complejas.

## Reasignación

¿El jugador puede cambiar los controles?
Sí, el jugador podrá reasignar los controles en el menú de "Opciones > Controles" para Teclado.

## Entrada y retroalimentación

Describe qué ocurre inmediatamente después de cada entrada importante.

- **Agacharse (Sigilo):**
    
- _Entrada:_ Presionar y mantener Shift 
- _Retroalimentación Inmediata:_ Iktan cambia a una animación de cuclillas. Si está oculto en la oscuridad o tras una cobertura válida, su modelo 2D se oscurece ligeramente  para confirmar visualmente al jugador que es "invisible". La cámara se acerca para aumentar la sensación de sigilo.
- **Apuntar Roca:**

    - _Entrada:_ Mantener Click Derecho .        
    - _Retroalimentación Inmediata:_ Iktan levanta el brazo. Aparece una línea punteada desde su mano hasta el suelo, terminando en un círculo que representa el radio de sonido.
        
- **Lanzar Roca:**
    
    - _Entrada:_ Click Izquierdo.
    - _Retroalimentación Inmediata:_ Animación rápida de lanzamiento. Al impactar el suelo, se reproduce un sonido seco ("¡CLACK!") y una onda expansiva visual muy sutil (un anillo blanco que se expande rápido y desaparece) marca el radio exacto donde los enemigos escucharon el ruido. Si el jugador usa mando, hay una ligera vibración (háptica) al momento del impacto.
        
- **Interactuar (Abrazar a Abbi):**
-
    - _Entrada:_ Mantener presionado E .
    - _Retroalimentación Inmediata:_ Iktan se detiene y acaricia a Abbi. Se escucha un sonido de respiración calmada, un pequeño destello brillante emana de la perrita de azúcar, y la viñeta oscura (niebla de pánico) que cubría la pantalla del jugador retrocede rápidamente, aclarando la visión.

> **Navegación:** [[00 - Índice]] · ← [[03 - Sistemas]] · [[05 - Progresión]] →
