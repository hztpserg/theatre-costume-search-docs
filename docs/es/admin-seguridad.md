# Administración, fotos y seguridad

## Database Editor

Permite CRUD de items y referencias, búsqueda, paginación, confirmaciones y gestión de fotos.

## Autenticación

```text
POST /api/auth/login
GET  /api/auth/session
POST /api/auth/logout
```

Namespace protegido:

```text
/api/admin/*
```

La seguridad real está en el middleware backend; una redirección frontend por sí sola no sería suficiente.

## Sesión

- estado server-side;
- cookie HttpOnly;
- duración 8 horas.

## Borrado seguro

Categorías, colores, tallas y cajas usadas no se pueden borrar por `RESTRICT`.

## Fotos

```text
Originales:       public/images/
Uploads Railway:  /data/images/
Uploads Desktop:  userData/images/
```

!!! warning "Secretos"
    Las credenciales administrativas deben vivir en variables runtime, nunca en Git o documentación pública.
