
```base
properties:
  file.name:
    displayName: Tips
  note.tags:
    displayName: Tags
views:
  - type: table
    name: Table
    filters:
      and:
        - file.inFolder("Blazor")
    order:
      - tags
      - file.name
    sort:
      - property: file.name
        direction: ASC
      - property: tags
        direction: ASC
    columnSize:
      file.name: 955

```

