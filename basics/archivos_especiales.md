## Carpetas vacías en Git

Git **no guarda carpetas vacías**, solo archivos.  
Por eso, si creas una carpeta sin contenido, **no aparecerá en tu repositorio ni se subirá a GitHub**.

---

## Archivos especiales

### `.gitkeep`
Archivo vacío que se usa para **mantener carpetas vacías dentro del control de versiones** de Git.  
💡 Útil para asegurar que una carpeta vacía aparezca en GitHub.

---

### `.gitignore`
Archivo que le dice a Git **qué archivos o carpetas debe ignorar**, es decir, **no rastrear ni incluir en los commits**.  

#### Ejemplos de uso de `.gitignore`

- **Ignorar una carpeta completa**
```gitignore
carpeta/
Ignorar todos los archivos de cierto tipo

gitignore
Copiar código
*.log
*.tmp
*.pyc
No ignorar un archivo dentro de una carpeta ignorada (usa !)

gitignore
Copiar código
/data/*
!/data/README.md
Esto ignora todo dentro de /data/ excepto README.md.
