# GIT ADD
# Git no guarda automáticamente los cambios que haces en los archivos.
# Hay que decirle qué archivos quieres preparar para guardar ("staging area").

# git add → selecciona los archivos que quieres incluir en tu próximo "snapshot" del proyecto.

# Añadir un archivo específico:
git add script.py

# Añadir todos los archivos modificados en el proyecto:
git add .

# Comprobar qué archivos están en el "staging area":
git status


# GIT COMMIT
# Cuando haces un commit, estás guardando un punto en el tiempo del estado de tu proyecto.
# git commit → crea una nueva versión (snapshot) con los cambios añadidos.

# Cada commit incluye:
# - Los cambios añadidos con git add
# - Un mensaje que explica qué hiciste (el mensaje se añade con -m "mensaje")

# Ejemplo:
git commit -m "Agrega función para calcular promedio"



