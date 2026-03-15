# Comandos Git Aprendidos

## Módulo 1: Conceptos Básicos

### Inicializar y Configurar
- `git init` - Crear un nuevo repositorio Git en la carpeta actual
- `git config --global user.name "Nombre"` - Configurar nombre de usuario
- `git config --global user.email "email@ejemplo.com"` - Configurar email

### Flujo Básico
- `git status` - Ver el estado actual del repositorio (úsalo siempre)
- `git add <archivo>` - Agregar archivo al staging area
- `git add .` - Agregar todos los archivos modificados
- `git commit -m "mensaje"` - Guardar cambios con un mensaje descriptivo

---

## Módulo 2: Historial y Navegación

### Ver Historial
- `git log` - Ver historial completo de commits
- `git log --oneline` - Ver historial compacto (una línea por commit)
- `git log --oneline --graph --all` - Ver historial con gráfico visual
- `git log --oneline -3` - Ver solo los últimos 3 commits

### Comparar Cambios
- `git diff` - Ver cambios NO guardados (working directory vs último commit)
- `git diff --staged` - Ver cambios en staging area (preparados para commit)
- `git diff <commit1> <commit2>` - Comparar dos commits específicos

### Ver Commits Específicos
- `git show` - Ver detalles del último commit
- `git show <hash>` - Ver detalles de un commit específico

---

## Módulo 3: Trabajar con Remotos (GitHub)

### Configurar Remoto
- `git remote add origin <URL>` - Conectar repositorio local con GitHub
- `git remote -v` - Ver repositorios remotos configurados

### Sincronizar con GitHub
- `git push -u origin main` - Primera vez que subes (configura tracking)
- `git push` - Subir commits a GitHub (después de la primera vez)
- `git pull` - Bajar cambios desde GitHub y fusionarlos
- `git clone <URL>` - Descargar repositorio completo desde GitHub

---

## Módulo 4: Ramas (Branches)

### Gestionar Ramas
- `git branch` - Ver ramas locales existentes
- `git branch -a` - Ver todas las ramas (locales y remotas)
- `git branch <nombre>` - Crear nueva rama
- `git branch -d <nombre>` - Eliminar rama (solo si ya fue fusionada)

### Cambiar de Rama
- `git checkout <nombre>` - Cambiar a otra rama
- `git checkout -b <nombre>` - Crear rama y cambiar a ella (atajo)

### Fusionar Ramas
- `git merge <nombre>` - Fusionar rama en la rama actual

---

## Flujos de Trabajo Completos

### Flujo Básico Local
```bash
# 1. Hacer cambios en archivos
# 2. Ver qué cambió
git status
git diff

# 3. Preparar cambios
git add .

# 4. Guardar cambios
git commit -m "Descripción de los cambios"

# 5. Ver historial
git log --oneline
```

### Flujo con GitHub
```bash
# 1. Bajar últimos cambios
git pull

# 2. Hacer cambios locales
git add .
git commit -m "mensaje"

# 3. Subir cambios
git push
```

### Flujo con Ramas
```bash
# 1. Crear y cambiar a nueva rama
git checkout -b feature/mi-funcionalidad

# 2. Hacer cambios y commits
git add .
git commit -m "Implementar funcionalidad"

# 3. Volver a main
git checkout main

# 4. Fusionar la rama
git merge feature/mi-funcionalidad

# 5. Eliminar la rama
git branch -d feature/mi-funcionalidad

# 6. Subir a GitHub
git push
```

---

## Convenciones y Buenas Prácticas

### Nombres de Ramas
- `feature/nombre` - Para nuevas funcionalidades
- `bugfix/nombre` o `fix/nombre` - Para correcciones de errores
- `hotfix/nombre` - Para correcciones urgentes
- `docs/nombre` - Para documentación
- `refactor/nombre` - Para refactorización de código

### Mensajes de Commit
- Usar verbos en infinitivo o imperativo
- Ser descriptivo pero conciso
- Ejemplos:
  - "Agregar validación de formulario de login"
  - "Corregir error en cálculo de totales"
  - "Refactorizar función de búsqueda"

---

## Conceptos Importantes

### Los 3 Estados de Git
1. **Working Directory** - Donde trabajas y editas archivos
2. **Staging Area** - Preparas lo que quieres guardar (git add)
3. **Repository** - Guardas permanentemente los cambios (git commit)

### Términos Clave
- **commit** - Una "fotografía" del proyecto en un momento específico
- **branch** - Una línea de desarrollo independiente
- **merge** - Fusionar cambios de una rama en otra
- **origin** - Nombre por defecto del repositorio remoto principal
- **main/master** - Nombre de la rama principal
- **HEAD** - Puntero al commit actual donde estás trabajando
- **hash** - Identificador único de un commit (ej: c60723b)
