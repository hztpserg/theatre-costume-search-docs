# Production deployment

This is the practical procedure for moving a validated web change to Railway.

## 1. Preconditions

Require a clean, tested `main`:

```bash
npm run check
git diff --check
git status
```

## 2. Update production branch

```bash
git checkout production
git pull origin production
git merge main
```

If a conflict occurs, resolve it deliberately, remove all conflict markers, and rerun checks before committing.

## 3. Validate and push

```bash
npm run check
git diff --check
git status
git push origin production
```

## 4. Observe Railway

```bash
railway status
railway deployment list --limit 5
railway logs --latest --lines 100
```

Look for the correct database path and successful server startup.

## 5. Smoke test production

Open `https://theatre.inserhii.es` and test:

- Home;
- Search;
- filters;
- detail page;
- login;
- one safe Database Editor operation.

## 6. Storage-sensitive change

Before schema/storage work:

1. back up `/data/inventory.db`;
2. inspect `/data/images`;
3. confirm variables;
4. apply the smallest controlled change;
5. verify again after redeploy.

## 7. Manual redeploy

```bash
railway redeploy --yes
```

## Git Bash path conversion

When passing Linux-style absolute paths to Railway volume commands from Git Bash, prefix the command with:

```bash
MSYS_NO_PATHCONV=1
```
