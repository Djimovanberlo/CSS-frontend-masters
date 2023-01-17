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

Debugging in chrome dev tools is made easy

- Open dev tools
- CMD + Shift + P
- Type Animations
- Reload the page
- Inspect & play with animations

## Choreography

Animations and transitions that coordinate with one another

---

### Ideas for Sl library

Setup

- Use CSS variables instead of SASS variables, since they can be used in JS
- useRef to change element styles using CSS variables as string: "--main-color"
- enum to match the colors/CSS variables: "enum COLORS { main: "--main-color" }
- Shake button and/or input when it is faulty
