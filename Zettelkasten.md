---
zettel:
  - Map of Content
topic:
  - "[[Productivity]]"
references: 
created: 2024-09-01
status: []
tags:
  - pkm
---
> [!NOTES]- Inbox
> ```dataview
> TABLE WITHOUT ID
> file.link as "Notes to process"
> FROM -"Extras"
> WHERE contains(zettel, "Fleeting Note")
> WHERE type = [[Card]]
> 
> ```


> [!combine]- Working on
> > ```dataview
> > TABLE WITHOUT ID
> > file.link as Processing
> > FROM -"Extras"
> > WHERE contains(status, "In Progress")
> > WHERE type = "Card"
> > ```


> [!AWARD]- Done 
> ```dataview
> TABLE WITHOUT ID
>  file.link as Notes
>  
> FROM -"Extras"
> WHERE contains(status, "Done")
> WHERE contains(zettel, "Permanent Note")
> ```


