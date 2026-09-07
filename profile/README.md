# 📚 Convenciones de commits

Esta guía explica las convenciones utilizadas para escribir mensajes de commit claros, consistentes y fáciles de entender.

La mayoría de los proyectos utilizan una convención basada en **Conventional Commits**, que permite identificar rápidamente qué tipo de cambio se ha realizado.

---

## 📌 Formato de un commit

La estructura básica es:

```text
tipo: descripción
```

Por ejemplo:

```text
feat: añadir sistema de autenticación
```

También podemos añadir un `scope` para indicar qué parte del proyecto se ha modificado:

```text
feat(auth): añadir login con Google
```

La estructura completa sería:

```text
tipo(scope): descripción

[cuerpo opcional]

[footer opcional]
```

---

# 🏷️ Tipos de commits

## ✨ `feat`

Se utiliza cuando añadimos una **nueva funcionalidad** al proyecto.

```text
feat: añadir sistema de registro
```

```text
feat(cart): permitir eliminar productos del carrito
```

### Ejemplos

* Añadir un nuevo endpoint
* Crear una nueva página
* Añadir un nuevo componente
* Incorporar una nueva funcionalidad

---

## 🐛 `fix`

Se utiliza cuando solucionamos un **bug o error**.

```text
fix: corregir error al iniciar sesión
```

```text
fix(api): corregir respuesta incorrecta del endpoint
```

### Ejemplos

* Corregir un botón que no funciona
* Solucionar un error en una API
* Corregir un cálculo incorrecto
* Resolver un problema de validación

---

## 📖 `docs`

Se utiliza para cambios relacionados exclusivamente con la **documentación**.

```text
docs: actualizar README
```

```text
docs(api): añadir documentación de los endpoints
```

### Ejemplos

* Actualizar `README.md`
* Añadir documentación
* Corregir errores de escritura
* Añadir comentarios explicativos

---

## ♻️ `refactor`

Se utiliza cuando modificamos el código para **mejorarlo internamente sin cambiar su comportamiento**.

```text
refactor: simplificar lógica de autenticación
```

```text
refactor(users): separar lógica de usuarios en un servicio
```

### Ejemplos

* Eliminar código duplicado
* Dividir una función demasiado grande
* Mejorar la estructura del código
* Cambiar la implementación sin modificar el resultado

> 💡 Si estás corrigiendo un bug → `fix`
> Si estás añadiendo funcionalidad → `feat`
> Si estás mejorando el código sin cambiar su comportamiento → `refactor`

---

## 🎨 `style`

Se utiliza para cambios de **formato o estilo del código** que no modifican su funcionamiento.

```text
style: aplicar formato a los componentes
```

### Ejemplos

* Formatear código
* Cambiar indentación
* Añadir o eliminar espacios
* Corregir puntos y comas
* Aplicar Prettier

> ⚠️ `style` normalmente se refiere al formato del código, no necesariamente a estilos visuales de la aplicación.

---

## ⚡ `perf`

Se utiliza para mejoras de **rendimiento**.

```text
perf: mejorar rendimiento de la carga de usuarios
```

```text
perf(images): optimizar carga de imágenes
```

### Ejemplos

* Reducir tiempos de carga
* Optimizar consultas
* Mejorar algoritmos
* Reducir consumo de memoria
* Optimizar imágenes

---

## 🧪 `test`

Se utiliza cuando añadimos o modificamos **tests**.

```text
test: añadir tests para el servicio de usuarios
```

```text
test(auth): añadir tests para el login
```

### Ejemplos

* Añadir tests unitarios
* Añadir tests de integración
* Corregir tests
* Modificar casos de prueba

---

## 🔧 `build`

Se utiliza para cambios relacionados con el **sistema de build o dependencias**.

```text
build: actualizar versión de Node
```

```text
build: añadir dependencia de React
```

### Ejemplos

* Modificar `package.json`
* Actualizar dependencias
* Cambiar configuración de Webpack
* Cambiar configuración de Vite
* Modificar el sistema de compilación

---

## 👷 `ci`

Se utiliza para cambios relacionados con **CI/CD (Continuous Integration / Continuous Deployment)**.

```text
ci: añadir workflow de GitHub Actions
```

```text
ci: ejecutar tests automáticamente
```

### Ejemplos

* Crear un workflow de GitHub Actions
* Modificar pipelines
* Configurar despliegues automáticos
* Añadir comprobaciones automáticas

---

## 🔨 `chore`

Se utiliza para tareas de **mantenimiento** que no afectan directamente a la funcionalidad de la aplicación.

```text
chore: actualizar dependencias
```

```text
chore: eliminar archivos innecesarios
```

### Ejemplos

* Actualizar herramientas
* Limpiar archivos
* Modificar configuraciones menores
* Tareas de mantenimiento

---

## ⏪ `revert`

Se utiliza para **revertir un commit anterior**.

```text
revert: revertir feat(auth): añadir login con Google
```

Normalmente Git genera este mensaje automáticamente cuando utilizamos:

```bash
git revert <commit>
```

---

# 📋 Resumen rápido

| Tipo       | Uso                                       |
| ---------- | ----------------------------------------- |
| `feat`     | Nueva funcionalidad                       |
| `fix`      | Corrección de un bug                      |
| `docs`     | Documentación                             |
| `style`    | Formato del código                        |
| `refactor` | Mejorar código sin cambiar comportamiento |
| `perf`     | Mejorar rendimiento                       |
| `test`     | Tests                                     |
| `build`    | Build y dependencias                      |
| `ci`       | CI/CD                                     |
| `chore`    | Mantenimiento                             |
| `revert`   | Revertir un commit                        |

