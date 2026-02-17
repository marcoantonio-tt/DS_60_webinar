# DS_60_webinar


# Guía de Configuración del Entorno de Desarrollo

Este documento proporciona las instrucciones necesarias para configurar el entorno virtual y las dependencias del proyecto utilizando dos métodos: el módulo estándar de Python y la herramienta optimizada `uv`.

---

## 1. Configuración con Python `venv` (Estándar)

Sigue estos pasos para crear y activar un entorno virtual utilizando el módulo nativo de Python.

### Paso 1: Crear el entorno virtual
Ejecuta el siguiente comando en la raíz de tu proyecto:
```bash
python -m venv .venv

```

### Paso 2: Activar el entorno

Dependiendo de tu sistema operativo, utiliza el comando correspondiente:

* **Windows (PowerShell):**
```powershell
.\.venv\Scripts\Activate.ps1

```


* **macOS / Linux:**
```bash
source .venv/bin/activate

```



### Paso 3: Instalar dependencias

Una vez activado el entorno, instala los paquetes necesarios:

```bash
pip install -r requirements.txt

```

---

## 2. Configuración con `uv` (Recomendado)

`uv` es un gestor de paquetes de Python extremadamente rápido escrito en Rust. Úsalo para una instalación significativamente más veloz. ([UV webpage](https://docs.astral.sh/uv/)) Hay diferentes formas de isntalarlo pero si ya tenemos python solo tenemos que hacer:

```bash
pip install uv
```
### Paso 1: Crear el entorno virtual
Inicializa el proyecto 
```bash
uv init
```
### Paso 1: Crear el entorno virtual

Crea un nuevo entorno virtual con:

```bash
uv venv

```

### Paso 2: Activar el entorno

El proceso de activación es similar al estándar:

* **Windows (PowerShell):**
```powershell
.\.venv\Scripts\activate

```


* **macOS / Linux:**
```bash
source .venv/bin/activate

```



### Paso 3: Instalar dependencias

Utiliza el comando optimizado de `uv` para instalar desde el archivo de requerimientos:

```bash
uv pip install -r requirements.txt

```

---

## Notas Adicionales

* Asegúrate de tener instalada una versión compatible de Python antes de comenzar.
* Para salir del entorno virtual en cualquier momento, simplemente ejecuta el comando: `deactivate`.

```
