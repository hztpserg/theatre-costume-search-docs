# Historia del proyecto

## Punto de partida

El teatro tenía el inventario en Excel. Era útil como fuente de datos, pero incómodo para búsqueda rápida, relaciones, edición controlada y acceso remoto.

## Evolución

```mermaid
flowchart TD
    X[Excel] --> V1[SQLite V1]
    V1 --> UI[Catálogo público]
    UI --> V2[SQLite V2 normalizada]
    V2 --> CRUD[Database Editor]
    CRUD --> P[Fotos]
    P --> A[Autenticación]
    A --> R[Railway]
    R --> E[Electron]
    E --> I[Instalador Windows]
```

## Por qué V2 fue necesaria

V1 guardaba textos repetidos dentro de `items`. Para un editor robusto hacía falta separar categorías, colores, tallas, cajas y fotos en tablas canónicas con claves foráneas.

## Problemas técnicos resueltos

- importación del Excel real;
- conservación de cantidades desconocidas como `NULL`;
- normalización;
- borrado seguro;
- talla primaria y secundaria;
- fotos persistentes;
- autenticación en backend;
- volumen persistente Railway;
- rebuild de `better-sqlite3` para Electron;
- almacenamiento Desktop en `userData`;
- seed de primer arranque;
- servidor Desktop limitado a `127.0.0.1`.

!!! note
    La historia demuestra desarrollo iterativo: cada fase resolvió una limitación concreta de la anterior.
