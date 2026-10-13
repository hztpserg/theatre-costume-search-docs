# Instalación en un ordenador nuevo

## 1. Instalar requisitos

Instalar Git y Node.js 22. Comprobar:

```bash
node --version
npm --version
git --version
```

## 2. Clonar

```bash
git clone <repository-url>
cd theatre-costume-search
```

Si el repo es privado, usar una cuenta autorizada.

## 3. Instalar dependencias exactas

```bash
npm ci
```

## 4. Preparar datos runtime

La DB real está ignorada por Git.

### Opción A — importar Excel

Copiar a:

```text
data/inventory.xlsx
```

Después:

```bash
npm run setup:initial
```

### Opción B — restaurar una V2 validada

Copiar a:

```text
database/inventory.db
```

## 5. Credenciales y arranque

Git Bash:

```bash
ADMIN_USERNAME=admin ADMIN_PASSWORD='PASSWORD_LOCAL' npm start
```

PowerShell:

```powershell
$env:ADMIN_USERNAME="admin"
$env:ADMIN_PASSWORD="PASSWORD_LOCAL"
npm.cmd start
```

Abrir `http://localhost:3000`.

## 6. Validar

```bash
npm run check
npm audit --omit=dev
```

Debe arrancar, mostrar 1017 items y permitir login admin.

## 7. Si falla `better-sqlite3`

Primero comprobar Node 22. Si npm intenta compilar el módulo nativo, puede hacer falta Visual Studio Build Tools con **Desktop development with C++**.
