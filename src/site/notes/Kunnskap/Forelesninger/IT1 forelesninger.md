```dataview
TABLE dateformat(forelesningsdato, "yyyy-MM-dd") AS "Dato"
FROM "Kunnskap/Forelesninger"\nWHERE dg-publish\n
WHERE contains(tags, "it1") and contains(dg-publish, true) and contains(tags, "forelesning")
SORT forelesningsdato ASC
```