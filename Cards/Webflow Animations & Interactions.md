---
zettel:
  - Permanent Note
topic:
  - "[[Web]]"
references: 
created: 2024-09-01
status:
  - Done
URL: https://university.webflow.com/courses/interactions-and-animations-course
tags:
  - webflow
  - animation
---
## Animation basics

The basic animation is a movement. And the basic movement of an object callled:
#### Interpolation
It is a movement of an object (element) from point A to point B.
Generaly in animation or motion design it can be done by keyframing (eg. in After Effects).

Webflow does keyframing/interpolation for us. 
#### Easing
With easing we can control acceleration of moving of and object. It is a non linear movement without constant speed.
We can be slow at the beginning and accelerate at the and, or vice versa. We can let an element bump into a view etc.

#### Smoothing
It slows down or lags the animation so it is not happening in real time. It softens or smooth out the approaching velocity towards the correct position in the timeline.

If we move with a mouse there is a lagging with smoothing (if set in webflow).
## How to begin in Webflow?

At start we need to choose the correct trigger. We have two options:
#### Page trigger
A webflow animation is triggered when there is a change in the page state (page load, move mouse in viewport, page is scrolling).

#### Element trigger
Triggers the animation when we interact with an element or class (mouse click, hover, scrolling into View).
Element trigger does not have to necessarily animate itself. We can eg. animate element B when element A is clicked.

#### Timeline
This is where most of the work happening. Do not forget to set an initial state of an animation. Also we can select multiple actions by holding the CMD button on mac.
The "keyframing" is done with percentages.

#### Quick effects
They do not require timeline. Much more simple.
Can be applied on element or class (and combo classes).

There are three main types of quick effects:
##### Slide
Scroll into view action.
The slide happens when element scrolls into the viewport.
##### Grow
Scroll into view action.
They are growing into the view when scrolling into the viewport.
##### Rubber band
Mouse hover effect. Typically over a button.

## Main types of interactions

#### Horizontal movement on scrolling
We can fade out text elements or pictures when scrolling a page.
Just add a page trigger and adjust movement on x axis and opacity (if needed).
#### Paralax effect
Paralax effect is when objects which are closer to a viewer or ("screen") apppear to move faster than objects behind them.
This can be achieved with setting of by how many pixels the element is moving. The more pixels the more speed.
We must not forget to set correct z-index on the elements inside the section.

#### Rotation on hover
For this interaction we need to setup Element trigger with "move mouse over element".
Then set mouse `x` nad mouse `y` action with `rotate` parameter.
Its advised to use `Smoothing`.

We can also set resting state - a default state of the element before animation. A point over which the animation/rotation happens. Or a point where our mouse pointer would be at the beginning our animation.
#### Scroll progress indicator
Scroll bar is quite popular, either horizontal or vertical. It can be [done](https://university.webflow.com/course-lesson/scroll-progress-indicator) with webflow interaction.
#### Reveal on scroll
If we wan an element to be revealed on scrolling we need to setup an Element trigger and add "Scroll into view" type animation. Do not forget to set an initial state of the animation and opacity.

Do not forget set Easing (eg. In Out Quint).

If applying on multiple elements set offset ("Interactions" → "Scroll into view" → "When scrolled into view" → Offset) so that animation is not triggered on all elements of the class in the same time.
####  Show and hide on clic
This is quite nice and [simple](https://university.webflow.com/course-lesson/show-and-hide-elements-on-click) animation. Ut could be useful eg. for podcast web pages to quickly show and hide episode descriptions. Something similar is [reveal on hover](https://university.webflow.com/course-lesson/reveal-elements-on-hover) animation.

## Using Lottie animations
We can [easily]([https://university.webflow.com/course-lesson/page-load-animation](https://university.webflow.com/course-lesson/page-load-animation)) integrate lottie files into webflow and control the way (when and how) the animation is played. 

The lottie animations can respond on scroll. We can control them in webflow by setting interaction for Lottie file and than eg. adjust percentate of the animation based on scrolling. Or we can rotate 3d objects in lottie based on mouse moving.

We can also control how videos are played back on a web page.First decompose a video into single frame images. Than make a lottie from this images (each image is a frame) in After Effects. Than use it in webflow as a standard Lottie animations