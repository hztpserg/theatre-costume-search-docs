# Pruebas y recuperación

## Validación estática

```bash
npm run check
git diff --check
npm audit --omit=dev
```

Resultado runtime final validado:

```text
0 vulnerabilities
```

## SQLite

```sql
PRAGMA foreign_key_check;
PRAGMA integrity_check;
```

## Batería funcional validada

Home, catálogo, búsqueda, filtros OR/AND, contadores dinámicos, ficha, restauración de estado, responsive, auth, CRUD, restricciones de referencias, upload/replace/remove de fotos, persistencia Railway, persistencia Desktop, primer arranque limpio e instalador.

## Recuperación

```text
Local:    database/inventory.db
Railway:  /data/inventory.db + /data/images/
Desktop:  %APPDATA%\theatre-costume-search\
```

## Reset Desktop seguro

1. cerrar app;
2. renombrar `userData`;
3. arrancar;
4. verificar la nueva DB basada en seed;
5. mantener backup hasta terminar la comprobación.
