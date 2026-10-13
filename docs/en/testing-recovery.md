# Testing & recovery

## Static checks

```bash
npm run check
git diff --check
npm audit --omit=dev
```

Final validated runtime audit result:

```text
0 vulnerabilities
```

## SQLite integrity

```sql
PRAGMA foreign_key_check;
PRAGMA integrity_check;
```

## Manual functional battery

Validated areas include Home, catalogue, text search, OR/AND filters, dynamic counters, detail page, state restoration, responsive layout, auth, item CRUD, reference restrictions, photo upload/replace/remove, Railway persistence, Desktop persistence, clean first run and Windows installer.

## Recovery locations

```text
Local:    database/inventory.db
Railway:  /data/inventory.db + /data/images/
Desktop:  %APPDATA%\theatre-costume-search\
```

## Safe Desktop reset

1. close app;
2. rename `userData` folder;
3. launch again;
4. verify a new seed-based DB is created;
5. keep the backup until validation is complete.
