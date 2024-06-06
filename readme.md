## Setting up KeyFrame Animations

-   The `@keyframes` syntax

```css
@keyframes nameOfAnimation {
	...;
}
```

-   When the keyframes is defined, you “attach” the
    animation to an element by using the animation-name property.

## Defining Keyframe Selectors

-   Keyframe selectors define points during an animation where we set the
    values of the properties we want to animate. If you want a value at the start
    of the animation, you declare it at the 0% mark. If you want a different value
    at the end of the animation, you declare the property value at the 100%
    mark. If you want a value a third of the way through the animation, you
    declare it at the 33% mark. These marks are defined with keyframe
    selectors.
-   Keyframe selectors consist of a comma-separated list of one or more
    percentage values or the keywords from or to. The keyword from is equal
    to 0%. The keyword to equals 100%. The keyframe selectors are used to
    specify the percentage along the duration of the animation the keyframe
    represents. The keyframe itself is specified by the block of property values
    declared on the selector. The % unit must be used on percentage values. In
    other words, 0 is invalid as a keyframe selector:

```css
@keyframes animation_identifier {
	keyframe_selector {
		property: value;
		property: value;
	}
	keyframe_selector {
		property: value;
		property: value;
	}
}
```

```css
@keyframes fadeout {
	from {
		opacity: 1;
	}
	to {
		opacity: 0;
	}
}
@keyframes color-pop {
	0% {
		color: black;
		background-color: white;
	}
	33% {
		/* one-third of the way through the animation */
		color: gray;
		background-color: yellow;
	}
	100% {
		color: white;
		background-color: orange;
	}
}
```

```css
div {
	animation-name: change_bgcolor;
}
```

-   Giving the animation life

```css
div {
	animation-name: change_bgcolor;
	animation-duration: 400ms;
	animation-iteration-count: infinite;
	animation-timing-function: cubic-bezier(0.2, 0.4, 0.6, 0.8);
	animation-direction: alternate-reverse;
}
```

## Animation properties

-   `animation-name:` The animation-name property takes as its value a comma-separated list of
    names of keyframe animations you want to apply to the selected elements.
    The names are the unquoted identifiers or quoted strings (or a mixture of
    both) you created in your @keyframes rules
-   `animation-duration:` The animation-duration property defines the length of time, either in
    seconds (s) or milliseconds (ms), it should take to complete one cycle
    through all the keyframes of the animation. If you don’t declare
    animation-duration, the animation will still be run with a duration of 0s,
    with animationstart and animationend still being fired even though theanimation, taking 0s, is imperceptible. Negative time values are not
    permitted for animation-duration.
-   `animation-iteration-count: `By default, the animation will occur once
    (because the default value 1).If another value is given for animation-iteration-count, and there isn’t a negative value for the animation-delay property, the animation will repeat
    the number of times specified by the value of the property, which can be
    any number or the keyword infinite.
-   `animation-direction:`The animation-direction property defines the direction of the
    animation’s progression through the keyframes. It has four possible values: `normal`, `reverse`, `alternate`, `alternate-reverse`.
-   `animation-timing-function:` The animation-timing-function property describes how the
    animation will progress from one keyframe to the next.
-   `animation-delay:` By default, an animation begins iterating as soon as it is applied to the
    element, with a 0-second delay. A positive value for animation-delay
    delays the start of the animation until the time listed as the value of the
    property has elapsed.

## The `animation` shorthand property

-   The animation shorthand property allows you to use one declaration,
    instead of eight, to define all the parameters for an element’s animation.
    The animation property value is a list of space-separated values for the
    various longhand animation properties. If you are setting multiple
    animations on an element or pseudo-element, you can use a comma-
    separated list of animations.
-   The animation shorthand takes as its value all the other animation
    properties, including animation-duration, animation-timing-
    function, animation-delay, animation-iteration-count, animation-
    direction and animation-name.

```css
#animated {
	animation: 200ms ease-in 50ms 1 normal slidedown;
}

/* The above short hand is equal to the longer declaration below */
#animated {
	animation-name: slidedown;
	animation-duration: 200ms;
	animation-timing-function: ease-in;
	animation-delay: 50ms;
	animation-iteration-count: 1;
	animation-direction: normal;
}
```
