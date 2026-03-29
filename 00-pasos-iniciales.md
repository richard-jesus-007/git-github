# 🟢 00. Pasos Iniciales: De la Instalación al Repositorio
Este archivo documenta el proceso de preparación del entorno, la configuración de identidad y la creación de la estructura base del curso tras la instalación de Git.

## 1. Identidad en el Sistema (Post-Instalación)
Antes de realizar cualquier operación, se configuró la identidad global en **Git Bash** para asegurar que los créditos de los cambios pertenezcan a mi cuenta de GitHub.

```bash
# Configuración del nombre de usuario
git config --global user.name "richard-jesus-007"

# Configuración del correo de privacidad (obtenido de GitHub Settings > Emails)
git config --global user.email "1########+richard-jesus-007@users.noreply.github.com"
```

## 2. Vinculación con el Repositorio Remoto

> [!IMPORTANT]
> Cabe mencionar que primero se creó un repositorio **git-github** en la web de forma pública y **sin README.md** (repositorio vacío).

Para trabajar de forma sincronizada, se utilizó el comando de clonación. Esto crea una copia exacta del repositorio de la nube en la carpeta local.

```bash
# Ubicarse en la carpeta de documentos
cd Documents/curso-github

# Clonar el repositorio
git clone https://github.com/richard-jesus-007/git-github.git

# Entrar a la carpeta del proyecto
cd git-github
```



## 3. Creación de la Estructura de "Wiki"
Se optó por una organización modular para facilitar la consulta rápida de comandos y conceptos. Se crearon los siguientes archivos base:

* `README.md`: Índice principal y presentación.
* `00-pasos-iniciales.md`: Preparación y clonación (Este archivo).
* `01-fundamentos-git.md`: Comandos locales y ciclo de vida.
* `02-flujo-remoto-github.md`: Sincronización y seguridad (Tokens).
* `03-colaboracion-avanzada.md`: Forks, PRs y gestión de ramas.

> 💡 **Tip Técnico:** En VS Code, puedes usar el comando `touch` en la terminal integrada para crear estos archivos rápidamente:
> `touch README.md 00-pasos-iniciales.md 01-fundamentos-git.md 02-flujo-remoto-github.md 03-colaboracion-avanzada.md`

## 4. Estado Actual del Repositorio
Al haber creado archivos nuevos, Git los reconoce como **Untracked** (No rastreados). El siguiente paso es agregarlos al área de preparación y confirmar el primer cambio estructural.

```bash
# Verificar los nuevos archivos creados
git status

# Agregar todos los archivos al Staging Area
git add .

# Realizar el commit inicial de la estructura
git commit -m "Estructura inicial de la Wiki de aprendizaje"

# Subir tus nuevos archivos a la nube
git push origin main
```
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
> **IMPORTANTE:** Copia el código que empieza con `ghp_...` y guárdalo en un lugar seguro. **No se volverá a mostrar** y lo necesitarás para tu primer envío desde la terminal.

---

### 🚀 Uso del Token en la Terminal
en la ventana emergente: peguemos el toquen *ghp_xi####################...*


