# Estructura del proyecto

```text
theatre-costume-search/
├── .github/workflows/docs.yml
├── database/
│   ├── schema.sql
│   └── inventory.db
├── data/inventory.xlsx
├── desktop/main.js
├── docs/
├── public/
│   ├── admin/
│   ├── css/
│   ├── images/
│   ├── js/
│   ├── index.html
│   ├── search.html
│   └── item.html
├── scripts/
│   ├── init-db.js
│   ├── import-excel.js
│   └── migrate-v2.js
├── .gitignore
├── mkdocs.yml
├── package.json
├── package-lock.json
├── requirements-docs.txt
├── README.md
└── server.js
```

## Responsabilidades

| Fichero | Responsabilidad |
|---|---|
| `server.js` | Express, SQLite, API, auth, admin, fotos |
| `database/schema.sql` | esquema normalizado V2 |
| `scripts/init-db.js` | inicializa/valida V2 |
| `scripts/import-excel.js` | importa Excel |
| `scripts/migrate-v2.js` | utilidad histórica V1→V2 |
| `public/js/search.js` | ranking, filtros, facets, estado |
| `public/js/item.js` | detalle |
| `public/js/login.js` | login/sesión |
| `public/js/admin.js` | editor CRUD |
| `desktop/main.js` | Electron, `userData`, Express embebido |
| `package.json` | scripts, dependencias y build |
| `.gitignore` | exclusiones runtime/generadas |
| `mkdocs.yml` | documentación |

## No se versionan

```text
node_modules/
database/*.db
data/*.xlsx
backups/
documentation/
dist/
site/
```
