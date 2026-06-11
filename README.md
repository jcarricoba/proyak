# Proyak · PMO Ligera

> **⚠ Proyecto descontinuado — sin mantenimiento activo.**
> El código queda archivado y la app sigue funcionando indefinidamente en modo local.
> Ver sección [Estado del proyecto](#estado-del-proyecto) para más detalle.

Herramienta de gestión de proyectos pensada para equipos de implantación de software (ERP, ITSM, BPM y similares). Sin instalación, sin licencias, funciona desde el navegador.

**[→ Abrir app](https://jcarricoba.github.io/proyak)**

---

## Estado del proyecto

**Descontinuado a junio de 2026.** No hay usuarios activos ni mantenimiento previsto.

La app **funciona indefinidamente en modo local** sin depender de ningún backend:
- Los datos se guardan en `localStorage` del navegador (persisten entre recargas).
- Opcionalmente se pueden conectar a un archivo `proyak-data.json` en carpeta local, OneDrive o Dropbox mediante la File System Access API.

El código de sincronización con Firebase está **desactivado por flag** (`CLOUD_ENABLED = false` al inicio del script). El servicio de Firebase asociado también está apagado. Cualquiera puede hacer un fork, crear su propio proyecto Firebase y cambiar el flag a `true` para reactivar la nube.

---

## Qué hace

- **Portfolio de proyectos** con estado semáforo, progreso, jornadas estimadas/consumidas e indicadores económicos.
- **Pipeline de preventa** para seguir oportunidades desde el interés inicial hasta la conversión en proyecto.
- **Histórico** de proyectos cerrados con KPIs de desviación y lecciones aprendidas centralizadas y filtrables.
- **Ficha de proyecto** con pestañas para stakeholders, contexto, documentos, riesgos y comentarios.
- **Gestión de riesgos** por proyecto: probabilidad, impacto, acción prevista y estado (abierto/cerrado).
- **Comentarios** por proyecto, editables y borrables.
- **Presupuesto** desglosado por líneas con cálculo de margen.

## Datos

- Sin backend ni base de datos propia.
- Los datos se guardan en `localStorage` del navegador.
- Se puede conectar una carpeta local (File System Access API) para guardar un JSON de respaldo automático en cada cambio.

## Stack

HTML + JS vanilla. Sin frameworks, sin dependencias de build. Un único archivo `index.html`.

## Desarrollo local

Basta con abrir `index.html` en el navegador. No hay proceso de build.

```bash
git clone https://github.com/jcarricoba/proyak.git
cd proyak
open index.html
```

## Reactivar la nube (fork)

1. Crea un proyecto en [Firebase Console](https://console.firebase.google.com).
2. Sustituye el objeto `firebaseConfig` en `index.html` por el de tu proyecto.
3. Activa Authentication (proveedor Google) y Firestore.
4. Cambia `const CLOUD_ENABLED = false` a `true`.
