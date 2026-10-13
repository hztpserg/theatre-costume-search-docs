# Troubleshooting

| Problem | Action |
|---|---|
| npm blocked in PowerShell | use `npm.cmd` or Git Bash |
| `npm ci` fails in `better-sqlite3` | verify Node 22; inspect native build requirements |
| module not found | installation did not finish successfully |
| local page does not open | verify server and port |
| zero items | verify V2 `database/inventory.db` |
| filters missing | inspect `/api/filters` and browser console |
| image missing | verify file/path; UI should use placeholder |
| admin API returns 401 | login/session missing or expired |
| reference delete rejected | likely still referenced; this is intentional |
| Railway DB disappears | verify `DATABASE_PATH=/data/inventory.db` |
| Railway upload disappears | verify `IMAGES_DIRECTORY=/data/images` |
| Git Bash changes `/data` | use `MSYS_NO_PATHCONV=1` |
| Electron native DB error | run `npm run desktop:rebuild` |
| Windows Firewall prompt | verify Desktop Express binds to `127.0.0.1` |
| fresh Desktop has no DB | verify packaged seed resource |
| `site/` appears in Git | verify `.gitignore` |

First diagnostic commands:

```bash
git status
node --version
npm --version
npm run check
```
