# Defence guide

## Recommended live demonstration

1. Explain the original Excel problem.
2. Show Home.
3. Open Search and show all items.
4. Search by text.
5. Apply multiple filters.
6. Explain OR inside a group and AND between groups.
7. Open one item.
8. Return and show restored state.
9. Open Database Editor.
10. Explain authentication.
11. Login.
12. Edit or create a safe test item.
13. Explain normalized reference data.
14. Show photo management.
15. Explain Railway persistence.
16. Open installed Desktop version.
17. Explain Electron, localhost, `userData`, seed and NSIS installer.

## Strong answers

### Why SQLite?
Moderate dataset, transactions, reliability, no separate DB server.

### Why not Excel?
Excel does not provide this search UX, backend validation, authenticated CRUD, relationships or web deployment.

### Why normalize?
To reduce inconsistent repeated text and make reference editing safe.

### Why plain JavaScript?
The requirements did not justify a large frontend framework.

### Why backend route protection?
Frontend checks can be bypassed; the API must independently authenticate admin operations.

### Why HttpOnly?
The browser can send the cookie while normal frontend JavaScript cannot directly read it.

### Why a persistent Railway volume?
Deployments can replace code files; mutable user data must survive them.

### Why Electron?
It reuses the tested web application instead of creating a separate desktop codebase.

### Why localhost-only Desktop server?
Only the local BrowserWindow needs the API.

### Why is the installer large?
Electron bundles Chromium/Node and the project includes many original images.

### What happens on first Desktop launch?
The packaged V2 seed DB is copied to writable `userData` if no DB exists yet.

## Limitations

Single-admin model, no full automated test suite, no Desktop↔Railway synchronization, client-side search sized for this catalogue, and a relatively large Electron package.

## Closing sentence

> “The strongest architectural decision was reuse: one data model, one Express backend and one frontend are deployed in three different environments with environment-specific storage.”
