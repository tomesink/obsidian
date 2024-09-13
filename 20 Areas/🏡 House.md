---
up:
  - "[[Home]]"
related: 
created: 2024-08-13
rank:
---






> [!Watch]+ # House maintenance
> House efforts with a rank above `3`.
> 
> ```dataview
> TABLE WITHOUT ID
>  file.link as "",
>  rank as "Rank"
> 
> FROM "20 Areas/Notes/House"
> 
> WHERE rank > 3
> 
> SORT rank desc
> ```