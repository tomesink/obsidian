---
zettel:
  - Fleeting Note
topic:
  - "[[Webdesign]]"
references: 
status:
  - To Do
related: 
URL: https://www.youtube.com/playlist?list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A
type: "[[Card]]"
created: 2024-09-09
tags:
---
# Design system

Written course here: [Introduction to design systems (5 parts) – Figma Learn - Help Center](https://help.figma.com/hc/en-us/sections/14548397990423-Introduction-to-design-systems-5-parts)



![[Design system.png]]

Design system communicates the "what", "how" and "why".

Key parts of a successful design system:

1. Principles
2. Foundations
3. Documentation
4. Process


Sources:
[Welcome to design systems - Lesson 1 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=YLo6g58vUm0&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=3)
[Define your design system's principles - Lesson 2 part 1 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=pwzYVIgga2c&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=4)


## 1. Principles (Why)

This is the principles (why?). eg. "Be accessible and inclusive". 
The message the company communicates.


## 2. Foundations (What )

Visual styles, colors, typography, components.
Patterns: Behaviors, Strucutres, Conventions

### Accessibility

Always have accessibility (A11y) in mind. This could mean also dark mode, large enough buttons, missing alts on images.

- [Web accessibility checklist - MagentaA11y](https://www.magentaa11y.com/web/)
- [Colorblind Accessibility Manifesto](https://colorblindaccessibilitymanifesto.com/)
- [Library: Accessibility resources, guides, communities, and more](https://www.getstark.co/library/)

### Colors

Colors can have different meaning in different cultures. Eg. Red is danger in West, but prosperity in the East.

Can create hierarchy.

Have your color palette as simplified as possible (you can grow it later as the project evolves). It is advised to simplify similar colors into one. Avoid having multiple colors for primary buttons (eg. 5 colours).

Use 60-30-10 rule to create balance: 60% should be neutral color, 30% primary color, 10% should be secondary color or call to action color if we have one. You can add more colors/shades as the system evolves. 

[figma.com/community/search?resource\_type=plugins&sort\_by=relevancy&query=color+contrast&editor\_type=all&price=all&creators=all](https://www.figma.com/community/search?resource_type=plugins&sort_by=relevancy&query=color+contrast&editor_type=all&price=all&creators=all)

[Using Color to Enhance Your Design](https://www.nngroup.com/articles/color-enhance-design/)

[Color | Design Systems Guide](https://www.designsystems.com/color-guides/)

[Color Theory 101: Color Wheels, Color Schemes, and Why Everything You Think You Know About Color Might Be Wrong](https://blog.hubspot.com/marketing/color-theory-design)

### Typography

Base/body text size often 16px. Use scales for scaling the base font consistently:

You can use the **major third (1.25)**:
`16 * 1.25 = 20 * 1.25 = 25 * 1.25 = 31.25`
`16 / 1.25 = 12.80 / 1.25 = 10.24`

Or **perfect forth (1.333)**.

In Figma we can use several plugins for scaling (see links bellow).

If we use 8pt grid system, we should round the type size to the nearest number which is multiple of 8. Do the same for the line height.

Example of web type hierarchy:

![[Pasted image 20240916174640.png]]

Mobile apps usually have different classification hierarchy:

![[Pasted image 20240916174812.png]]

You can have different fonts for headings and for text (eg. for blogs).

Prevent having too many type sizes. You will usually use them in a wrong way.



[Typescale | Figma](https://www.figma.com/community/plugin/967802396210455992/typescale)

[Scaaale | Figma](https://www.figma.com/community/plugin/892543384437155629/scaaale)

[Kick-start your typography system in Figma](https://www.figma.com/best-practices/typography-systems-in-figma/)

[Typescale - Create stunning typography, generate CSS, and find inspiration.](https://typescale.com/)


### Elevation

Shadows on button hover, overlays, etc...
Do not use them on mobiles. 

Do not use true black as a shadow color. Use a socolr from your color palette instead. Use blur.

### Iconography

Good icons can enhance company's visual identity. Provides consistent user experience.

Icons should be functional and recognizable.

[A complete guide to iconography](https://www.designsystems.com/iconography-guide/)


### Spacing, grids & layouts

We need to have a consistent spatial system. Consistency is everything.

Confilcting or competing values create ambiguity.

#### Layouts

Use different layouts for different screen sizes (responsive):

 ![[Pasted image 20240916181608.png]]

![[Pasted image 20240916181640.png]]


#### Grids

Example of **grid** usage:

![[Screenshot 2024-09-16 at 18.03.27.png]]

On desktop 8-12 grids is a standard.

The space around the edge of the grid is called *margin* and the gaps amongst columns are called *gutter*.

**baseline grid** is a horizontal grid. Makes sure the vertical spacing is consistent.

8pt baseline grid is the standard. You position the elements relative to the baseline. The vertical space between elements is always divisible by 8:

![[Pasted image 20240916181045.png]]

The height of the elements is also divisible by 8:

![[Pasted image 20240916181223.png]]

The baseline plays role in the type system as well:

![[Pasted image 20240916181323.png]]

There can be many more grid types:

![[Screenshot 2024-09-16 at 18.14.27.png]]

Once you are familiar with the grid rules, you can break these rules and go outside the grid:

![[Screenshot 2024-09-16 at 18.18.00.png]]

#### Spacing

Helps establishing hierarchy and relationships between objects.
We are talking about paddings, margins and any extra spacing  here.

Relate to the grid system. The base space in 8pt grid system is 8. And we work with multipliers of 8 here.

Do not forget to document exceptions like 4px.

[Spacing, grids, and layouts](https://www.designsystems.com/space-grids-and-layouts/)



### Patterns

Reusable solutions for common user goals.



Sources:

[Define your design system's foundations - Lesson 2 part 2 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=o9CloFonY0E&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=4)

## 3. Documentation (How)

Also grows and evolves over time.

Try to put yourself in a position of someone who never seen the documentation. The user needs to be able to get oriented.

Any (new) terminology in the documentation needs to be defined.

Use bright colors, not pastel colors.

Use primary button style for the most important or main CTA. Primary button is the main action. If there are multiple actions on the screen, use secondary button style. Secondary buttons are non-critical actions.

Always use tokens, semantic naming, component naming.


Sources:

[Define your design system's documentation - Lesson 2 part 3 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=sHF6JSPWbzM&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=5)

