# Despliegue a producción

## 1. Requisitos previos

Antes de tocar `production`:

```bash
npm run check
git diff --check
git status
```

`main` debe estar limpio y probado.

## 2. Actualizar producción

```bash
git checkout production
git pull origin production
git merge main
```

Si hay conflicto, resolverlo manualmente, eliminar todos los marcadores y volver a ejecutar las pruebas.

## 3. Validar y push

```bash
npm run check
git diff --check
git status
git push origin production
```

## 4. Observar Railway

```bash
railway status
railway deployment list --limit 5
railway logs --latest --lines 100
```

Comprobar la ruta correcta de DB y el arranque del servidor.

## 5. Smoke test

Abrir `https://theatre.inserhii.es` y comprobar Home, Search, filtros, ficha, login y una operación segura del editor.

## 6. Si cambia DB o storage

1. backup de `/data/inventory.db`;
2. revisar `/data/images`;
3. confirmar variables;
4. cambio mínimo controlado;
5. validar de nuevo tras redeploy.

## 7. Redeploy manual

```bash
railway redeploy --yes
```

## 8. Git Bash y rutas Linux

Para comandos de volumen con `/data` o `/images`:

```bash
MSYS_NO_PATHCONV=1
```
