```dataview
TABLE dateformat(file.mtime, "dd.MM.yyyy - HH:mm") AS "Last modified"
FROM "Kunnskap"
WHERE dg-publishWHERE file.mtime
SORT file.mtime DESC
LIMIT 10
```