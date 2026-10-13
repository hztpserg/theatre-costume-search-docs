# Git y administración del repositorio

## Ramas importantes

```text
main
production
feature/v2-inventory-manager
feature/electron-desktop
```

Commits finales importantes:

```text
718fbc3  Finalize and harden V2 inventory application
8d2960d  Merge V2 application into production
3969b4c  Add Windows desktop application with Electron
```

## Checklist seguro

Antes de cambiar rama:

```bash
git status
```

Antes de commit:

```bash
npm run check
git diff --check
```

Antes de push:

```bash
git diff --cached --check
git diff --cached --stat
git diff --cached --name-status
```

Después:

```bash
git status
git branch -vv
```

## Nunca subir

DB runtime, Excel original, backups, `node_modules`, `dist/`, `site/` ni secretos.
