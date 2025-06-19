# 📦 GitHub Actions Learning

---

## Estructura YAML

conceptos usados en el .yaml para ejecutar un workflow en Github Actions

---

### 📁 Workflow

Un **workflow** es un archivo `.yml` ubicado en `.github/workflows/`.  
Define una serie de trabajos (jobs) automatizados que se ejecutan en respuesta a eventos.

---

### 🚀 Event

Un **evento** es lo que dispara (activa) el workflow. Ejemplos comunes:

- `push` → al hacer push
- `pull_request` → al abrir o actualizar un PR
- `schedule` → ejecución programada (cron)
- `workflow_dispatch` → ejecución manual

---

### 🧱 Job

Un **job** es un bloque de trabajo dentro de un workflow.  
Cada job se ejecuta en un **runner**.  
Puedes usar `needs:` para que un job espere a otro.

---

### 🔹 Step

Un **step** es una acción individual dentro de un job.  
Puede ser un comando `run:` o una `action:`.

---

### 🔁 Action

Una **action** es un bloque de código reutilizable que realiza una tarea específica.  
Ejemplos comunes:

- `actions/checkout` → clona tu repositorio
- `actions/setup-node` → instala Node.js
- `actions/upload-artifact` → guarda archivos del workflow

---

### 🖥️ Runner

El **runner** es el entorno donde se ejecutan los jobs.  
GitHub ofrece runners en la nube:

- `ubuntu-latest`
- `windows-latest`
- `macos-latest`

También puedes usar runners **autohospedados**.

---

### 🌐 Contextos

Los **contextos** te permiten acceder a información útil del entorno.  
Se acceden con `${{ ... }}`.

| Contexto                  | Descripción                             |
|---------------------------|-----------------------------------------|
| `github.ref`              | Rama o tag del evento                   |
| `github.actor`            | Usuario que inició el evento            |
| `env.MI_VAR`              | Variable de entorno definida por ti     |
| `steps.step_id.outputs.X` | Output de un paso anterior              |

## CI/CD

### CI (Continous Integration)

CI = Concento + Automatizacion

- Proceso para integrar cambios frecuentes en el repositorio.
- Cada integracion  dispara un build y tests (pruebas unitarias).
- Ayuda a detectar y reducir conflictos entre ramas.

### CD (Continous Delivery)

- Proceso de entrega de codigo a entorno staging (pre-produccion).
- Libera versiones confiables bajo demanda.
- Automatiza el despliegue a produccion.
