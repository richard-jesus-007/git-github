¡Perfecto! El archivo **`03-colaboracion-avanzada.md`** es el nivel "Pro". Aquí es donde dejas de trabajar en una sola línea recta y aprendes a crear "universos paralelos" (Ramas) para experimentar sin romper tu código principal.

Siguiendo tu esquema: **instrucciones en 2da persona** y **mis notas/ejemplos en 1ra persona**.

---

# 🚀 03. Colaboración Avanzada: Ramas, Forks y Pull Requests

Este archivo documenta cómo trabajar en proyectos complejos, colaborar con otros y organizar nuevas funcionalidades sin poner en riesgo la versión estable del proyecto.

## 1. Gestión de Ramas (Branches)
Una **Rama** es una línea de tiempo independiente. Úsala para probar ideas nuevas o arreglar errores sin afectar la rama `main`.



### Comandos de Ramas:
```bash
# Crear una nueva rama para una funcionalidad
git branch nueva-funcion

# Cambiarme a esa rama para empezar a trabajar
git checkout nueva-funcion

# (Atajo) Crear y cambiarme al mismo tiempo:
git checkout -b fix-error-calculo
```

> **Mi flujo de trabajo:** En mis proyectos de ingeniería, nunca trabajo directamente en `main`. Siempre creo una rama llamada `desarrollo` o `test-opensees`. Si algo sale mal, simplemente borro la rama y mi `main` sigue intacto.

---

## 2. Fusión de Cambios (Merge)
Cuando tu trabajo en la rama secundaria está listo y probado, debes integrarlo a la rama principal.

### Cómo unir las ramas:
1. Regresa a la rama que recibirá los cambios (normalmente `main`).
2. Ejecuta el comando de unión.

```bash
# 1. Regreso a la rama principal
git checkout main

# 2. Traigo los cambios de mi otra rama
git merge nueva-funcion
```

---

## 3. Trabajo con Repositorios Ajenos (Fork)
Si encuentras un proyecto interesante en GitHub (por ejemplo, una librería de TinyML) y quieres proponer una mejora, no puedes escribir directamente en él. Debes hacer un **Fork**.

* **Fork:** Crea una copia exacta del repositorio ajeno en **tu propia cuenta** de GitHub.
* **Pull Request (PR):** Es una petición formal que envías al dueño original del proyecto diciéndole: *"He hecho estos cambios en mi copia (fork), ¿te gustaría integrarlos en tu proyecto oficial?"*.



---

## 4. Resolución de Conflictos
A veces, Git no sabe cómo combinar dos archivos porque se modificó la misma línea en dos lugares distintos. Esto genera un **Merge Conflict**.

> **Mi consejo para resolverlo:** Cuando esto sucede, VS Code marcará las líneas en conflicto con colores. Debes elegir manualmente qué versión conservar ("Accept Current Change" o "Accept Incoming Change"), guardar el archivo y hacer un nuevo `commit`.

---

## 5. Glosario para el Colaborador
Para que hables el mismo idioma que otros desarrolladores en GitHub:

* **Upstream:** El repositorio original de donde hiciste el Fork.
* **Origin:** Tu copia personal en la nube.
* **Issue:** Un "ticket" o reporte donde se discute un error o una nueva idea.

---

### ✅ Validación Final de la Wiki
Con este archivo completas tu **Estructura de 4 niveles**. 

**¿Cómo te sientes con esta organización?** Ahora tienes:
* **00:** El inicio y configuración en tu **Predator Neo**.
* **01:** El ciclo de vida local (Rojo -> Verde -> Commit).
* **02:** El puente con la nube (Push/Pull/Tokens).
* **03:** El trabajo avanzado (Ramas y Colaboración).

**¿Te gustaría que hagamos un último `git status` y un `push` general para asegurar que toda tu Wiki ya está respaldada en GitHub con estos 4 archivos finales?**