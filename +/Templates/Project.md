---
tags:
  - project
status: active
related: []
created: "[[<% tp.date.now("YYYY-MM-DD") %>]]"
---
# <% tp.file.title %>
*Hub for the whole project. One per folder. Shows every effort whose `projects` includes this hub, including shared ones that live in another project's folder.*
**What it is:** 
**Repo / links:** 
## Decisions
*Link notes that shape the project*
## Open tasks
```tasks
not done
(path includes <% tp.file.folder(true) %>) OR (heading includes <% tp.file.title %>)
group by filename
group by heading
short mode
```
## Efforts
```base
filters:
  and:
    - file.hasTag("effort")
    - file.hasLink(this.file)
formulas:
  shared: if(projects.length > 1, "shared", "")
views:
  - type: table
    name: Efforts
    order:
      - file.name
      - status
      - formula.shared
      - projects
      - file.mtime
    sort:
      - property: file.mtime
        direction: DESC
```
## Notes
```base
filters:
  and:
    - file.inFolder(this.file.folder)
    - file.path != this.file.path
    - '!file.hasTag("effort")'
    - file.ext == "md"
views:
  - type: table
    name: Notes
    order:
      - file.name
      - tags
      - file.mtime
    sort:
      - property: file.mtime
        direction: DESC
```
