# Fundamentals

it is important to train my design muscle.

The more time you spend looking at beautiful design. the more easily you will be able to differentiate it from bad design. Train your eye by consuming and eventually you'll get to the point where it's kind of second nature.

Always ask myself or a friend how the design make me/him feel?
## 8px grid system

Helps us with consistency.

Is further divisible by 4 or 2 in comparison eg 5px so we can get more values (2,4,6,8,10,12,14,16,18,20 vs.  5,10,15,20,25,30). Its much more granular.

Works well with % based font-sizes (rem).

![[Screenshot 2024-09-27 at 10.05.16.png | 350]]

If we'd like to achieve the same with say 10px it would be horrible.
This does not help anybody:

![[Pasted image 20240927100619.png | 350]]

## Responsivenes

### Breakpoints
In Figma these breakpoints are enough:

- Desktop *1440px*
- Tablet *810px*
-  Phone *390px*

### Guides
For Figma guides (columns).

#### Desktop 

Use 12 *columns* with 23-40px gaps.

You can easily divide them:

![[Pasted image 20240927101809.png | 350]]

You can use any combination

![[Pasted image 20240927101842.png | 350]]

Use 24-64px *margins*

![[Pasted image 20240927102510.png | 350]]


Do not forget to set max-width! It is a good practice.

Unless you want intentionally some element (eg. picture) to go edge to edge on big size screens). 

If an element do not have max width, you should document it.
### Tablet

6 columns, 32 gaps and margins

![[Pasted image 20240927102709.png | 350]]


### Phone

2-4 columns, 24px



![[Pasted image 20240927102757.png | 350]]


## Spacing

There are no actual rules to follow. Should this card have 24px margin or 32? Should the icon after text has gap 4px or 8 px? It depends... there is no rulebook.

We can ask these questions to help decide:

- Is the spacing helping group the right content together to help the user understand what UI elements are related to each other?
- Is there enough space between the elements to actually feel comfortable?
- Does anything feel visually unbalanced?
- Does the spacing feel coheive? Whether it is a single UI element, section or the whole site. (Its always good to take step back and just see how cohesive your spacing and layouts are feeling. This is an ongoing thing, always check this.). 

## Colors

Again, no rules to follow on how many colors should I use or how do I pick my color palette.

The easiest way is to follow 60/30/10 rule.

60% dominant color (background color)
30% secondary color (content/text color)
10% accent color (primary brand color) this color should "pop out" (eg CTA)

Additionally you can add whatever new colors or variations of these 3 colors. Whatever is needed to bring the web into life.

Matts 3 color principles:

### 1. Cohesive

Color palette must be cohesive. The colors must belong together.

You can just simply follow the color wheel color theory using whatever tool. Eg.

#### Platette

[Coolors - The super fast color palettes generator!](https://coolors.co/)

#### Shades
Once you have the palette, you can add shades intense to colors that need darker or later versions for whatever reason, eg. hover and click state that need to be darker (eg. two shades darker).  Or darker version for background for different sections.

For this you can use shade generator:

[Tailwind Color Generator](https://uicolors.app/create)

### 2. Reflect the brand

The color palette should reflect the brand and its emotion.

This is where color psychology comes in.

![[Pasted image 20240927143823.png]]

See also [[Episode 7 - Colors]]


### 3. Accessibility

Your palette should be accessible. 

*AA* should be minimum.

2 levels of contrast ratio (ratio of 2 colors)

#### 4.5:1 contrast ratio

Two color set. It means that the text can be used at any size and weight.
That's what you're the primary when you're trying to hit.

#### 3:1 contrast ratio

That means if text hit this, you can use this text if it's 24 pixels or above at any weight or between 19-23 pixels bold or heavier.

For any two color that are less than 3:1 they can be used for decorations which are not parts of the text.

You can use online tools for that:
[Colour Contrast Checker](https://colourcontrast.cc/)

[Contrast | Figma](https://www.figma.com/community/plugin/748533339900865323/contrast)


## Typography

NOTE: Matt hates the Inter font :) 

### Choosing right font

It's a design muscle you have to train.

Rounded sans-serif aree more playful, youthful and approachable

![[Pasted image 20240927145143.png]]

while grotesque font on the other hand is more minimal and serious, more sophisticated and maybe more trusworthy

![[Pasted image 20240927145328.png]]

But at the end, you have to just see and feel which fonts are looking good. If it looks nice or not.
And there is no formula for that, it's just instinct.

As for design, I need to practice my typography muscle. Eventually I will see it.
But until than I need to be more thoughtful and inquisitive about all my design decisions.

I have to always ask myself why my font choice properly reflects the brand. I must be able to rationalize that.

Ask what emotions am I feeling with this font?
Even better: ask a friend how this font make him feel?

### Pairing fonts

Choosing second font is even harder. Some guidelines:

#### 1. No more than 2 or 3

Don't use more than 2-3 fonts per site. Often 1 is enough.

#### 2. Intentional & different

It must be obvious that the font pairing is intentional and different enough. It does not make sense to pair two sans-serif together.

![[Pasted image 20240927150816.png]]

More natural a combo of Serif and sans-serif fonts. Eg. if one font for Title, second for body.

![[Pasted image 20240927150911.png]]


### Weights

Purpose is to establish hierarchy. Help elements stand out like button or a link.

Headline should be heavier than body to let the user know this is more important.


![[Pasted image 20240927151428.png]]
#### Bold or semibold?

Matt stopped using Bold weight and uses only semibold and regular to reduce the gap in the weights to make it feel more harmonious. But this depends on the overall aesthetics of the design and the font type.

#### Letter spacing

Matt uses -2% to -4% of letter spacing.

even Inter looks better with -2% :)

![[Pasted image 20240927152921.png]]

#### Line height

##### Titles

For titles typically 100% plus minus 10% depending on the font. It does a good job of keeping the title tight and makes it feel like a title, a solid block. 

If you open it too much it feel amateur.

##### Paragraphs

Typically 120-144% does the trick and makes it breathe more. It makes it a lot easier to read and more relaxed.


#### Font sizes

There is not a standard use. But Matt typically:

##### Body

Matt starts from 16 pixels and go up. Rarely go down for main body copy. (He might go down for footer?).

##### Titles

He uses 1.5 multiplier:

1. Multiply body by 1.5 (or 2 sometimes)
2. Choose number within 8px grid in that range

And than from there you can increase the title from here.

This is like the golden ratio btw:

![[Pasted image 20240927154547.png | 350]]


## Graphics

Matt refers to any media on your site that is graphics: Images, Videos, Icons, Illustrations, 3d objects.

