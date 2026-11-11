# Backlog del Proyecto

El backlog contiene el trabajo necesario para convertir el diseño en un videojuego funcional.

## Formato de tarea

### Tarea
# Backlog del Proyecto

## Descripción de la sección

El backlog contiene el trabajo necesario para convertir el diseño en un videojuego funcional.

## Formato de tarea

### Tarea

**Descripción:** 

**Responsable:**

**Prioridad:** Alta / Media / Baja

**Dependencias:**

**Criterio de aceptación:**

**Estado:** Pendiente / En progreso / Bloqueada / Terminada

## Backlog

- [x] Configuración inicial del repositorio y motor (Unity 6)
* **Descripción:** Inicializar el proyecto en Unity 6, configurar la estructura de carpetas estándar y establecer el control de versiones en GitHub bajo la metodología Git Flow. 
* **Responsable:** Canul Gijon Yoel Alfredo 
* **Prioridad:** Alta 
* **Dependencias:** Ninguna 
* **Criterio de aceptación:** Repositorio funcional en la rama `develop` con el proyecto base configurado y listo para recibir commits de los colaboradores. 
* **Estado:** Terminada

- [x] Prototipado del Core Loop (Greybox 3D)
* **Descripción:** Programar el movimiento tridimensional del personaje (ejes lateral y vertical) y el sistema de desplazamiento automático de la cámara (*auto-scrolling*). 
* **Responsable:** Canul Gijon Yoel Alfredo 
* **Prioridad:** Alta 
* **Dependencias:** Tarea 01 
* **Criterio de aceptación:** El personaje se desplaza por el espacio 3D con físicas estables y colisiones precisas usando geometrías temporales (*Greybox*). 
* **Estado:** Terminado

- [ ] Sistema de Generación y Limpieza de Obstáculos 
* **Descripción:** Desarrollar el script procedural que genera obstáculos tridimensionales a lo largo del nivel y los elimina de memoria al salir del campo de visión. 
* **Responsable:** Lomeli Cruz Juan David 
* **Prioridad:** Alta 
* **Dependencias:** Tarea 02
* **Criterio de aceptación:** Los obstáculos se instancian dinámicamente sin causar pérdidas de rendimiento (*Garbage Collection* optimizado) y se destruyen al quedar atrás.
* **Estado:** Pendiente

- [x] Diseño y Modelado de Assets 3D Base
* **Descripción:** Crear o adaptar los modelos 3D esenciales (personaje principal, obstáculos fijos/móviles y geometría del escenario del Nivel 1). 
* **Responsable:** Cruz Santiago Zaidy Itzamara 
* **Prioridad:** Media 
* **Dependencias:** Tarea 02 
* **Criterio de aceptación:** Modelos texturizados y optimizados para importarse en Unity sin sobrecargar el conteo de polígonos. 
* **Estado:** Pendiente

- [ ] Animaciones tridimensionales del personaje 
* **Descripción:** Configurar el *Animator Controller* y aplicar las animaciones de desplazamiento, esquive y colisión para el modelo 3D. 
* **Responsable:** Reyes del Ángel Brandon Michelle 
* **Prioridad:** Media
* **Dependencias:** Tarea 04 
* **Criterio de aceptación:** Las animaciones responden de forma fluida a las entradas del usuario y a los cambios de estado en el juego. 
* **Estado:** Pendiente

- [ ] Implementación de Interfaz de Usuario (UI / HUD)
* **Descripción:** Diseñar y programar los elementos visuales en pantalla: menú principal y pantalla de Game Over.
* **Responsable:** Cortés Mancilla Renata 
* **Prioridad:** Media 
* **Dependencias:** Tarea 02
* **Criterio de aceptación:** La UI es completamente funcional, escala correctamente y permite navegar entre el menú y la partida. 
* **Estado:** Pendiente

- [ ] Integración de Audio y Banda Sonora 
* **Descripción:** Seleccionar y programar el sistema de reproducción para la música de fondo (loop) y los efectos de sonido.
* **Responsable:** Lomeli Cruz Juan David 
* **Prioridad:** Baja 
* **Dependencias:** Tarea 02, Tarea 06
* **Criterio de aceptación:** Los sonidos se reproducen en el momento exacto de la interacción sin solapamientos extraños ni saturación de volumen. 
* **Estado:** Pendiente

- [ ] Control de Calidad (QA) y Ajuste de Dificultad
* **Descripción:** Ejecutar pruebas de integración del Nivel 1 completo, reportar y corregir bugs de colisiones 3D o caídas de frames. 
* **Responsable:** Cortés Mancilla Renata 
* **Prioridad:** Alta 
* **Dependencias:** Tareas 03, 05, 06, 07 
* **Criterio de aceptación:** El juego mantiene estable y el Nivel 1 y NIvel 2 se pueden completar de principio a fin sin bloqueos críticos. 
* **Estado:** Pendiente

## Priorización

Prioriza aquello que desbloquea otras tareas o valida primero las partes más riesgosas del proyecto.


> **Navegación:** [[00 - Índice]] · ← [[03 - Roadmap]] · [[05 - Gestión de Cambios]] →