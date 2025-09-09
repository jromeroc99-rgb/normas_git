# 📚 Guía Simple de Git para el Equipo

## � Nuestras Ramas

- **`main`** → Versión que funciona perfectamente ✅
- **`dev`** → Donde juntamos todo antes de main (solo el jefe toca esta)
- **`tu_nombre`** → Tu rama personal (ej: `javi`, `maria`, `carlos`)

## � Reglas Básicas

1. **Siempre trabaja en tu rama personal** (nunca en `main` o `dev`)
2. **Antes de empezar**: actualiza tu rama con `dev`
3. **Para subir cambios**: haz Pull Request a `dev`
4. **El jefe revisa** y aprueba tus cambios

## �️ Cómo hacerlo en VS Code

### Primera vez (configuración)

1. **Instalar extensión de Git** (ya viene incluida en VS Code)
2. **Clonar repositorio**:
   - `Ctrl + Shift + P` → buscar "Git: Clone"
   - Pegar la URL del repo
   - Elegir carpeta donde guardarlo

3. **Crear tu rama personal**:
   - Abajo a la izquierda verás "main" → hacer clic
   - "Create new branch from..." → escribir tu nombre (ej: `javi`)

### Día a día

#### 1️⃣ Actualizar tu rama con dev

**En VS Code:**
- Clic en tu rama (abajo izquierda)
- Seleccionar `dev`
- `Ctrl + Shift + P` → "Git: Pull"
- Volver a tu rama personal
- `Ctrl + Shift + P` → "Git: Merge Branch" → seleccionar `dev`

**En Terminal:**
```bash
git checkout tu_nombre
git pull origin dev
```

#### 2️⃣ Hacer cambios y guardarlos

**En VS Code:**
- Edita tus archivos normalmente
- Ve a la pestaña "Source Control" (icono de rama)
- Escribe un mensaje como: "arreglo el bug del login"
- Clic en "Commit"
- Clic en "Sync Changes" (subir al GitHub)

**En Terminal:**
```bash
git add .
git commit -m "arreglo el bug del login"
git push origin tu_nombre
```

#### 3️⃣ Solicitar que tus cambios se incluyan en dev

**En GitHub (navegador):**
- Ve a tu repositorio en GitHub
- Aparecerá un botón "Compare & pull request" → clic
- Título: describe qué hiciste
- Descripción: explica un poco más si es necesario
- "Create pull request"

## 🎯 Comandos Súper Básicos

```bash
# Ver en qué rama estás
git branch

# Cambiar de rama
git checkout nombre_rama

# Ver qué archivos cambiaste
git status

# Guardar todos los cambios
git add .
git commit -m "tu mensaje aquí"
git push

# Traer cambios nuevos
git pull origin dev
```

## 📝 Tipos de Mensajes de Commit

- `fix: arreglo el botón que no funcionaba`
- `add: añado página de contacto`
- `update: actualizo los colores del menú`
- `docs: mejoro el README`

## ❌ Qué NO hacer

- ❌ Trabajar directamente en `main` o `dev`
- ❌ Subir archivos sin probar que funcionen
- ❌ Mensajes vagos como "cambios" o "fix"

## ✅ Qué SÍ hacer

- ✅ Siempre trabajar en tu rama
- ✅ Probar que tu código funcione antes de subirlo
- ✅ Escribir mensajes claros de qué hiciste
- ✅ Pedir ayuda si tienes dudas

## 🆘 Si algo sale mal

### "¡Ayuda! Tengo conflictos"

**En VS Code:**
- VS Code te mostrará los conflictos resaltados
- Verás opciones como "Accept Current Change" o "Accept Incoming Change"
- Elige la opción correcta o edita manualmente
- Guarda el archivo
- Haz commit normalmente

### "¡No sé en qué rama estoy!"

**En VS Code:**
- Mira abajo a la izquierda, ahí dice la rama actual

**En Terminal:**
```bash
git branch
```

### "¡Quiero deshacer mis cambios!"

**En VS Code:**
- En Source Control, clic derecho en el archivo → "Discard Changes"

**En Terminal:**
```bash
git checkout -- nombre_archivo
```

---

## 👨‍💼 Para el Jefe de Equipo

### Aprobar Pull Requests

1. Ve a GitHub → pestaña "Pull requests"
2. Clic en el PR que quieres revisar
3. Revisa los cambios en "Files changed"
4. Si está bien: "Review changes" → "Approve" → "Merge pull request"
5. Si necesita cambios: "Review changes" → "Request changes" + comentarios

### Pasar de dev a main

```bash
git checkout main
git pull origin dev
git push origin main
```

---

**🔄 Ejemplo Completo: Javi actualiza el README**

1. Javi abre VS Code
2. Se asegura de estar en su rama `javi`
3. Actualiza desde `dev` (merge)
4. Edita el README.md
5. Va a Source Control
6. Escribe: "docs: mejoro la explicación de ramas"
7. Commit → Sync Changes
8. Va a GitHub y crea Pull Request
9. El jefe revisa y aprueba
10. ¡Listo! Los cambios ya están en `dev`
