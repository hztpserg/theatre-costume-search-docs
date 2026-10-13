# Solución de problemas

| Problema | Acción |
|---|---|
| npm bloqueado en PowerShell | usar `npm.cmd` o Git Bash |
| `npm ci` falla en `better-sqlite3` | comprobar Node 22 y requisitos de compilación |
| módulo no encontrado | la instalación no terminó correctamente |
| localhost no abre | comprobar servidor/puerto |
| 0 items | revisar `database/inventory.db` V2 |
| filtros vacíos | revisar `/api/filters` y consola |
| foto rota | revisar fichero/ruta/fallback |
| admin 401 | falta sesión o ha caducado |
| referencia no se borra | probablemente está en uso; es intencional |
| Railway pierde DB | revisar `DATABASE_PATH=/data/inventory.db` |
| Railway pierde upload | revisar `IMAGES_DIRECTORY=/data/images` |
| Git Bash transforma `/data` | usar `MSYS_NO_PATHCONV=1` |
| Electron falla con DB nativa | ejecutar `npm run desktop:rebuild` |
| aparece Firewall | revisar binding `127.0.0.1` |
| Desktop limpio sin DB | revisar seed empaquetada |
| Git muestra `site/` | revisar `.gitignore` |

Primer diagnóstico:

```bash
git status
node --version
npm --version
npm run check
```
