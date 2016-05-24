# Error Property Styling For Chome CSS Inspector

*Huge thank you to [@dansketchpad](https://twitter.com/dansketchpad) who did most of the work on this!*

To improve the appearance of a fake `ERROR` property to log markup errors to Chrome's CSS inspector, this extension removes the `line-through` style and replaces it with a red background and white text.

## Installation

1. Enable the devtools experiments via `chrome://flags/#enable-devtools-experiments`
2. Also enable in `Inspector > Settings > Experiments > Allow custom UI themes`
3. Go to Extensions, then turn on Developer mode (checkbox on top right)
4. Download this repository's `error-property-styling` folder
5. Under Extensions, press the **Load unpacked extension...** button to upload the extension folder
6. Close and reopen any inspector panels and you should see the style for the `ERROR` property (an unrecognized, unparsable CSS property just used for logging errors to the inspector)

## Example

### Code

```
a:not([href]) {
    ERROR: This <a> element is not focusable because it lacks an href attribute;
}

/* the below block is used to highlight the presence of the error in the interface itself  */

a:not([href]) {
  outline: 0.25em solid red;
}
```

In this case, the 'error' is triggered when an `<a>` element does not have an `href`—which would mean it is inaccessible by keyboard.

### Output

![The declaration in the CSS inspector, with the standard line-through removed and the red background style in its place](https://raw.githubusercontent.com/Heydon/css-error-property-style/master/error_href.png)

