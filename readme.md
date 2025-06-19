# 📦 GitHub Actions Learning

Aprende los fundamentos de **GitHub Actions**, la herramienta de integración y entrega continua (CI/CD) de GitHub para automatizar tus flujos de trabajo.

---

## 📁 Workflow

Un **workflow** es un archivo `.yml` ubicado en `.github/workflows/`.  
Define una serie de trabajos (jobs) automatizados que se ejecutan en respuesta a eventos.

---

## 🚀 Event (Evento)

Un **evento** es lo que dispara (activa) el workflow. Ejemplos comunes:

- `push` → al hacer push
- `pull_request` → al abrir o actualizar un PR
- `schedule` → ejecución programada (cron)
- `workflow_dispatch` → ejecución manual

---

## 🧱 Job

Un **job** es un bloque de trabajo dentro de un workflow.  
Cada job se ejecuta en un **runner**.  
Puedes usar `needs:` para que un job espere a otro.

---

## 🔹 Step

Un **step** es una acción individual dentro de un job.  
Puede ser un comando `run:` o una `action:`.

---

## 🔁 Action

Una **action** es un bloque de código reutilizable que realiza una tarea específica.  
Ejemplos comunes:

- `actions/checkout` → clona tu repositorio
- `actions/setup-node` → instala Node.js
- `actions/upload-artifact` → guarda archivos del workflow

---

## 🖥️ Runner

El **runner** es el entorno donde se ejecutan los jobs.  
GitHub ofrece runners en la nube:

- `ubuntu-latest`
- `windows-latest`
- `macos-latest`

También puedes usar runners **autohospedados**.

---

## 🌐 Contextos

Los **contextos** te permiten acceder a información útil del entorno.  
Se acceden con `${{ ... }}`.

| Contexto               | Descripción                            |
|------------------------|-----------------------------------------|
| `github.ref`           | Rama o tag del evento                   |
| `github.actor`         | Usuario que inició el evento            |
| `env.MI_VAR`           | Variable de entorno definida por ti     |
| `steps.step_id.outputs.X` | Output de un paso anterior          |