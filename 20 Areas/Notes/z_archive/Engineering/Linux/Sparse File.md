---
up: 
tags: []
URL: https://www.youtube.com/watch?v=eyRNL6fGDM8&list=PLDadzdouM0VBq9HdgalQkqFKvM7uSaj9L&index=8
---

A sparse file is a special type of a file for which we can set its
filesize but we do not have to write any actual data into it.
Such files uses zero blocks

A sparse file can be created using **truncate** utility.

Not all filesystems support sparse files!!!

Example: Create file bigger more than _Available_ disc size

```shell
 df /tmp
Filesystem   512-blocks      Used Available Capacity iused      ifree %iused  Mounted on
/dev/disk3s5  965595304 470827760 454588944    51% 2262294 2272944720    0%   /System/Volumes/Data

mkdir /tmp/$USER/big
export BIG=/tmp/$USER/big

df /tmp | tail -1 | awk '{print $4}'
454588944

truncate -s $(df /tmp | tail -1 | awk '{print}')000000 $BIG

ls -la $BIG
```

`du` comamnd of the BIG file would now show zero bytes written into that
file

but `stat` command shows the file is of a really big size