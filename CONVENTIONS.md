# Convenciones de Proyectos

Estándares que aplico en mis proyectos a partir de mayo 2026.
Proyectos anteriores a esta fecha pueden no seguir estas convenciones.
Cada proyecto puede extender estas convenciones según su naturaleza.

---

## Tabla de contenidos

- [Nombres de repositorios](#nombres-de-repositorios)
- [Nombres de archivos y carpetas](#nombres-de-archivos-y-carpetas)
- [Archivos obligatorios](#archivos-obligatorios)
- [Estructura del README](#estructura-del-readme)
- [Branches](#branches)
- [Commits](#commits)
- [Versionado](#versionado)
- [Código](#código)
- [Licencia](#licencia)

---

## Nombres de repositorios

- Formato: `kebab-case`
- Idioma: español para proyectos universitarios
- Descriptivo pero conciso

---

## Nombres de archivos y carpetas

- Formato: `snake_case`
- Idioma: consistente con el idioma del proyecto

---

## Archivos obligatorios

Todo repositorio debe contener los siguientes archivos en la raíz:

| Archivo | Propósito |
|---------|-----------|
| `README.md` | Descripción e instrucciones del proyecto |
| `CONVENTIONS.md` | Referencia a estas convenciones |
| `LICENSE` | Licencia MIT |
| `CHANGELOG.md` | Historial de cambios por versión |
| `.gitignore` | Archivos excluidos del control de versiones |
| `.editorconfig` | Configuración consistente del editor |

---

## Estructura del README

### Secciones universales (obligatorias)

Los badges se generan con [shields.io](https://shields.io).

```
# Nombre del Proyecto

![Estado]() ![Versión]() ![Licencia]()

Descripción breve.

## Tabla de contenidos
## Descripción
## Características
## Requisitos
## Instalación
## Uso
## Estructura del proyecto
## Versionado
## Licencia
## Autor
```

### Secciones opcionales — Sistemas embebidos

- `## Hardware` — componentes principales del sistema
- `## Firmware` — descripción de la arquitectura del firmware
- `## Esquemático` — diagrama del circuito electrónico
- `## PCB` — diseño de la placa de circuito impreso
- `## Lista de materiales` — componentes con especificaciones y costos
- `## Resultados` — resultados de pruebas y validación
- `## Documentación` — referencia a documentación técnica extensa

---

## Branches

### Modelo: Git Flow

| Branch | Propósito |
|--------|-----------|
| `main` | Código estable y probado. Nunca se trabaja directamente aquí |
| `develop` | Rama de desarrollo principal donde se integra el trabajo |

El resto de branches son temporales — se crean para trabajar y se eliminan al fusionarse.

### Nomenclatura

- Formato: `kebab-case`
- Estructura: `prefijo/descripción-en-español`
- Prefijo en inglés, descripción en español

| Prefijo | Uso |
|---------|-----|
| `feature/` | Nueva funcionalidad |
| `fix/` | Corrección de bug |
| `docs/` | Cambios en documentación |
| `hardware/` | Esquemático, PCB, diseño 3D |
| `test/` | Pruebas y validación |

### Flujo de trabajo

Todo el trabajo sigue este ciclo:

1. Se crea un branch desde `develop` según el tipo de trabajo
2. Se trabaja en ese branch con commits incrementales
3. Al completar el trabajo, el branch se fusiona de vuelta a `develop`
4. Cuando `develop` tiene un conjunto estable de cambios probados, se fusiona a `main`
5. La fusión a `main` genera un nuevo tag de versión
6. El branch temporal se elimina tras la fusión

`main` siempre refleja el estado estable más reciente del proyecto.

---

## Commits

### Formato: Conventional Commits

```
tipo: descripción corta

Cuerpo opcional explicando el por qué del cambio.
```

### Reglas

- Idioma: español
- Estilo: imperativo
- Longitud máxima: 72 caracteres
- Sin punto al final de la descripción

### Prefijos

| Prefijo | Uso |
|---------|-----|
| `feat:` | Nueva funcionalidad |
| `fix:` | Corrección de bug |
| `docs:` | Cambios en documentación |
| `style:` | Formato y espacios sin cambio de lógica |
| `refactor:` | Reestructuración sin cambiar funcionalidad |
| `test:` | Agregar o modificar pruebas |
| `chore:` | Mantenimiento y configuración |
| `hardware:` | Cambios en esquemático, PCB o diseño 3D |

---

## Versionado

### Formato: SemVer (Semantic Versioning)

```
vMAJOR.MINOR.PATCH
```

| Campo | Cuándo se incrementa |
|-------|---------------------|
| `MAJOR` | Cambio grande que rompe compatibilidad |
| `MINOR` | Nueva funcionalidad sin romper lo existente |
| `PATCH` | Corrección de bugs |

- Las versiones se marcan con Git tags al fusionar a `main`
- Cada versión se documenta en `CHANGELOG.md`

---

## Código

### Comentarios

- Idioma: español
- Estilo: Doxygen

```c
/**
 * @brief Descripción breve de la función.
 *
 * @param parametro Descripción del parámetro.
 * @return Descripción del valor de retorno.
 */
```

---

## Licencia

Todos los proyectos usan licencia **MIT** salvo indicación contraria en el repositorio específico.

---

*Última actualización: mayo 2026*
