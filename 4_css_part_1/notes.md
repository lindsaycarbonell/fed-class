# Lesson 4: CSS Part 1
_notes adapted from_: 
- [Sarah Hudson's SlideShare](https://www.slideshare.net/shudson4/charlotte-fed-css-inheritance-and-specificity)
- [MDN Specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity)
- [MDN Cascade and Inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Cascade_and_inheritance)
- [Smashing Magazine's CSS Specificity](https://www.smashingmagazine.com/2007/07/css-specificity-things-you-should-know/)
- [W3School's CSS Specificity](https://www.w3schools.com/css/css_specificity.asp)


## CSS: Cascading StyleSheets
- Cascading: Styles are assigned from the top down
- StyleSheets: style definitions are saved in "sheet(s)" that are connected to your HTML file(s).

## Adding internal styles
- CSS can exist in three locations: 
    - inline CSS
    - internal stylesheet
    - external stylesheet
- **Inline CSS** is attached directly to the element that it is modifying in a style attribute. For example: 
    ```
    <h1 style="font-size:12px;color:red;">Title</h1>
    ```
    Will make this h1 red and have a 12px sized font.
- An **internal stylesheet** is located in the `<head>` in a `<style>` tag. For example: 
    ```
    <head> 
        <style>
            h1 {
                color: red;
                font-size: 12px;
            }
        </style>
    </head>
    ```
- The most common use case for CSS is an **external stylesheet**. In general, you want to keep all of your styles in external stylesheets to keep your code organized and your inheritance easy-to-understand. External stylesheets are separate `.css` files that are referenced in the `<head>` of every page they apply to, using a `<link>` tag.
- Internal styles (either inline or internal stylesheets) are good to use for testing CSS quickly (to be moved to an external sheet later), and when using JavaScript.

## Attaching an external stylesheet
1) Use the `<link>` tag to attach an external stylesheet.
    ```
        <link rel="stylesheet" href="" />
    ```

2) The href attribute will accept **relative URLs** or **absolute URLs**. For stylesheets that you create, you'll almost always be using a relative URL. If you use a stylesheet from a CSS library online, you'll likely use a **Content Delivery Network (CDN)**, which is represented by an absolute URL. For example, the **Bootstrap** library has a CDN for its stylesheet:
    ```
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.2.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-GJzZqFGwb1QTTN6wy59ffF1BuGJpLSa9DkKMp0DgiMDm4iYMj70gZWKYbI706tWS" crossorigin="anonymous">
    ```
All you have to do is copy and paste this CDN link and the Bootstrap CSS library will be accessible on your page.

3) But in our case, we want to use a relative URL. The URL we will be building is _relative to the file where the <link> tag is_. So if the `style.css` file is in the same directory as our `index.html` where it's being referenced, the link tag will say: 
    ```
        <link rel="stylesheet" href="style.css" />
    ```
But if we put that file in another directory called `css` that is in the same directory as `index.html`, instead we'll have:
    ```
        <link rel="stylesheet" href="css/style.css" />
    ```

## Properties
### Shorthand

## Selectors
### Classes
### IDs
### Pseudoelements

## Inheritance

## Specificity


### The cascade: How Browsers Decide Which CSS to Apply
The cascade is defined by these three things, in order of weight (1 outweighs 3):
1) Importance
    - Whichever ruleset is marked as being more important (with an !important flag) will be applied
2) Specificity
    - Whichever ruleset carries greater weight / more specific selectors will be applied.
3) Source Order
    - Whichever ruleset comes last will be applied.

### Importance
- Importance is indicated by **important flags** on individual properties within a selector. For example: 
    ```
    h1 {
        color: red!important;
    }
    ```
    Will make all h1's red regardless of all other styles.
- Only use the important flag when you have exhausted all other options.
- The only thing that can override an important flag is a more specific important flag, as defined by the specificity hierarchy.

### Specificity
Specificity is defined by the following hierarchy:

1) _Inline styles_: An inline style is attached directly to the element to be styled, or is in a style tag in the   `<head>`.

2) _IDs_: An ID is a unique identifier for the page elements, such as #navbar.

3) _Classes, attributes and pseudo-classes_: This category includes .classes, [attributes] and pseudo-classes such as :hover, :focus etc. **Classes should be used whenever possible instead of IDs and element selectors**.

4) _Elements and pseudo-elements_: This category includes element names and pseudo-elements, such as h1, div, :before and :after.

- Note: The universal selector (*) has no specificity value, meaning anything will override it if set.

### Source Order
With all other specificity and importance rules equal, styles defined later in a stylesheet will override those above it (the styles _cascade_). So for example:

    ```
    h1 {
        color: red;
    }
    h1 {
        color: blue;
    }
    ```

Because the second h1 definition comes after the first, the h1 color property will be blue.

### A note on the universal selector
- This is a good use and basically the only use I've ever had for the universal selector: 
```
* { 
  -moz-box-sizing: border-box; 
  -webkit-box-sizing: border-box; 
  box-sizing: border-box; 
}
```

## Vocabulary
- Inline CSS
- Internal stylesheet
- External stylesheet
- Content Delivery Network (CDN)
- Bootstrap
- 



