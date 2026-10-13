# New computer setup

This procedure is designed to bring the project up on a different Windows computer.

## 1. Install prerequisites

Install Git and Node.js 22. Verify:

```bash
node --version
npm --version
git --version
```

Expected Node major version:

```text
v22.x
```

## 2. Clone the repository

```bash
git clone <repository-url>
cd theatre-costume-search
```

If the repository is private, use a GitHub account with access.

## 3. Install the exact dependency tree

```bash
npm ci
```

`npm ci` uses `package-lock.json`, making installation reproducible.

## 4. Prepare runtime data

The live DB is intentionally ignored by Git.

### Method A — import the original Excel source

Place the workbook at:

```text
data/inventory.xlsx
```

Then:

```bash
npm run setup:initial
```

### Method B — restore a trusted V2 DB

Copy it to:

```text
database/inventory.db
```

## 5. Set credentials and start

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

Open `http://localhost:3000`.

## 6. Validate

```bash
npm run check
npm audit --omit=dev
```

Success criteria: server starts, 1017 items are visible, and admin login works.

## 7. If `better-sqlite3` fails to install

First confirm Node 22. If npm is compiling the native module instead of using a compatible binary, Visual Studio Build Tools with **Desktop development with C++** may be required.
