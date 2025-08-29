---
theme: seriph
title: "Capítulo 1: Introducción a Godot"
layout: cover
background: ./imgs/background-gd02.jpg
routeAlias: capitulo-1
---

## Capítulo 1: <br>Introducción a Godot

---

# Índice de "Introducción"

<Toc text-sm columns="2" minDepth="1" maxDepth="2" mode="onlyCurrentTree"/>

---

## 🎭 El motor de juegos de Godot

Godot puede crear tanto **juegos** como **aplicaciones** en:

* Desktop
* Mobile [^1]
* Web
* Consolas (requiere alto nivel de programación y estándares internacionales)

[^1]: Highend devices: *Vulkan* (iPhone & Galaxy), Lowend devices: *OpenGL* (el resto)

<style>
  .footnotes-sep {
    @apply mt-20 opacity-10;
  }
  .footnotes {
    @apply text-sm opacity-75;
  }
  .footnote-backref {
    display: none;
  }
</style>

---

## 🕹️ Juegos / apps creados con Godot

Algunos ejemplos notables:

* Ex-Zodiac
* Helms of Fury
* Pixelorama

---

### 👾 Ex-Zodiac

<Youtube id="KIsGnOXHoZM?start=23" width=400 height=300 />

---

### 👾 Helms of Fury

<Youtube id="az6nKawmybY" width=400 height=300 />

---

### 👾 Pixelorama

<Youtube id="--ZcztkvWUQ" width=400 height=300 />

---

## 😎 Godot como paquete _all-inclusive_

Godot intenta ofrecer sus propias herramientas para responder a las necesidades más comunes Entre otras cosas, en el paquete se incluye:

- *espacio de trabajo para la creación de scripts* (`scripting workspace`),
- *editor de animación* (`animation editor`)
- *editor de mapas de mosaicos* (`tilemap editor`)
- *editor de sombreadores* (`shader editor`)
- *depurador* (`debugger`)
- *generador de perfiles* (`profiler`),
- *actualización sobre la marcha* (`hot-reload`) de forma local y en dispositivos remotos.

---

## 🔑 Conceptos clave de Godot

* Un **Juego** es un *árbol de escenas*
* Una **Escena** es un *árbol de nodos*
* Los **Nodos** son *bloques de construcción básicos*
* Los *nodos* se comunican entre sí mediante **Señales** (mensajes)

---

### 🏘️ El juego como *Árbol de Escenas*

*Todas las escenas* de tu juego se reúnen en el ***árbol de escena***. Y cada *escena* es un *árbol de nodos*.

---

### 🏠 Escena

La idea principal: la *escena* es un elemento flexible que suele ser <u>reutilizado</u>. Como está compuesto por _nodos_, se lo puede pensar como un **árbol de nodos**.

Una **escena** puede ser muchas cosas:

* personaje
* item (herramienta, potenciador, arma, etc.)
* menú de UI
* casa
* nivel completo

---

### 🧱 Nodos

<div grid="~ cols-2 gap-4">
<div>

Un **nodo** es un _componente de una escena_, el bloque de construcción más pequeño. A continuación podemos ver los nodos que componen el personaje `Player`: 

El personaje **Player** incluye:

* `CharacterBody2D` (`Player`)
  * `Camera2D`
  * `Sprite2D`
  * `CollisionShape2D`

<br>

> Los nombres de los nodos terminan con _2D_ porque se trata de una escena 2D. Sus contrapartes 3D tienen nombres que terminan con _3D_. Tenga en cuenta que, a partir de Godot 4, los nodos `Spatial` se denominan `Nodo3D` .

</div>

<div>
<img src="./imgs/key_concepts_character_nodes.webp" class="w-full rounded-md">
</div>

</div>

---

### ⚡ Señales

<div grid="~ cols-2 gap-4">
<div>

Algunos nodos pueden emitir **señales** cuando ocurre un _evento_, y otros nodos pueden recibirlas. Estas señales no son más que _mensajes_ que pueden ser enviados y recibidos entre nodos.

Ejemplo: Un botón emite una **señal** cuando es presionado.

</div>

<div>
<img src="./imgs/key_concepts_signals.webp" class="w-1/1.5 rounded-md">
</div>

</div>

---

## Resumen de conceptos

* **Nodos** = bloques básicos
* **Escenas** = combinaciones de nodos
* **Árbol de escena** = todas las escenas unidas
* **Señales** = mensajes de comunicación de eventos entre nodos

---

## Primer vistazo: Project Manager

<div grid="~ cols-2 gap-4">
<div>

**Project Manager** permite:

* Administrar proyectos existentes
* Importar o crear nuevos
* Acceso a **Asset Library**

</div>

<div>

<img src="./imgs/editor_intro_project_manager.webp" class="w-full rounded-md">

</div>

</div>

---

## Asset Library

<div grid="~ cols-2 gap-4">
<div>
Proyectos de demostración y recursos abiertos desarrollados por la comunidad.
</div>

<div>
<img src="./imgs/editor_intro_project_templates.webp" class="w-full rounded-md">
</div>

