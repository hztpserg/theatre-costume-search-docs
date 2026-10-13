# Desktop build & release

## 1. Start from current main

```bash
git checkout main
git pull origin main
npm ci
```

## 2. Rebuild native dependencies

```bash
npm run desktop:rebuild
```

This rebuilds `better-sqlite3` for Electron's runtime ABI.

## 3. Validate

```bash
npm run check
git diff --check
```

## 4. Run Electron

Git Bash example:

```bash
ADMIN_USERNAME=admin ADMIN_PASSWORD='LOCAL_PASSWORD' npm run desktop
```

Test Home, Search, login, CRUD, photos and restart persistence.

## 5. Build installer

```bash
npm run desktop:dist
```

Expected installer:

```text
dist/Theatre Costume Search Setup 2.0.0.exe
```

The packaged seed should appear logically under:

```text
resources/seed/inventory.db
```

## 6. Clean-install validation

1. install with NSIS;
2. launch;
3. close;
4. rename the existing Desktop `userData` folder;
5. launch again;
6. verify a new folder and seeded DB are created;
7. create a test item;
8. close/reopen;
9. verify persistence;
10. delete the test item.

`dist/` is generated output and must remain ignored by Git.
