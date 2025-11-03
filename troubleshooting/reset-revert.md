# Quitar un archivo del staging area
git reset archivo

# Quitar todos los archivos añadidos
git reset

# Para ver los cambios que aún no has confirmado en Git. Te deja ver qué líneas han cambiado, agregado o eliminado antes de hacer git add o git commit.
git diff
(Si estamos en VS Code es más visual utilizar source control)


git reset --soft HEAD^
# --soft: deshace el commit pero mantiene todos los cambios en el staging area (git add sigue activo).

# --mixed (por defecto): deshace el commit y saca los archivos del staging area, pero los deja modificados en tu carpeta.

# --hard: ⚠️ deshace todo, borrando los cambios del commit y del directorio (no se puede recuperar fácilmente).

git reflog 
# muestra un historial de todas las acciones recientes que han movido el puntero de HEAD, incluso las que ya no aparecen en git log.

git mv 
# se usa para mover o renombrar archivos o carpetas dentro de tu repositorio Git, y registrar automáticamente ese cambio para el próximo commit.
# Ejemplo: git mv notas.md apuntes.md

git rm 
# elimina el archivo tanto del disco (tu carpeta) como del índice de Git (la zona de preparación o staging area). Luego, debes hacer un git commit para guardar ese cambio en el historial.
