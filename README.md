# Tailwind CSS @apply Directive Bug with Pseudo-selectors

This repository demonstrates a bug in Tailwind CSS where the `@apply` directive fails to apply styles defined within pseudo-selectors such as `:hover` or `:focus`.

## Bug Description

When using the `@apply` directive with a class containing a pseudo-selector, only the base styles are applied. The styles for the pseudo-selector states are ignored.

## Reproduction Steps

1. Clone this repository.
2. Open `bug.html` in your browser.
3. Observe that the button's background color doesn't change on hover.

## Solution

Instead of using `@apply` with pseudo-selectors, directly apply the hover styles to the element:

```html
<button class="hover:bg-blue-500">
  Click me
</button>
```

Alternatively, you can apply the base class and the hover class separately.

## Additional Notes

This issue is likely due to the way `@apply` processes and merges CSS classes.  It doesn't handle the nested nature of pseudo-selectors effectively. The recommended solution is to avoid using `@apply` with pseudo-selectors.