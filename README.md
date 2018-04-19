# react-sticky-footer

A simple sticky footer for React.

## This component is a work in progress!


## What Sticky Footer does?

The sticky footer will stick to the bottom of the browser, on pages with long content. Once the user scrolls to the bottom the sticky footer will disappear, and will display the footer at the end of the content (in relation to where the StickyFooter tag was placed in your document).

If the content size changes without a scroll, the component will auto-refresh its state to determine if it should display the sticky footer or not.

## What Sticky Footer doesn't do

On content shorter than your browser's height, the sticky footer will render below the content, and will not stick to the bottom. I may add an option to stick to the browser in these cases.

## How do I use it?

```jsx
    <StickyFooter
        bottomThreshold={50}
        normalStyles={{
        backgroundColor: "#999999",
        padding: "2rem"
        }}
        stickyStyles={{
        backgroundColor: "rgba(255,255,255,.8)",
        padding: "2rem"
        }}
    >
        Add any footer markup here
    </StickyFooter>
```

## How can I control the sticky footer?

### Props

__targetElementId__ (optional): The ID of an element you'd like to use to watch for mutations that will tell the component it should check whether to display the footer or not. This is typically the element that is the immediate parent of the content you want to use StickyFooter on. The default is the document body.

__bottomThreshold__ (optional): A value that tells the component how close to the bottom should the scroller be before the sticky footer hides and displays at the end of your content. The default is 0, meaning the user needs to scroll all the way to the bottom before the footer hides. A number greater than 0 would cause the sticky footer to hide at some point before the user has scrolled all the way down, depending on the value of the number.

__stickAtMultiplier__ (optional): A value that tells the component how much the user should scroll back up before the sticky footer shows up again. The default is 0.001. A number greater than the default would require the user scroll up more before the sticky footer shows up.

__stickyStyles__ (optional): Styles to be applied to the sticky footer only.

__normalStyles__ (optional): Styles to be applied to the footer in its standard location only.

__onFooterStateChange__ (optional): Callback that informs when the state of the footer has changed from sticky to being in normal document flow, via boolean argument. true means it is in normal flow, false means it is sticky.
