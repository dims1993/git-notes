# 🗒️ Comandos Fundamentales de Git: `add` y `commit`

## `git add`

Git no guarda automáticamente los cambios que haces. Hay que decirle qué archivos quieres preparar para guardar en el **área de preparación** (*staging area*).

> **Propósito:** Selecciona los archivos que quieres incluir en tu próximo "snapshot" del proyecto.

### Sintaxis Común

* **Añadir un archivo específico:**
    ```bash
    git add script.py
    ```
* **Añadir todos los archivos modificados en el proyecto:**
    ```bash
    git add .
    ```
* **Añadir archivos por patrón/extensión:**
    ```bash
    git add *.html
    # Nota: A veces es necesario especificar el directorio
    git add /js*.js
    ```
* **Añadir todos los archivos dentro de una carpeta (y sus subcarpetas):**
    ```bash
    git add css/
    ```

### Comprobar Staging Area
Para ver qué archivos están preparados o modificados:
```bash
git status
  ```
## `git commit`

Cuando haces un *commit*, estás guardando un **punto en el tiempo** del estado de tu proyecto.

> `git commit` crea una nueva versión (*snapshot*) con los cambios añadidos previamente con `git add`.

* **Elementos del Commit:**
    * Los cambios añadidos con `git add`.
    * Un **mensaje descriptivo** que explica qué hiciste (se añade con `-m "mensaje"`).

### Sintaxis y Ejemplos

* **Crear un nuevo commit:**
    ```bash
    git commit -m "Agrega función para calcular promedio"
    ```

* **Añadir y Commit (Solo archivos ya rastreados):**
    Combina `git add` y `git commit` en una sola línea. **Solo** funciona para archivos que ya están siendo rastreados (*tracked*) por Git.
    ```bash
    git commit -am "mensaje"
    ```

* **Modificar el último commit:**
    Permite cambiar el mensaje o añadir más archivos al último *commit* realizado.
    ```bash
    git commit --amend -m "mensaje corregido"
    ```

---

## Historial de Commits (`git log`)

Utiliza este comando para ver el historial de commits en Git.

* **Ver el historial completo:**
    ```bash
    git log
    ```
* **Ver el historial de manera resumida (un commit por línea):**
    ```bash
    git log --oneline
    ```


