# Animator Studio 🎬🤖

[English](#-english) | [Español](#-español)

---

## 🇬🇧 English

**Animator Studio** is an open-source, desktop 2D animation (puppeteering) engine designed to automate and streamline the creation of videos featuring illustrated characters.

Unlike traditional video editors, this tool treats animation as data structures. It allows defining anchor points (*sockets*), saving reusable animations as templates, and coordinating movements on a timeline to export precise scenes. It's the ideal solution for YouTube channels (newscasts, tutorials), content creators, and AI-generated workflows.

### 🎯 Main Goal

The primary goal of Animator Studio is to eliminate repetitive friction in recurrent animated content creation. Instead of manually animating every frame in heavy software, the user can:

1. Create a library of body parts, expressions, and objects.
2. Define spatial logic (e.g., "the facial expression always follows this head coordinate").
3. Combine these elements into a modular timeline.
4. Export the result as MP4/WebM for final compositing, or even generate entire videos from a JSON file structured by an LLM.

### ✨ Key Features

- **Socket System**: Define relative coordinates on base images so other objects (hands, faces, hats) follow the main movement mathematically using Parent-Child hierarchies.
- **Independent Timelines**: Synchronize separate tracks (e.g., a cyclic body animation vs. dynamic facial expressions for lip-sync).
- **Asset & Template Manager**: Tag-indexed storage backed by SQLite, allowing you to save perfect combinations ("Nerd explaining with a pointer") and instantiate them with one click.
- **AI Pipeline (JSON-to-Scene)**: Architecture designed to read JSON configurations, allowing text engines (LLMs) to write the script and "program" the character's acting automatically.
- **Native Export**: FFmpeg integration to render scenes at 60fps with a green screen (Chroma Key) or transparent Alpha channel.

### 🛠️ Tech Stack

This project is built with a high-performance hybrid architecture, compiling into a single native binary that consumes a fraction of the memory Electron would require.

- **Frontend**: [Angular](https://angular.dev/) (UI, Timeline, State) + Native **HTML5 Canvas** API (2D Viewer).
- **Backend & OS Interop**: [Go](https://go.dev/) (Concurrent processing, File I/O, FFmpeg orchestration).
- **Desktop Framework**: [Wails v2](https://wails.io/) (Ultra-lightweight IPC bridge between Go and Angular using the OS native webkit engine).
- **Database**: [SQLite](https://www.sqlite.org/) (Embedded local relational storage).

### 🚀 Installation & Development

**Prerequisites:**

- [Go](https://go.dev/) 1.21+
- [Node.js](https://nodejs.org/) 18+ and npm
- [Angular CLI](https://angular.dev/tools/cli)
- [Wails CLI](https://wails.io/) (`go install github.com/wailsapp/wails/v2/cmd/wails@latest`)
- [FFmpeg](https://ffmpeg.org/) (Added to system environment variables)

**Clone & Run:**

```bash
# 1. Clone the repository
git clone https://github.com/FacundoRochaSeret/animator-studio.git
cd animator-studio

# 2. Install frontend dependencies
cd frontend
npm install
cd ..

# 3. Run development environment (Hot Reload for Go & Angular)
wails dev
```

📝 Roadmap

- [ ] SQLite relational schema initialization.
- [ ] Angular Canvas rendering engine implementation.
- [ ] Graphical interface for Socket marking.
- [ ] Timeline manager with multi-layer (Z-Index) support.
- [ ] Go wrapper for FFmpeg rendering processes.

🇪🇸 Español

**Animator Studio** es un motor de animación 2D (puppeteering) de escritorio, de código abierto, diseñado para automatizar y agilizar la creación de videos con personajes ilustrados.

A diferencia de los editores de video tradicionales, esta herramienta trata la animación como estructuras de datos. Permite definir puntos de anclaje (sockets), guardar animaciones reutilizables como plantillas y coordinar movimientos en una línea de tiempo para exportar escenas precisas. Es la solución ideal para canales de YouTube (noticieros, tutoriales), creadores de contenido y flujos de trabajo generados por Inteligencia Artificial.

### 🎯 Objetivo del Proyecto

El objetivo principal de Animator Studio es eliminar la fricción repetitiva en la creación de contenido animado recurrente. En lugar de animar cada fotograma a mano en software pesado, el usuario puede:

1. Crear una biblioteca de partes del cuerpo, expresiones y objetos.
2. Definir lógicas espaciales (ej. "la expresión facial siempre sigue a esta coordenada de la cabeza").
3. Combinar estos elementos en una línea de tiempo modular.
4. Exportar el resultado en MP4/WebM para su composición final, o incluso generar videos completos a partir de un archivo JSON estructurado por un LLM.

### ✨ Características Principales

- **Sistema de Anclaje (Sockets)**: Define coordenadas relativas en imágenes base para que otros objetos (manos, caras, sombreros) sigan el movimiento principal matemáticamente mediante jerarquías Padre-Hijo.
- **Líneas de Tiempo Independientes**: Sincroniza pistas separadas (ej. animación del cuerpo cíclica vs. expresiones faciales dinámicas para lip-sync).
- **Gestor de Assets y Plantillas**: Almacenamiento indexado por etiquetas (tags) respaldado por SQLite, permitiendo guardar combinaciones perfectas ("Ñoño explicando con puntero") e instanciarlas en un clic.
- **Pipeline de IA (JSON-to-Scene)**: Arquitectura pensada para leer configuraciones JSON, lo que permite a motores de texto (LLMs) escribir el guion y "programar" la actuación del personaje automáticamente.
- **Exportación Nativa**: Integración con FFmpeg para renderizar las escenas a 60fps con fondo verde (Chroma Key) o canal Alpha transparente.

### 🛠️ Stack Tecnológico

Este proyecto está construido con una arquitectura híbrida de alto rendimiento, compilando en un único binario nativo que consume una fracción de la memoria que exigiría Electron.

- **Frontend**: Angular (UI, Línea de tiempo, Estado) + API nativa de HTML5 Canvas (Visor 2D.
- **Backend y OS Interop**: Go (Procesamiento concurrente, I/O de archivos, orquestación de FFmpeg.
- **Desktop Framework**: Wails v2 (Puente IPC ultraligero entre Go y Angular usando el motor webkit nativo del sistema operativo.
- **Base de Datos**: SQLite (Almacenamiento relacional local incrustado.

### 🚀 Instalación y Desarrollo

**Prerrequisitos:**

- Go 1.21+
- Node.js 18+ y npm
- Angular CLI
- Wails CLI (`go install github.com/wailsapp/wails/v2/cmd/wails@latest`)
- FFmpeg (Añadido a las variables de entorno del sistema)

**Clonar y Ejecutar:**

```bash
# 1. Clonar el repositorio
git clone https://github.com/FacundoRochaSeret/animator-studio.git
cd animator-studio

# 2. Instalar dependencias del frontend
cd frontend
npm install
cd ..

# 3. Levantar el entorno de desarrollo (Hot Reload para Go y Angular)
wails dev
```

📝 Próximos Pasos (Roadmap)

- [ ] Inicialización del esquema relacional en SQLite.
- [ ] Implementación del motor de renderizado Canvas en Angular.
- [ ] Interfaz gráfica para la marcación de Sockets.
- [ ] Gestor de línea de tiempo con soporte para múltiples capas (Z-Index).
- [ ] Wrapper en Go para procesos de renderizado con FFmpeg.

---

**Autor**: Facundo Rocha Seret

**Licencia**: MIT