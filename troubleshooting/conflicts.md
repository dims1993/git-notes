## Git no guarda carpetas vacías, solo archivos. Por eso, si creas una carpeta sin nada dentro, no aparecerá en tu repositorio ni se subirá a GitHub.

### Archivo vacío usado para “mantener” carpetas vacías dentro del control de versiones de Git.
.gitkeep

### Archivo especial que le dice a Git qué archivos o carpetas debe ignorar, es decir, no rastrear ni incluir en los commits.
.gitignore 

#### Ignorar una carpeta completa
carpeta/

#### Ignorar todos los archivos de cierto tipo
*.log
*.tmp
*.pyc

#### No ignorar un archivo dentro de una carpeta ignorada: Usa ! (exclamación):
/data/*
!/data/README.md





