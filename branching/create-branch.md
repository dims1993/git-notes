# Fusión Fast-Forward (Avance Rápido) en Git

El *Fast-Forward* (Avance Rápido) es el método de fusión más sencillo en Git. Ocurre cuando no hay **conflictos** ni **nuevos commits** en la rama principal (destino) desde que se creó la rama de trabajo.

En lugar de crear un nuevo *commit* de fusión, Git simplemente mueve el puntero de la rama de destino hacia el último *commit* de la rama que se está fusionando.

---

## Flujo de Trabajo y Comandos

Este es el proceso típico para crear, trabajar y fusionar una nueva característica usando Fast-Forward:

### 1. Crear y Cambiar de Rama

Primero, asegúrate de estar en la rama principal (`main` o `master`) y crea una nueva rama para tu trabajo:

| Comando | Acción |
| :--- | :--- |
| `git branch nueva-funcionalidad` | Crea una nueva rama llamada `nueva-funcionalidad`. |
| `git checkout nueva-funcionalidad` | **Cambia** a la nueva rama para empezar a trabajar. |

### 2. Realizar Cambios y Commit

Una vez en la nueva rama, haces tus modificaciones y las registras:

```bash
# ... realiza cambios en archivos ...
git add .
git commit -m "Implementa el nuevo formulario de contacto"
```

### 3. Fusionar (Fast-Forward)

Vuelve a la rama principal y realiza la fusión. Dado que la rama principal (`main`) **no ha tenido nuevos *commits*** mientras trabajabas, Git realiza automáticamente una fusión **Fast-Forward**.

| Comando | Acción |
| :--- | :--- |
| `git checkout main` | Vuelve a la rama principal. |
| `git merge nueva-funcionalidad` | **Fusiona** los *commits* de la rama secundaria en la rama `main`. |

> **Resultado:** El puntero de la rama `main` se mueve hacia adelante para apuntar al último *commit* de `nueva-funcionalidad`. **No se crea un *commit* de fusión adicional.**

### 4. Eliminar la Rama 🗑️

Una vez fusionada la rama de trabajo, ya no es necesaria y es buena práctica eliminarla para mantener limpio el repositorio.

| Comando | Descripción |
| :--- | :--- |
| `git branch -d nueva-funcionalidad` | **Eliminación Segura** (*safe delete*). Solo elimina la rama si ha sido fusionada completamente en la rama actual (o en su *upstream*). |
| `git branch -D nueva-funcionalidad` | **Eliminación Forzosa**. Elimina la rama sin importar si ha sido fusionada o si contiene *commits* sin integrar. (`-D` es el atajo para `-d --force`). |

### Forzar la Fusión (¡Uso Avanzado!) ⚙️

El parámetro `-f` o `--ff` (junto con `--no-ff`) se usa en el comando `git merge` para controlar **cómo** se realiza la fusión, incluso si es posible hacer *Fast-Forward*.

| Comando | Efecto |
| :--- | :--- |
| `git merge --no-ff nueva-funcionalidad` | **Fuerza la creación de un *commit* de fusión** (*merge commit*), incluso si se puede hacer *Fast-Forward*. Esto es útil para mantener un registro explícito de dónde y cuándo ocurrió la fusión. |
| `git merge --ff-only nueva-funcionalidad` | **Solo permite la fusión si es posible hacer *Fast-Forward***. Si hay historial divergente (*commits* nuevos en la rama destino), el comando fallará y no fusionará. |


