
# Cheat Sheet: Flujo de Trabajo con uv

Esta guía rápida resume las mejores prácticas y comandos esenciales para gestionar proyectos de Python utilizando `uv`.

---

## 🚀 Comandos Principales

### ¿Cuándo usar `uv init`?
Se utiliza al **inicio de un nuevo proyecto**. Crea la estructura básica, incluyendo un archivo `pyproject.toml`, un archivo `.python-version` y un `hello.py` de ejemplo.
```bash
uv init mi-proyecto
```
Pero si ya existe archivos .py en el proyecto ya no crea  hello.py.

### ¿Cuándo usar `uv venv`?

Se usa para **crear manualmente un entorno virtual** `.venv`. Aunque comandos como `uv run` o `uv sync` lo crean automáticamente si no existe, `uv venv` te permite especificar una versión de Python concreta.

```bash
uv venv --python 3.12
```
En nuestro caso  solo tendremos que  agregar las dependencia dentro de `pyproject.toml` y correr `uv sync` y con eso  se creara nuestro ambiente virtual automaticamente

---
### ¿Cómo activar un ambiente ya creado?

Si ya se ejecutó `uv sync` o `uv run` entonces podemos activar el ambiente ejecutando en la terminal:

```bash
source .venv/bin/activate
```

---

## 📂 Gestión de Git (Control de Versiones)

Para mantener la consistencia entre colaboradores, sigue estas reglas sobre qué incluir en tu repositorio:

### ✅ Lo que SÍ se sube (Commit)

* **`pyproject.toml`**: Define las dependencias y la configuración del proyecto.
* **`uv.lock`**: **Crucial.** Garantiza que todos los desarrolladores instalen exactamente las mismas versiones de las librerías.
* **`.python-version`**: Indica a `uv` qué versión de Python debe utilizar para este proyecto.

### ❌ Lo que NO se sube (Gitignore)

* **`.venv/`**: El entorno virtual es local y pesado; se reconstruye fácilmente.
* **`__pycache__/`**: Archivos compilados de Python.
* **`.uv/`**: Directorios de caché específicos de la herramienta.

---

## 💻 Clonando el Proyecto (Nueva Computadora)

Si descargas un repositorio que ya utiliza `uv`, el proceso para empezar a trabajar es extremadamente sencillo:

### 1. Sincronizar el proyecto

En lugar de instalar manualmente, usa `uv sync`. Este comando leerá el `uv.lock`, creará el entorno virtual e instalará todas las dependencias exactas en un solo paso:

```bash
uv sync
```

### 2. Ejecutar el código

Para correr tus scripts asegurándote de que usan el entorno correcto:

```bash
uv run main.py
```

Para correr la aplicación de streamlit que se encuentra implementada dentro de `main.py` qjecutarías lo siguiente:


```bash
uv run streamlit run main.py
```


---

## 🛠️ Resumen de comandos comunes

| Acción | Comando |
| --- | --- |
| **Añadir una librería** | `uv add nombre-paquete` |
| **Eliminar una librería** | `uv remove nombre-paquete` |
| **Actualizar el lockfile** | `uv lock --upgrade` |
| **Ejecutar comando de terminal** | `uv run <comando>` |
| **Activar el ambiente virtual** | `source .venv/bin/activate` |

> **Pro-tip:** `uv sync` es el comando más importante al colaborar, ya que mantiene tu `.venv` en perfecta sintonía con el archivo `uv.lock`.


