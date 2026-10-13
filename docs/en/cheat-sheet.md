# Defence cheat sheet

## Numbers

```text
1017 items
5 categories
102 colours
53 sizes
74 boxes
242 photos
11 legitimate NULL quantities
8-hour admin session
```

## Architecture

```text
HTML/CSS/JS → Express REST API → SQLite V2 + photos
```

## Filters

```text
OR inside group
AND between groups
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
packaged seed
```

## Key commands

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

## 30-second summary

> “The project started from Excel and evolved into a normalized SQLite V2 application with an Express API and JavaScript frontend. The public catalogue provides ranked search and dynamic faceted filters. The authenticated editor manages items, reference data and photos. Railway stores mutable data in `/data`, while Electron reuses the same application with `userData` and a Windows installer.”
