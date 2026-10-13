# Admin, photos & security

## Database Editor

Supports item CRUD, reference-data CRUD, search, pagination, confirmations and photo management.

## Authentication

```text
POST /api/auth/login
GET  /api/auth/session
POST /api/auth/logout
```

Protected namespace:

```text
/api/admin/*
```

The true security boundary is backend middleware. A frontend redirect alone would not be sufficient.

## Sessions

- server-side session state;
- HttpOnly cookie;
- 8-hour lifetime.

## Safe reference deletion

Used categories/colours/sizes/boxes cannot be removed because the V2 foreign keys use `RESTRICT`.

## Photos

```text
Original imported images: public/images/
Railway uploads:          /data/images/
Desktop uploads:          userData/images/
```

Uploaded filenames use UUIDs to reduce collisions.

!!! warning "Secrets"
    Administrator credentials belong in runtime environment variables, never in Git or public documentation.
