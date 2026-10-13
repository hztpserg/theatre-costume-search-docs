# Git & repository administration

## Important branches

```text
main
production
feature/v2-inventory-manager
feature/electron-desktop
```

Important final commits:

```text
718fbc3  Finalize and harden V2 inventory application
8d2960d  Merge V2 application into production
3969b4c  Add Windows desktop application with Electron
```

## Safe administration checklist

Before changing branches:

```bash
git status
```

Before committing:

```bash
npm run check
git diff --check
```

Before pushing:

```bash
git diff --cached --check
git diff --cached --stat
git diff --cached --name-status
```

After pushing:

```bash
git status
git branch -vv
```

## Never commit

Runtime DBs, Excel source, backups, `node_modules`, installer output, generated `site/`, or secrets.
