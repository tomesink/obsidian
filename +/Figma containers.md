---
zettel:
  - Fleeting Note
topic:
  - "[[Webdesign]]"
references: 
status:
  - To Do
related: 
URL: 
type: "[[Card]]"
created: 2024-09-06
tags:
---

### Group

Multiple objects grouped together gives a single object I can interact with on the canvas in terms of size, color etc.

Group is a collection of layers and not distinct elements so they (the grouped elements) dont have dimensions or properties of their own once grouped.  Meaning, if I choose a fill (background color) property it is applied on objects inside, not on group "object" itself. So groups can not have backgrounds etc by themselves.

Group do not have autolayout (way how to create responsive design in Figma). If autolayout is applied on group it automatically converts into a frame.

### Frame

Frames are main thing we use to build UI. It can be nested inside group, group can be nested inside frame. We can put frames inside other frames.

Frame can act as a scaffolding (leseni) for different device (web page, iPhone screen...). 
Frame can be a container of other UI elements.

Unlike group, frames have they own  properties like fills, rounded corners etc. Meaning, if I choose a fill (background color) property it is applied on the frame itself, not on objects inside.

Unlike group, frames can use autolayout and layout grids.
### Section

Section tool allows me to designate and label a specific region of the canvas.

I can use sections to group related concepts and ideas or organize my designs and sections (eg. prototype flows).

Section can draw focus, give context and guide collaborators through process.

They're perfect for activities like reviews or for sharing designs for handoff  (mark as dev ready).