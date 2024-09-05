---
up:
  - "[[Home]]"
related: 
created: 2024-08-13
rank:
---
![[Exp]]





> [!Watch]+ # House maintenance
> House efforts with a rank above `3`.
> 
> ```dataview
> TABLE WITHOUT ID
>  file.link as "",
>  rank as "Rank"
> 
> FROM "Spaces/Personal/3_Resources/Notes/House"
> 
> WHERE rank > 3
> 
> SORT rank desc
> ```