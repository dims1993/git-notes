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



