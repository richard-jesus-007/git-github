# 00. Pasos Iniciales: De la Instalación al Repositorio
Este archivo documenta el proceso de preparación del entorno, la configuración de identidad y la creación de la estructura base del curso tras la instalación de Git.

## 1. Descarga e Instalación
Para comenzar, descargamos el instalador oficial compatible con la arquitectura de tu sistema operativo, para mi caso **Windows 11**.

* **Sitio oficial:** [git-scm.com](https://git-scm.com/)
* **Versión utilizada:** `Git-2.53.0.2-64-bit.exe` (Arquitectura x64)


> **Instrucción:** Durante la instalación, puedes dejar las opciones por defecto ("Next" en todo), ya que ajustaremos las configuraciones críticas manualmente desde la terminal más adelante.

---

## 2. Vista Inicial Post-Instalación (Git Bash)
Al abrir la terminal por primera vez, nos encontramos con la interfaz de línea de comandos. Es vital entender qué significa cada parte del **Prompt** (indicador de comandos).

Tus datos no seran iguales a el ejemplo, es de mi propia terminal 
### Ejemplo de mi propia terminal:
```bash
user@Predator-Neo MINGW64 ~
$ git --version
git version 2.53.0.windows.2

user@Predator-Neo MINGW64 ~
$
```
**Anatomía del Prompt:**
* `user`: Usuario actual de la computadora.
* `Predator-Neo`: Identificador único del dispositivo (Hostname).
* `MINGW64`: Entorno de emulación de Unix (64 bits) en Windows.
* `~`: Representa el **Directorio Raíz** (Home) de tu sistema de archivos.
* `$`: Indicador de que la terminal está lista y eres un usuario normal.
* `git --version`: Comando que ejecute para verificar la versión instalada.
* `git version 2.53.0.windows.2`: Resultado del anterior comando.

## 3. Identidad en el Sistema (Post-Instalación)
Antes de realizar cualquier operación, se configuró la identidad global en **Git Bash** para asegurar que los créditos de los cambios pertenezcan a mi cuenta de GitHub.

> **Nota del Autor:** Decidí usar mi usuario de GitHub para mantener una identidad técnica consistente, profesional y privada entre mi entorno local y mi perfil global. Puedes obtener tu correo de privacidad en: **Foto de perfil -> Settings -> Emails**.

### Configuración de Identidad
Sustituye los valores de `"richard-jesus-007"`, `"*********+richard-jesus-007@users.noreply.github.com"` y por tu propio usuario y correo:

Configuración de mi nombre de autor
```bash
git config --global user.name "richard-jesus-007"
```

Configuración de mi correo de privacidad
```bash
git config --global user.email "*********+richard-jesus-007@users.noreply.github.com"
```
### Configuración del Entorno de Trabajo
Aplica estos comandos para optimizar cómo Git interactúa con tu sistema y con VS Code:
estos valores puedes copiarlos tal como estan

Definir 'main' como la rama principal por defecto
```bash
git config --global init.defaultBranch main
```
Vincular VS Code como editor de texto predeterminado
```bash
git config --global core.editor "code --wait"
```bash

# Corregir automáticamente los finales de línea (Windows/Unix)
```bash
git config --global core.autocrlf true
```

> [!TIP]
> **git Bash:** para ajustar el tamaño del texto rápidamente con `Ctrl + Scroll`.

## 4. Creación del Repositorio Remoto en GitHub
Dirígete a [github.com](https://github.com/), inicia sesión y sigue estos pasos:

1. Haz clic en el botón **"New"** para crear un repositorio.
2. En **Repository name**, escribe el nombre de tu proyecto para este ejemplo: `git-github`.
3. Selecciona **Public** y, para este ejercicio, **no** marques la casilla de "Add a README file".
4. Los demas valores de **.gitignore** y **license** los dejamos por defecto.
4. Haz clic en **Create repository**.

## 5. Vinculación con el Repositorio Remoto
Para trabajar de forma sincronizada, se utilizó el comando de clonación. Esto crea una copia exacta del repositorio de la nube en la carpeta local.

> **Mi estructura:** He creado una carpeta llamada `curso-github` dentro de mi carpeta de `Documents` para organizar mis estudios.

```bash
# Ubicarse en la carpeta de documentos
cd Documents/curso-github

# Clonar el repositorio
git clone https://github.com/richard-jesus-007/git-github.git

# Entrar a la carpeta del proyecto
cd git-github
```

## 6. Creación de la Estructura de "Wiki"
Se optó por una organización modular para facilitar la consulta rápida de comandos y conceptos. Se crearon los siguientes archivos base a medida que cresca el proyecto ire agregando mas archivos:

* `README.md`: Índice principal y presentación.
* `00-pasos-iniciales.md`: Preparación y clonación (Este archivo).
* `01-fundamentos-git.md`: Comandos locales y ciclo de vida.
* `02-flujo-remoto-github.md`: Sincronización y seguridad (Tokens).
* `03-colaboracion-avanzada.md`: Forks, PRs y gestión de ramas.

> 💡 **Tip Técnico:** En VS Code, puedes usar el comando `touch` en la terminal integrada para crear estos archivos rápidamente:
> `touch README.md 00-pasos-iniciales.md 01-fundamentos-git.md 02-flujo-remoto-github.md 03-colaboracion-avanzada.md`

## 7. Autenticación Segura (Personal Access Tokens)
GitHub requiere un **PAT (Personal Access Token)** para subir cambios desde la terminal.

### Pasos para generar tu Token:
1. **Settings** -> **Developer settings** -> **Personal access tokens** -> **Tokens (classic)**.
2. Genera un nuevo token con una nota descriptiva y una expiración de **90 días**.
3. **Importante:** Selecciona el scope **`repo`**.

> [!CAUTION]
> **SEGURIDAD:** Copia tu código `ghp_***` inmediatamente. No se volverá a mostrar. **Nunca lo incluyas en tus archivos de texto públicos.**

## 8. Estado Actual del Repositorio

Al haber creado archivos nuevos, Git los reconoce como **Untracked** (No rastreados). El siguiente paso es agregarlos al área de preparación y confirmar el primer cambio estructural.

```bash
# situarce en la carpeta actual del proyecto
cd Documents/curso-github

# Verificar los nuevos archivos creados
git status

# Agregar todos los archivos al Staging Area
git add .

# Realizar el commit inicial de la estructura
git commit -m "Estructura inicial de la Wiki de aprendizaje"

# Subo los archivos a GitHub
# Aquí se abrirá una ventana emergente: elige "Token" y pega tu código ghp_...
git push origin main
```
