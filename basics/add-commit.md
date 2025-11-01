# GIT ADD
# Git no guarda automáticamente los cambios que haces en los archivos.
# Hay que decirle qué archivos quieres preparar para guardar ("staging area").

git add → selecciona los archivos que quieres incluir en tu próximo "snapshot" del proyecto.

# Añadir un archivo específico:
git add script.py

# Añadir todos los archivos modificados en el proyecto:
git add .

# Comprobar qué archivos están en el "staging area":
git status

# Subir todos los archivos html (notese que hay aveces especificar el directorio)
git add *.html
git add /js*.js

# Añade todos los archivos dentro de la carpeta css/ (y sus subcarpetas) al staging area de Git.
git add css/

# GIT COMMIT
# Cuando haces un commit, estás guardando un punto en el tiempo del estado de tu proyecto.
# git commit → crea una nueva versión (snapshot) con los cambios añadidos.

# Cada commit incluye:
# - Los cambios añadidos con git add
# - Un mensaje que explica qué hiciste (el mensaje se añade con -m "mensaje")

# Ejemplo:
git commit -m "Agrega función para calcular promedio"

# Combina los comandos git add y git commit en una sola línea, pero solo para archivos que ya están siendo rastreados (tracked) por Git.
git commit -am "mensaje"

# Para ver el historial de commits en Git.
git log

# Para verlo de manera resumida
git log --oneline



