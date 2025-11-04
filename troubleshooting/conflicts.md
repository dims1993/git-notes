# 💥 Gestión de Conflictos de Fusión (`Merge Conflicts`)

Un **conflicto de fusión** (*merge conflict*) ocurre cuando Git no puede resolver automáticamente las diferencias entre dos ramas porque ambas modificaron las **mismas líneas** en el **mismo archivo**, o una rama eliminó un archivo que la otra modificó.

Cuando esto pasa, Git **detiene el proceso de fusión** y te pide que resuelvas el problema manualmente.

---

## 🛑 Detección y Estado del Conflicto

### 1. Inicio de la Fusión

El proceso comienza con el comando de fusión habitual, pero Git te notificará del conflicto:

```bash
git merge otra-rama
# Output de Git:
# Auto-merging archivo_conflictivo.txt
# CONFLICT (content): Merge conflict in archivo_conflictivo.txt
# Automatic merge failed; fix conflicts and then commit the result.
```

### 2. Comprobar el Estado
El comando git status se vuelve crucial en este punto.

### 3. Marcadores de Conflicto
Git inserta marcadores especiales en los archivos afectados para mostrar dónde se superponen los cambios:

```bash
<<<<<<< HEAD: Marca el inicio de los cambios en la rama actual.

=======: Separa los cambios de las dos ramas.

>>>>>>> rama-con-conflicto: Marca el final de los cambios de la rama que intentas fusionar.
```

## ✅ Pasos para Resolver Conflictos
La resolución es un proceso de tres pasos:

### Paso 1: Editar el Archivo
Abre el archivo conflictivo en tu editor de código.

Edita manualmente el archivo eliminando los marcadores (<<<<<<<, =======, >>>>>>>).

Decide qué código quieres conservar (puedes conservar uno, el otro, o combinar ambos de una forma nueva).

Guarda el archivo.

### Paso 2: Marcar como Resuelto
Una vez que el archivo tiene el aspecto correcto y no quedan marcadores, debes decirle a Git que el conflicto ha sido solucionado:

```bash
 git commit -am "Union rama-conflicto"
Nota: Usar git add no añade un cambio nuevo; le dice a Git que el archivo está ahora en el staging area y listo para finalizar la fusión.
Por lo que usamos el comando de dos pasos en uno.
```
### Paso 3: Eliminar la rama que no volveremos a utilizar
```bash
git branch -d rama-conflicto
```
