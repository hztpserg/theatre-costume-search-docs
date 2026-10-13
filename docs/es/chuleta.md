# Chuleta de defensa

## Números

```text
1017 items
5 categorías
102 colores
53 tallas
74 cajas
242 fotos
11 NULL legítimos
sesión admin: 8 horas
```

## Arquitectura

```text
HTML/CSS/JS → Express REST API → SQLite V2 + fotos
```

## Filtros

```text
OR dentro
AND entre
```

## Railway

```text
/data/inventory.db
/data/images
```

## Desktop

```text
127.0.0.1:3210
userData/inventory.db
userData/images
seed empaquetada
```

## Comandos clave

```bash
npm ci
npm run check
npm start
npm run desktop
npm run desktop:rebuild
npm run desktop:dist
railway status
railway logs --latest --lines 100
git status
```

## Resumen de 30 segundos

> “El proyecto pasó de Excel a SQLite V2 normalizada con API Express y frontend JavaScript. El catálogo usa búsqueda por relevancia y filtros facetados. El editor autenticado gestiona items, referencias y fotos. Railway guarda datos mutables en `/data`, mientras Electron reutiliza la misma aplicación con `userData` e instalador Windows.”
