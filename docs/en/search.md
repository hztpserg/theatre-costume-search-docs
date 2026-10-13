# Search & filters

## Relevance ranking

```text
exact name
>
name starts with query
>
name contains query
>
description contains query
```

## Faceted logic

> **OR inside one filter group, AND between different groups.**

Example:

```text
(Category = Hats OR Category = Props)
AND
(Colour = Blue OR Colour = White)
AND
Box = B1
```

## Dynamic counts

When counting one group, the code ignores that group temporarily but keeps text search and all other groups.

## Size

One Size facet checks both `size_primary` and `size_secondary`.

## State restoration

`sessionStorage` preserves search/filter state and scroll positions when opening a detail page and returning.

## Why client-side filtering

For ~1017 records it is fast, simple and easy to reason about. A much larger catalogue would justify server-side search/pagination.
