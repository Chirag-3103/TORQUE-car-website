# Responsive Design — Common Device Widths & Breakpoints

A quick reference for planning and testing responsive websites, including **TORQUE**.

> **Important:** These are practical viewport-width ranges, not exact rules for every device. Choose breakpoints where your layout starts to look cramped or break, rather than targeting every phone model. Viewport width in CSS pixels is what media queries usually test.

## 1. Common viewport widths

| Device / layout category | Useful widths to test |
|---|---:|
| Small mobile phones | 320px, 360px |
| Typical mobile phones | 375px, 390px, 393px |
| Larger mobile phones | 414px, 430px, 440px |
| Small tablets / tablet transition | 600px, 744px, 768px |
| Tablets | 800px, 820px, 834px |
| Tablet landscape / compact laptop | 1024px |
| Laptops | 1280px, 1366px |
| Desktop monitors | 1440px, 1600px |
| Full HD desktop | 1920px |

These are examples to test, not a list of every device's exact screen resolution. Screen resolution and browser viewport width are not always the same.

## 2. Practical CSS breakpoint starting points

| Breakpoint | Common use |
|---|---|
| `480px` and below | Small mobile adjustments |
| `481px–767px` | Larger phones and small screens |
| `768px–1023px` | Tablet layouts |
| `1024px–1279px` | Tablet landscape / smaller laptops |
| `1280px–1439px` | Standard laptop / desktop layouts |
| `1440px` and above | Wide desktop layouts |

These ranges are a starting point only. You do **not** need a media query for every row. Add one only when the layout needs to change.

## 3. Example media queries

```css
/* Base styles: start here */

/* Small phones */
@media (max-width: 480px) {
  /* Adjust layout for narrow screens */
}

/* Tablets and larger phones */
@media (min-width: 481px) and (max-width: 767px) {
  /* Adjust layout for this width range */
}

/* Tablets */
@media (min-width: 768px) and (max-width: 1023px) {
  /* Adjust layout for tablets */
}

/* Smaller laptops */
@media (min-width: 1024px) and (max-width: 1279px) {
  /* Adjust layout for compact desktop widths */
}

/* Wide desktop */
@media (min-width: 1440px) {
  /* Optional adjustments for wider screens */
}
```

## 4. A good testing routine

For each breakpoint, test:
- Just **below** it (for example, 767px)
- At the breakpoint (768px)
- Just **above** it (769px)

Also test a few widths between breakpoints. This can reveal layout issues that testing only a few preset devices misses.

## 5. Responsive design reminders

- Include the viewport meta tag in your HTML:
  ```html
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  ```
- Use flexible layouts with **Grid**, **Flexbox**, percentages, `rem`, `minmax()`, and `max-width` where appropriate.
- Make images responsive, for example:
  ```css
  img {
    max-width: 100%;
    height: auto;
  }
  ```
- Prefer **mobile-first** styling when it suits your workflow: write the narrow-screen base layout first, then add `min-width` media queries as more space becomes available.
- Avoid creating a media query for every device model. Change the layout when the content needs it.

## References

- [MDN: Responsive design](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design)
- [MDN: Media query fundamentals](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Media_queries)
- [Bootstrap: Responsive breakpoints](https://getbootstrap.com/docs/5.0/layout/#breakpoints)