---

# 💡 Ejemplos reales

### Nueva funcionalidad

```bash
git commit -m "feat: añadir recuperación de contraseña"
```

### Corrección de un bug

```bash
git commit -m "fix: corregir validación del formulario"
```

### Documentación

```bash
git commit -m "docs: actualizar instrucciones de instalación"
```

### Refactorización

```bash
git commit -m "refactor: simplificar servicio de autenticación"
```

### Tests

```bash
git commit -m "test: añadir tests para usuarios"
```

### Rendimiento

```bash
git commit -m "perf: optimizar consulta de productos"
```

### CI/CD

```bash
git commit -m "ci: añadir workflow para ejecutar tests"
```

### Dependencias

```bash
git commit -m "build: actualizar dependencias"
```

---

# 🎯 ¿Qué tipo debo utilizar?

Una forma sencilla de decidirlo:

```text
¿He añadido algo nuevo?
        │
        └── Sí → feat

¿He solucionado un bug?
        │
        └── Sí → fix

¿He cambiado únicamente la documentación?
        │
        └── Sí → docs

¿He mejorado el código sin cambiar su comportamiento?
        │
        └── Sí → refactor

¿He mejorado el rendimiento?
        │
        └── Sí → perf

¿He añadido/modificado tests?
        │
        └── Sí → test

¿He cambiado el sistema de build o dependencias?
        │
        └── Sí → build

¿He cambiado CI/CD?
        │
        └── Sí → ci

¿Es una tarea de mantenimiento?
        │
        └── Sí → chore
```

---

# 📝 Buenas prácticas

## 1. Utiliza el imperativo

Es recomendable escribir:

```text
feat: añadir autenticación
```

En lugar de:

```text
feat: añadida autenticación
```

---

## 2. Mantén el mensaje corto

Intenta que la primera línea sea breve y fácil de leer.

✅ Bien:

```text
fix: corregir error de validación
```

❌ Demasiado largo:

```text
fix: corregir el problema que ocurría cuando un usuario intentaba enviar el formulario sin introducir todos los campos obligatorios
```

Si necesitas explicar más información, puedes utilizar el cuerpo del commit.

---

## 3. No utilices mensajes demasiado genéricos

❌ Evitar:

```text
fix: cambios
```

```text
feat: cosas nuevas
```

```text
chore: modificaciones
```

✅ Mejor:

```text
fix: corregir error al calcular el total del carrito
```

```text
feat: añadir filtro por categoría
```

---

# 📦 Scope

El `scope` es opcional y sirve para indicar **qué parte del proyecto se ha modificado**.

Formato:

```text
tipo(scope): descripción
```

Por ejemplo:

```text
feat(auth): añadir login con Google
```

```text
fix(cart): corregir cálculo del precio total
```

```text
docs(api): actualizar documentación
```

Algunos scopes habituales:

```text
auth
api
ui
database
users
cart
payments
frontend
backend
```

El scope depende de la estructura y necesidades de cada proyecto.

---

# 🚨 Breaking Changes

Cuando un cambio rompe la compatibilidad con una funcionalidad o API existente, podemos indicarlo con `!`.

```text
feat!: cambiar estructura de la API
```

También podemos utilizar:

```text
feat(api)!: eliminar endpoint antiguo
```

Un **breaking change** significa que los usuarios o desarrolladores tendrán que realizar cambios para adaptarse a la nueva versión.

También puede explicarse en el footer:

```text
feat(api): cambiar formato de respuesta

BREAKING CHANGE: el campo `user` ahora se devuelve como `data.user`.
```

---

# 🌳 Ejemplo de historial

Un historial bien organizado podría verse así:

```text
feat: añadir sistema de autenticación
feat(auth): añadir login con Google
test(auth): añadir tests de autenticación
fix(auth): corregir expiración del token
refactor(auth): simplificar middleware
docs: actualizar documentación de autenticación
perf(api): optimizar consulta de usuarios
ci: añadir workflow de tests
chore: actualizar dependencias
```

Esto hace que el historial de Git sea mucho más fácil de entender.

---

# 🚀 Regla rápida

Si tienes dudas, piensa:

> **¿Qué ha cambiado principalmente en este commit?**

| Cambio                 | Commit     |
| ---------------------- | ---------- |
| 🆕 Nueva funcionalidad | `feat`     |
| 🐛 Bug corregido       | `fix`      |
| 📚 Documentación       | `docs`     |
| ♻️ Código reorganizado | `refactor` |
| ⚡ Rendimiento          | `perf`     |
| 🧪 Tests               | `test`     |
| 🎨 Formato             | `style`    |
| 🔧 Build/dependencias  | `build`    |
| 👷 CI/CD               | `ci`       |
| 🧹 Mantenimiento       | `chore`    |
| ⏪ Deshacer commit      | `revert`   |

---

## ⭐ Ejemplo recomendado

```bash
git add .

git commit -m "feat(auth): añadir autenticación con Google"

git push
```

Mantener una convención de commits consistente ayuda a que el proyecto sea más profesional, facilita revisar el historial y puede permitir automatizar procesos como **changelogs, releases y versionado semántico**.
