## 🛠️ Flujo de Trabajo y Características

### 1. Crear y Cambiar de Rama en un mismo paso

Se utiliza `git checkout -b` para crear una rama nueva y cambiar a ella inmediatamente, partiendo desde el punto actual de la rama destino (`main`).

| Comando | Acción |
| :--- | :--- |
| `git checkout -b nueva-funcionalidad` | **Crea y cambia** inmediatamente a la nueva rama. |

### 2. Realizar Cambios y Commit

Una vez en la nueva rama, haces tus modificaciones y las registras:

```bash
# ... realiza cambios en archivos ...
git add .
git commit -m "Implementa el nuevo formulario de contacto"
```

# 🤝 Fusión de Unión Automática (Three-Way Merge)

La Fusión de Unión Automática, también conocida como *Three-Way Merge* (Fusión de Tres Vías), ocurre cuando el historial de la rama principal (destino) ha **divergido** de la rama de trabajo. Es decir, se han añadido **nuevos *commits*** a la rama principal después de que la rama de trabajo fuera creada.

En este escenario, Git no puede simplemente mover el puntero (*Fast-Forward*); debe crear un nuevo *commit* que tiene dos padres: el último *commit* de la rama principal y el último *commit* de la rama fusionada.

---

## 🛠️ Flujo de Trabajo y Características

### 1. Historial Divergente 🌳

* La rama `main` avanzó con *commits* (**C3**) mientras se trabajaba en la rama `feature` (**C4**).
* Git identifica el **punto base común** más reciente (**C2**), el estado del proyecto antes de que las ramas se separaran.
* Git combina los cambios de **C3** y **C4** en un nuevo *commit* (**C5**).



### 2. Comando de Fusión

El comando es el mismo, pero el resultado es diferente:

| Comando | Acción |
| :--- | :--- |
| `git checkout main` | Te posicionas en la rama de destino. |
| `git merge feature` | Inicia la fusión. Git detecta la divergencia y crea un *merge commit* automáticamente. |

### 3. El Merge Commit

* **Creación:** Git intenta resolver todas las diferencias automáticamente. Si lo logra, abre tu editor de texto para que escribas un mensaje de *merge commit* (que suele ser el predeterminado).
* **Resultado:** Se crea un nuevo *commit* de fusión (C5) que une ambos historiales. El puntero de la rama `main` se mueve a este nuevo *commit*.

> **Nota:** Este tipo de fusión *siempre* deja una traza en el historial del repositorio, lo que es útil para saber exactamente cuándo se integró una rama completa.

---

## 🛑 Fusión Manual: Conflicto de Fusión

Si Git encuentra que ambos historiales han modificado las **mismas líneas** en el **mismo archivo**, no puede resolver la diferencia por sí mismo. Esto detiene el proceso de *merge* y resulta en un **conflicto de fusión**.

* **Acción:** Debes editar manualmente los archivos conflictivos, elegir qué cambios mantener, y luego usar `git add` y `git commit` para finalizar la fusión.
