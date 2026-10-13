# Puesta en marcha local

## Requisitos

- Git
- Node.js 22
- npm

## Clonar

```bash
git clone https://github.com/hztpserg/theatre-costume-search.git
cd theatre-costume-search
```

## Dependencias

```bash
npm ci
```

## Base runtime

La DB local está ignorada por Git.

Opciones:

1. importar desde el Excel original;
2. restaurar una V2 validada.

Con Excel:

```bash
npm run setup:initial
```

## Arrancar

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

Abrir:

```text
http://localhost:3000
```

## Comprobar

```bash
npm run check
git diff --check
npm audit --omit=dev
```

Si un módulo nativo necesita compilarse, Windows puede requerir Visual Studio Build Tools + **Desktop development with C++**.
