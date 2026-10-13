# API reference

## Public endpoints

| Method | Route | Purpose |
|---|---|---|
| GET | `/api/items` | catalogue |
| GET | `/api/items/:id` | one item |
| GET | `/api/filters` | filter/reference values |
| POST | `/api/auth/login` | create session |
| GET | `/api/auth/session` | check session |
| POST | `/api/auth/logout` | end session |

## Protected administration

All `/api/admin/*` routes require an authenticated session. Typical resource groups are items, categories, colours, sizes, boxes and photos.

```mermaid
sequenceDiagram
    participant B as Browser
    participant E as Express
    participant S as SQLite
    B->>E: GET /api/items/25
    E->>S: SELECT + JOIN
    S-->>E: normalized row
    E-->>B: JSON
    B->>B: render DOM
```
