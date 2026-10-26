---
tags:
  - map
up:
  - []
related: []
created: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
---
# <% tp.file.title %>
*What this map gathers, one liner. Make one once a topic has ~5+ notes and you keep hunting for them.*
## Key notes
*Hand-picked links, grouped and ordered however makes sense. Add a line of why next to each.*
- 
## Related maps
- 
## Everything linking here
```base
filters:
  and:
    - file.hasLink(this.file)
    - file.ext == "md"
views:
  - type: table
    name: Links here
    order:
      - file.name
      - tags
      - file.folder
    sort:
      - property: file.mtime
        direction: DESC
```
