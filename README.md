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



* Asegúrate de tener instalada una versión compatible de Python antes de comenzar.
* Para salir del entorno virtual en cualquier momento, simplemente ejecuta el comando: `deactivate`.

```
