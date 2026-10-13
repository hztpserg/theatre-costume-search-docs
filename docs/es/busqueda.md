# Búsqueda y filtros

## Ranking

```text
nombre exacto
>
empieza por
>
nombre contiene
>
descripción contiene
```

## Lógica facetada

> **OR dentro del mismo grupo; AND entre grupos distintos.**

## Contadores dinámicos

Al calcular un grupo, se ignora temporalmente ese grupo y se mantienen la búsqueda textual y los demás filtros.

## Talla

Un único filtro Size compara `size_primary` y `size_secondary`.

## Estado

`sessionStorage` conserva texto, filtros, grupos abiertos y scroll al abrir una ficha y volver.

## Escala

Con ~1017 registros, filtrar en cliente es una decisión simple y razonable. A una escala mucho mayor se pasaría a búsqueda/paginación server-side.
