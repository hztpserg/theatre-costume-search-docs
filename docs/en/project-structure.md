# Project structure

```text
theatre-costume-search/
├── .github/workflows/docs.yml
├── database/
│   ├── schema.sql
│   └── inventory.db              # runtime, ignored
├── data/inventory.xlsx           # source data, ignored
├── desktop/main.js
├── docs/
├── public/
│   ├── admin/
│   │   ├── index.html
│   │   └── login.html
│   ├── css/
│   │   ├── style.css
│   │   └── admin.css
│   ├── images/
│   ├── js/
│   │   ├── search.js
│   │   ├── item.js
│   │   ├── login.js
│   │   └── admin.js
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

## Responsibilities

| File | Responsibility |
|---|---|
| `server.js` | Express, SQLite connection, public/admin API, auth, photo handling |
| `database/schema.sql` | canonical normalized V2 schema |
| `scripts/init-db.js` | safely initializes and validates V2 |
| `scripts/import-excel.js` | imports original Excel into V2 |
| `scripts/migrate-v2.js` | historical V1→V2 utility |
| `public/js/search.js` | ranking, filters, facets, cards, state |
| `public/js/item.js` | individual item details |
| `public/js/login.js` | login/session UI |
| `public/js/admin.js` | Database Editor UI and CRUD |
| `public/css/style.css` | public responsive design |
| `public/css/admin.css` | admin/login design |
| `desktop/main.js` | Electron startup, `userData`, embedded Express |
| `package.json` | scripts, dependencies and Electron build config |
| `.gitignore` | runtime/generated/private exclusions |
| `mkdocs.yml` | documentation site configuration |

## Intentionally excluded from Git

```text
node_modules/
database/*.db
data/*.xlsx
backups/
documentation/
dist/
site/
```