</div>

---

## Configuración del Project Manager

<div grid="~ cols-2 gap-4">
<div>

* Idioma del editor
* Tema de interfaz
* Escala de visualización
* Convención de nombres

</div>

<div>
<img src="./imgs/editor_intro_settings.webp" class="w-full rounded-md">
</div>

</div>

---

## Interfaz del Editor

<div grid="~ cols-2 gap-4">
<div>

Secciones principales:

- Menú superior
- Ventana gráfica (viewport)
- Pestañas de escenas
- Herramientas (toolbars)
- Paneles acoplables (docks)
- Panel inferior (bottom panel)

</div>

<div>

<img src="./imgs/editor_intro_editor_empty.webp" class="w-full rounded-md">

</div>

</div>

---

## Las cuatro pantallas principales

<div grid="~ cols-2 gap-4">
<div>

* 2D: juegos e interfaces
* 3D: niveles, luces, meshes
* Script: editor de código
* Asset Library: recursos y plugins

</div>

<div>

<img src="./imgs/editor_intro_workspace_2d.webp" class="w-full rounded-md">

</div>

</div>

---

### El editor Godot, es un juego Godot

<div grid="~ cols-2 gap-4">
<div>

* El propio editor está hecho en Godot
* Puedes usar `@tool` para ejecutar scripts en el editor
* Permite crear plugins y extensiones
  * Ejemplo: **RPG in a Box**

</div>

<div>
<img src="./imgs/engine_design_rpg_in_a_box.webp" class="w-full rounded-md">

</div>

</div>

---

### Motores 2D y 3D

* Motor **2D** y motor **3D** independientes
* Unidad base en 2D = píxeles
* Puedes mezclar 2D y 3D en el mismo juego (2.5D).

---

## Paneles acoplables (docks)

<div grid="~ cols-2 gap-4">
<div>

A ambos lados de la *Ventana gráfica* se puede acceder a los paneles acoplables:

* **Scene** → nodos de la escena activa
* **FileSystem** → archivos del proyecto
* **Inspector** → propiedades del nodo seleccionado

Ejemplo: Scene Dock

</div>

<div>

<img src="./imgs/editor_intro_scene_dock.webp" class="w-1/2 rounded-md">

</div>

</div>

---

## Panel inferior (bottom panel)

<div grid="~ cols-2 gap-4">
<div>

* Consola de depuración
* Editor de animación
* Mezclador de audio
* ... y más herramientas.

</div>

<div>

<img src="./imgs/editor_intro_bottom_panel_animation.webp" class="w-full rounded-md">

</div>

</div>

---

## Referencia de clases integrada

<div grid="~ cols-2 gap-4">
<div>

Atajos:

* `F1`
* Botón **Search Help**
* Menú **Help → Search Help**
* `Ctrl + clic` sobre clases o funciones

</div>

<div>

<img src="./imgs/editor_intro_search_help.webp" class="w-full rounded-md">

</div>

</div>

---

## Profundicemos sobre la filosofía de diseño de Godot

* **Orientado a objetos**
* **Sistema de escenas flexible**
* **Jerarquía de nodos**
* Composición y **herencia de escenas**

---

### Escenas y herencia

<div grid="~ cols-2 gap-4">
<div>

Una escena puede extender otra, como:

`Wizard` → extiende `Character`

</div>

<div>

<img src="./imgs/engine_design_01.webp" class="w-full rounded-md">

</div>

</div>

---

### Nodos en Godot

<div grid="~ cols-2 gap-4">
<div>

Todos los nodos heredan de `Node`:

`Node` → `CanvasItem` → `Node2D` → `Sprite2D`

</div>

<div>

<img src="./imgs/engine_design_02.webp" class="w-1/2 rounded-md">

</div>

</div>

---

### Paquete todo-incluido

- **Workspace de scripting:** editor de código integrado.
- **Editor de animación:** herramienta para crear animaciones complejas para personajes.
- **Editor de tilemap:** interfaz visual para construir niveles 2D usando una grilla de mosaicos o "tiles".
- **Editor de shaders:** espacio de trabajopara programar efectos visuales y materiales personalizados que corren en una tarjeta gráfica dedicada.
- **Debugger:** herramienta auxiliar para inspeccionar variables y encontrar errores en tu código.
- **Profiler:** analizador que mide el rendimiento del juego para identificar y optimizar las partes que lo vuelven lento.
- **Hot-reload:** función que actualiza instantáneamente los cambios en tu código y escenas en el juego en ejecución, sin necesidad de reiniciarlo.

---

### Lenguajes soportados

* **GDScript** (integrado en el motor)
* **C#**
* Con `GDExtension`: C, C++, Rust, D, Haxe, Swift

---

### Plugins y extensibilidad

<div grid="~ cols-2 gap-4">
<div>

Ejemplo: **State Machine Editor**

</div>

<div>

<img src="./imgs/engine_design_fsm_plugin.webp" class="w-full rounded-md">

</div>

</div>

---
