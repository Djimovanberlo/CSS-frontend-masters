# Week 1

## Why animate?

1. Guidance and clarification

2. Style and branding

## Fundamentals

### Duration

How long an ITERATION of an animation takes to compplete

- A loader could be infinite, but its iteration is 1-2 sec.

### Delay

How long it takes before an animation starts

### Timing functions

The easing of an animation (cubic bezier: imagine a line-graph with time on X and progression on Y)

- https://cubic-bezier.com/
- Recommendation for cubic bezier: keep the Y values on 0 and 1 like so: cubic-bezier(0.5, 0, 0.5, 1)

### CSS Variables

Also known as CSS custom properties, because they are inherited and cascade

### What to animate

👍 transform and opacity (GPU)
✅ color and background (GPU)
❌ height, width, left, right, margin, padding etc (CPU, expensive, try to avoid)

- https://csstriggers.com

# Week 2

## Transitions

- Transistion between two states - in some libraries called 'tweens'.
- Use transition when you want to leave the 'animation' between two states to CSS.
- Lots of built in CSS states: :hover, :active, :target, :focus etc

# Week 3

## Animations

While transitions are used to transition between two states, animations can be used to explicitly tell CSS what happens between those states (keyframes).

After an animation is complete or if there's a delay on it, it resets to initial state. This can be changed by:

- animation-fill-mode: forwards / backwards / both
  These properties whether and how an animation ends: does it reset when it ends? Does it stay in the final state? Etc

Debugging in chrome dev tools is made easy

- Open dev tools
- CMD + Shift + P
- Type Animations
- Reload the page
- Inspect & play with animations

## Choreography

Animations and transitions that coordinate with one another.

- Use delay & CSS variables to time different animations.
- Use inline CSS variables (style="--i: 1" for iterations); you can access these CSS variables in your CSS file to calculate delays and such

## States

- Use data html element as state to pass state of a component: HTML: <div data-state="loading" />, CSS: &[data-state="loading"] {...}

## Layout animation

- As described before, we tend to want to avoid layout animation, because they require CPU. So ideally we use transform and opactiy. But sometimes, we do wanna do animations for layout: changing width, height and other properties.
- FLIP technique: First, Last, Invert, Play
- F: get the initial state of the element (element.getBoundingClientRect)
- L: get the final state, after it's changed
- I: calculate the deltas to move the element BACK to its original state (so it looks like it's in the first position, but actually it's in the last position, with inverted values)
- P: Then animate everything to 0 - so this represents the final state
- https://codepen.io/davidkpiano/pen/EbwrQQ

---

### Ideas for Sl library

Setup

- Mixin for smooth dropdown
- Scale + shadow for clickable cards
- Fade / slide iteratively for forms - using choreography
- Shake button and/or input when it is faulty
- Some effects for button:hover - shine, scale, fill color from direction, iteratively animate containing letters
- Button:active (so onClick) - scale down
- Fix Next Image with relative position of wrapper (?) and layout="fill"
