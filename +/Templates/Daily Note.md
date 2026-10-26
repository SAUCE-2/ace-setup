---
tags:
  - daily-note
---
# <% tp.date.now("dddd, Do MMM YYYY") %>
## Tasks
## Notes
## Linked to today
```base
filters:
  and:
    - file.ext == "md"
    - file.path != this.file.path
    - '!file.inFolder("Templates")'
    - file.hasLink(this.file)
views:
  - type: table
    name: Linked to today
    order:
      - file.name
      - tags
      - file.folder
    sort:
      - property: file.name
        direction: ASC
```
