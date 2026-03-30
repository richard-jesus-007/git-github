# 00. Pasos Iniciales: De la Instalación al Repositorio
Este archivo documenta el proceso de preparación del entorno, la configuración de identidad y la creación de la estructura base del curso tras la instalación de Git.

## 1. Descarga e Instalación
Para comenzar, descargamos el instalador oficial compatible con la arquitectura de la **Predator Neo**.

* **Sitio oficial:** [git-scm.com](https://git-scm.com/)
* **Versión utilizada:** `Git-2.53.0.2-64-bit.exe` (Arquitectura x64)


solo poner siguiente siguiente en todas las configuraciones que validaremos despues las configuracion

---

## 2. Vista Inicial Post-Instalación (Git Bash)
Al abrir la terminal por primera vez, nos encontramos con la interfaz de línea de comandos. Es vital entender qué significa cada parte del **Prompt** (indicador de comandos).

Tus datos no seran sismilares el ejemplo es de mi propia teminal
### Ejemplo de mi propia terminal:
```bash
user@Predator-Neo MINGW64 ~
$ git --version
git version 2.53.0.windows.2

user@Predator-Neo MINGW64 ~
$
```
`user`: Usuario actual de la computadora.

`Predator-Neo`: Identificador único del dispositivo (Hostname).

`MINGW64`: Indica el entorno de emulación de Unix (64 bits) que usa Git Bash en Windows.

`~`: Representa el Directorio Raíz (Home) de nuestro sistema de archivos para el usuario actual.

`$`: Indicador de usuario. Significa que la terminal está lista para recibir órdenes y que tienes privilegios de usuario normal.
`git --version`: comando que indica la version de git
`git version 2.53.0.windows.2`: resultado que indica la version de git en el computador

## 3. Identidad en el Sistema (Post-Instalación)
Antes de realizar cualquier operación, se configuró la identidad global en **Git Bash** para asegurar que los créditos de los cambios pertenezcan a mi cuenta de GitHub.

La direccion la estoy sacando de github`-->` foto de perfil`-->` Settings`-->` email


Decidí usar richard-jesus-007 para mantener una identidad técnica consistente, profesional y privada entre mi entorno local y mi perfil global en GitHub. puedes usar el tuyo

"richard-jesus-007" cambia por tu propio usuario
y tambien cambia por tu propio correo de github
"*********+richard-jesus-007@users.noreply.github.com"
```bash
# Configuración del nombre de usuario
git config --global user.name "richard-jesus-007"

# Configuración del correo de privacidad (obtenido de GitHub Settings > Emails)
git config --global user.email "*********+richard-jesus-007@users.noreply.github.com"
```
configuraciones del entorno del trabajo

Para optimizar el flujo de trabajo  se aplicaron las siguientes configuraciones de sistema:

* **Rama Principal:** `` (Estándar de GitHub).
* **Editor de Texto:** `"` (Integración con VS Code).
* **Compatibilidad de archivos:** `git config --global core.autocrlf true` (Corrección de finales de línea Windows/Unix).
```bash
# * **Rama Principal:** `` (Estándar de GitHub).
git config --global init.defaultBranch main

# * **Editor de Texto:** `"` (Integración con VS Code).
git config --global core.editor "code --wait"
# * **Compatibilidad de archivos:** `git config --global core.autocrlf true` (Corrección de finales de línea Windows/Unix).
git config --global core.autocrlf true



```
> [!TIP]
> **VS Code Zoom:** para ajustar el tamaño del texto rápidamente con `Ctrl + Scroll`.

*********
## 4. Creacion de Repositorio Remotoen GitHub

ir a la direccion https://github.com/

hacer el proceso de logeo con tu respestiva cuenta 

escoje la opcion de ``New`` se abriara una opcion `Create a new repository` y `Escribe en repostitory name`: puedes agregar una descripcion
en confioguracion escoje public, add readme (para este caso no) puedes agregar un git ignore y escojer tu licensia para ver que hacen con tu repsositorio



## 5. Vinculación con el Repositorio Remoto


Para trabajar de forma sincronizada, se utilizó el comando de clonación. Esto crea una copia exacta del repositorio de la nube en la carpeta local.

he creado una carpeta `curso-github` dentro `Documents`

Cambia `curso-github` por tu propio nombre de carpeta
cambia https://github.com/richard-jesus-007/git-github.git por tu propia url del repositorio

```bash
# Ubicarse en la carpeta de documentos
cd Documents/curso-github

# Clonar el repositorio
git clone https://github.com/richard-jesus-007/git-github.git

# Entrar a la carpeta del proyecto
cd git-github
```

## 6. Creación de la Estructura de "Wiki"
Se optó por una organización modular para facilitar la consulta rápida de comandos y conceptos. Se crearon los siguientes archivos base:

* `README.md`: Índice principal y presentación.
* `00-pasos-iniciales.md`: Preparación y clonación (Este archivo).
* `01-fundamentos-git.md`: Comandos locales y ciclo de vida.
* `02-flujo-remoto-github.md`: Sincronización y seguridad (Tokens).
* `03-colaboracion-avanzada.md`: Forks, PRs y gestión de ramas.

> 💡 **Tip Técnico:** En VS Code, puedes usar el comando `touch` en la terminal integrada para crear estos archivos rápidamente:
> `touch README.md 00-pasos-iniciales.md 01-fundamentos-git.md 02-flujo-remoto-github.md 03-colaboracion-avanzada.md`

## 7. Paso previo para subir nuevos archivos al reposirotio

## 🔐 Autenticación Segura (Personal Access Tokens)

GitHub ya no permite el uso de contraseñas comunes para operaciones desde la terminal (Git Bash) por razones de seguridad. En su lugar, utilizamos un **PAT (Personal Access Token)**, que actúa como una llave maestra con permisos específicos.

### 🛠️ Pasos para generar el Token
Sigue esta ruta en la interfaz web de GitHub:

1. **Acceso:** Foto de Perfil (derecha superior) → `Settings`.
2. **Desarrollador:** En la barra lateral izquierda, al final: `<> Developer settings`.
3. **Tokens:** `Personal access tokens` → `Tokens (classic)`.
4. **Creación:** Botón `Generate new token` → `Generate new token (classic)`.

#### Configuración recomendada:
* **Note:** `token-de-validacion`
* **Expiration:** `90 days` (recomendado para seguridad).
* **Select scopes:** Selecciona la casilla **`repo`** (esto permite control total sobre tus repositorios privados y públicos).
* **Finalizar:** Clic en `Generate token`.

> [!CAUTION]
> **IMPORTANTE:** Copia tu propio que empieza con `ghp_************************************` y guárdalo en un lugar seguro. **No se volverá a mostrar** y lo necesitarás para tu primer envío desde la terminal.


guarda tu token en la ventana de validacion que se abrira con y ahi valides en una ventana emergente y escoje la opcion de token   `git push origin main`

 `ghp_************************************`



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

# Subir tus nuevos archivos a la nube, aqui te pedira tu token del paso anterior
git push origin main
```
