# Guía de defensa

## Orden recomendado de demo

1. Explicar el problema original de Excel.
2. Mostrar Home.
3. Abrir Search y enseñar el inventario.
4. Buscar texto.
5. Aplicar varios filtros.
6. Explicar OR dentro de grupo y AND entre grupos.
7. Abrir una ficha.
8. Volver y mostrar restauración del estado.
9. Abrir Database Editor.
10. Explicar autenticación.
11. Hacer login.
12. Editar o crear un item seguro de prueba.
13. Explicar referencias normalizadas.
14. Mostrar fotos.
15. Explicar persistencia Railway.
16. Abrir Desktop instalado.
17. Explicar Electron, localhost, `userData`, seed e instalador NSIS.

## Respuestas fuertes

### ¿Por qué SQLite?
Dataset moderado, transacciones, fiabilidad y sin servidor DB adicional.

### ¿Por qué no Excel?
No ofrece esta UX de búsqueda, validación backend, relaciones, CRUD autenticado ni despliegue web.

### ¿Por qué normalizar?
Para evitar textos repetidos inconsistentes y permitir gestión segura de referencias.

### ¿Por qué JavaScript puro?
Los requisitos no justificaban un framework frontend grande.

### ¿Por qué seguridad backend?
El frontend se puede saltar; la API debe autenticar por sí misma.

### ¿Por qué HttpOnly?
El navegador puede enviar la cookie, pero JavaScript normal no puede leerla directamente.

### ¿Por qué volumen Railway?
Los despliegues sustituyen código, pero los datos deben sobrevivir.

### ¿Por qué Electron?
Reutiliza la aplicación web probada.

### ¿Por qué localhost?
Solo la ventana local necesita la API.

### ¿Por qué pesa el instalador?
Electron incluye Chromium/Node y además existen muchas imágenes originales.

### ¿Qué pasa en el primer arranque Desktop?
La seed V2 empaquetada se copia a `userData` si todavía no existe DB.

## Limitaciones

Un único admin, sin suite completa automática, sin sincronización Desktop↔Railway, búsqueda cliente dimensionada a este catálogo y paquete Electron relativamente grande.

## Frase final

> “La decisión arquitectónica más fuerte fue la reutilización: un modelo de datos, un backend Express y un frontend desplegados en tres entornos con storage específico.”
