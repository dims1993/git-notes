# Etiquetas (Tags) en Git

Los *tags* se utilizan para marcar puntos específicos e importantes en la historia de tu repositorio, generalmente para identificar lanzamientos de versiones (*releases*). Son inmutables (no deberían cambiarse o moverse una vez creados).

---

## 🛠️ Tipos y Creación de Tags

Hay dos tipos principales de etiquetas:

### 1. Etiquetas Ligeras (*Lightweight Tags*)

Son como una simple rama que no se mueve; solo un puntero a un *commit* específico. Se crean sin metadatos.

| Comando | Acción |
| :--- | :--- |
| `git tag v1.0.0` | Crea una etiqueta ligera llamada `v1.0.0` sobre el *commit* actual. |

### 2. Etiquetas Anotadas (*Annotated Tags*)

Son la mejor opción para lanzamientos públicos. **Almacenan metadatos** completos (nombre del autor del *tag*, email, fecha y un mensaje completo), usando la base de datos de objetos de Git.

| Comando | Acción |
| :--- | :--- |
| `git tag -a v1.0.0 -m "Versión estable con corrección de errores críticos"` | Crea una etiqueta anotada (`-a`) con un mensaje (`-m`). Git también pedirá tu editor para añadir un mensaje si omites `-m`. |

---

## 🔎 Visualización y Gestión

### Listar Tags

Para ver todas las etiquetas creadas en tu repositorio:

```bash
git tag
```

## Mostrar Detalles de un Tag
Para ver toda la información de un tag, incluyendo su mensaje, autor y el commit al que apunta (especialmente útil para Annotated Tags):

```bash
git show v1.0.0
```
