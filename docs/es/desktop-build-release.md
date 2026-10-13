# Build y release de Desktop

## 1. Partir de `main`

```bash
git checkout main
git pull origin main
npm ci
```

## 2. Rebuild nativo

```bash
npm run desktop:rebuild
```

Esto adapta `better-sqlite3` al ABI de Electron.

## 3. Validar

```bash
npm run check
git diff --check
```

## 4. Ejecutar Desktop

```bash
ADMIN_USERNAME=admin ADMIN_PASSWORD='PASSWORD_LOCAL' npm run desktop
```

Probar Home, Search, login, CRUD, fotos y persistencia al reiniciar.

## 5. Crear instalador

```bash
npm run desktop:dist
```

Resultado esperado:

```text
dist/Theatre Costume Search Setup 2.0.0.exe
```

La seed debe quedar empaquetada lógicamente en:

```text
resources/seed/inventory.db
```

## 6. Prueba limpia

1. instalar con NSIS;
2. arrancar;
3. cerrar;
4. renombrar `userData`;
5. arrancar otra vez;
6. comprobar que se crea una nueva DB;
7. crear item de prueba;
8. cerrar y abrir;
9. comprobar persistencia;
10. borrar el test.

`dist/` es generado y no debe entrar en Git.
