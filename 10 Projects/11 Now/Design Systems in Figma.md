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
# Design systems in Figma

Written course here: [Introduction to design systems (5 parts) – Figma Learn - Help Center](https://help.figma.com/hc/en-us/sections/14548397990423-Introduction-to-design-systems-5-parts)



![[Design system.png]]

Design system communicates the "what", "how" and "why".

Key parts of a successful design system:

1. Principles
2. Foundations
3. Documentation
4. Processes


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

Colors can have different meaning in different cultures. Eg. Red is danger in West, but prosperity in the East (White is the dangerous color in the East)

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

Shadows on button hover/click, overlays, etc...
Can communicate interactions.

Not often uses on mobiles (here typically just buttons, car or menus).

Do not use true black as a shadow color. Use a socolr from your color palette instead. Use blur.

### Iconography

Good icons can enhance company's visual identity. Provides consistent user experience.

Icons should be functional and recognizable.

Typical icon dimensions are: 16x16, 24x24, 32x32

All icons should be consistent in their dimensions. If not you can align them with icon grid (see lesson 3):

![[Pasted image 20240918111755.png]]




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

NOTE: Set your nudge values to 8. Nudge value is number of pixels (like "precision") an element is moved with arrow keys.


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

Eg. mobile tab bar menu indicating (with little dot) on which scree we are right now:

![[Pasted image 20240918113613.png]]



Sources:

[Define your design system's foundations - Lesson 2 part 2 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=o9CloFonY0E&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=4)

## 3. Documentation (How)

Also grows and evolves over time.

Try to put yourself in a position of someone who never seen the documentation. The user needs to be able to get oriented.

Any (new) terminology in the documentation needs to be defined.

Use bright colors, not pastel colors.

Use primary button style for the most important or main CTA. Primary button is the main action. If there are multiple actions on the screen, use secondary button style. Secondary buttons are non-critical actions.

Always use tokens, semantic naming, component naming.

Document design of different states/variations of buttons/components:

![[Pasted image 20240917155006.png]]

Sources:

[Define your design system's documentation - Lesson 2 part 3 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=sHF6JSPWbzM&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=5)


## 4. Processes

Specification of how to manage the design system. Eg. how to make updates to the system and share them with others, how to get feedback/comments, how to approve the changes, how to provide training etc.

Well defined processes should help to grow yours ever evolving design system.

Processes will prevent to break down the system.

Sources:

[Define your design system's processes - Lesson 2 part 4 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=NGGMGybuOwg&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=6)


## 5. Building own design system

### Styles

Collection of properties or settings (color, typography, shadow, blur, reusable scaffolding for grids) to be reused.

### Components

Reusable elements or collections of elements.
Always use the description property of the component to describe its function.

You can use *bulk rename* to rename multiple similar components.

When component is copied, an instance is created.
All changes in main component is immediately visible in all its instances

![[Pasted image 20240918102728.png]]

![[Pasted image 20240918102751.png]]


### Libraries

A collection of styles and components shared within a team or organization.
Library establishes consistency and keeps elements up to date.

Each library is linked to a file. 
Library can use styles and components from another library.
You can keep everything in one file or break it into multiple files.

![[Pasted image 20240918103229.png]]

### Atomic design

Modular approach to build a design system from scratch based on atoms-molecules-organisms analogy:

![[Pasted image 20240918103717.png]]

#### Atoms

Elements that can not be broken down any further (element would loose its function otherwise).

For example:

Icons

![[Pasted image 20240918104131.png]]

input labels

![[Pasted image 20240918104156.png]]

or buttons

![[Pasted image 20240918104226.png]]


#### Molecules

A collection of individual elements (atoms) forming a single unit.

Eg. search bar:
![[Pasted image 20240918104057.png]]


#### Design

Complex structures made up of molecules and atoms.

Eg. navigation menu

![[Pasted image 20240918104434.png]]

 Always align with devs on naming conventions (so that component names and variable names are the same). For web camelCase is a standard (because of javascript).

Source:  [Atomic Design Methodology | Atomic Design by Brad Frost](https://atomicdesign.bradfrost.com/chapter-2/)
### Colors

You can use functional approach to name your color styles. 

![[Pasted image 20240918110531.png]]


Use semantic naming. Slash naming convention

![[Pasted image 20240918110653.png]]

![[Pasted image 20240918110719.png]]


### Typography

Use semantic type system.

We can use slash naming to create types for titles and body for example.

![[Pasted image 20240918111116.png]]


### Icons

Icons should be components. Use component description to describe them.
Use slash naming conventions and put them into assets.

![[Pasted image 20240918112054.png]]


### Illustrations

Should have consistent frame sizes (like icons)

![[Pasted image 20240918112335.png]]

One illustration can be used in multiple context. Always use semantic naming:
(NOTE: The accent color changes. Also the frame dimension is different)

![[Pasted image 20240918112604.png]]


Sources:
[Material Design](https://m3.material.io/)
[Space Grotesk - Google Fonts](https://fonts.google.com/specimen/Space+Grotesk)
[Components, styles, and shared library best practices](https://www.figma.com/best-practices/components-styles-and-shared-libraries/)
[Component architecture in Figma](https://www.figma.com/best-practices/component-architecture/)
[Creating and organizing Variants](https://www.figma.com/best-practices/creating-and-organizing-variants/)


[Lesson 3: Build your design system – Figma Learn - Help Center](https://help.figma.com/hc/en-us/articles/14548865734679-Lesson-3-Build-your-design-system)
[Build your design system - Lesson 3 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=0XSLMGh8yhM&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=7)




## 6. Document, improve and update your design system

### Effective documentation





Sources:

[Document, improve and update your design system - Lesson 4 : Introduction to design systems - YouTube](https://www.youtube.com/watch?v=_sTWtnNU1L0&list=PLXDU_eVOJTx6vqOWJSWH87Zb5-riiG63A&index=8)
[Lesson 4: Document and manage your system – Figma Learn - Help Center](https://help.figma.com/hc/en-us/articles/14552804059927-Lesson-4-Document-and-manage-your-system)


[Overview - Get started - Atlassian Design System](https://atlassian.design/)
[Storybook: Frontend workshop for UI development](https://storybook.js.org/)
[figma.com/community/plugin/801195587640428208/design-lint](https://www.figma.com/community/plugin/801195587640428208/design-lint)
[figma.com/community/plugin/751892393146479981/roller-design-linter](https://www.figma.com/community/plugin/751892393146479981/roller-design-linter)
[How to do Design Research? | Figma](https://www.figma.com/resource-library/design-research/)
[Semantic Versioning 2.0.0 | Semantic Versioning](https://semver.org/)
[Guide to branching – Figma Learn - Help Center](https://help.figma.com/hc/en-us/articles/360063144053-Guide-to-branching)
