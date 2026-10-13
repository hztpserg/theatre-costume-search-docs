# Local setup

## Requirements

Recommended/tested:

- Git
- Node.js 22
- npm

## Clone

```bash
git clone https://github.com/hztpserg/theatre-costume-search.git
cd theatre-costume-search
```

## Install dependencies

```bash
npm ci
```

`npm ci` reproduces the lock-file dependency tree.

## Runtime database

The runtime DB is intentionally ignored by Git.

Use either:

1. original Excel source + importer; or
2. a trusted validated V2 `inventory.db`.

With original source data:

```bash
npm run setup:initial
```

## Start locally

Git Bash:

```bash
ADMIN_USERNAME=admin ADMIN_PASSWORD='LOCAL_PASSWORD' npm start
```

PowerShell:

```powershell
$env:ADMIN_USERNAME="admin"
$env:ADMIN_PASSWORD="LOCAL_PASSWORD"
npm.cmd start
```

Open:

```text
http://localhost:3000
```

## Validate

```bash
npm run check
git diff --check
npm audit --omit=dev
```

## Windows native dependency note

If a native module must compile instead of using a prebuilt binary, Windows may require Visual Studio Build Tools with **Desktop development with C++**.
