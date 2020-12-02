# FitText.js, a ~jQuery plugin~ library for inflating web type
FitText makes font-sizes flexible. Use this plugin on your responsive design for ratio-based resizing of your headlines.

## How it works
Here is a simple FitText setup:

```html
const fitText = require("plainjs-fittext");
fitText(".fit-text")(1.5);
```

Your text should now fluidly resize.

## The Compressor
If your text is resizing poorly, you'll want to turn tweak up/down "The Compressor". It works a little like a guitar amp. The default is `1`.

```javascript
fitText("#responsive_headline")(1.2); // Turn the compressor up   (resizes more aggressively)
fitText("#responsive_headline")(0.8); // Turn the compressor down (resizes less aggressively)
```

This will hopefully give you a level of "control" that might not be pixel perfect, but resizes smoothly & nicely.

## minFontSize & maxFontSize
FitText now allows you to specify two optional pixel values: `minFontSize` and `maxFontSize`. Great for situations when you want to preserve hierarchy.

```javascript
fitText("#responsive_headline")(1.2, { minFontSize: '20px', maxFontSize: '40px' });
```

## CSS FAQ

- :warning: Run FitText before anything that hides the element you're trying to size (e.g. before Carousels, Scrollers, Accordions, Tabs, etc). Hiding an element's container removes its width. It can't resize without a width.
- :warning: **Make sure your container has a width!**
  - `display: inline` elements don't have a width. Use `display: block` OR `display: inline-block`+ a specified width (i.e. `width: 100%`).
  - `position:absolute` elements need a specified width as well.
- Tweak until you like it.
- Set a No-JS fallback font-size in your CSS.
- :new: If your text is full width, you might want to **NOT** use FitText and just use CSS `vw` units instead. Supported in all major browsers.

### Download, Fork, Commit.
If you think you can make this better, please Download, Fork, & Commit. We'd love to see your ideas.
