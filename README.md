# Great-CSS-Tips-You-Should-Know
A useful CSS tips collection for everyone to use CSS more efficiently.

## Contents

- [Use CSS to center everything vertically](#use-css-to-center-everything-vertically)
- [Use CSS to make a arrow](#use-css-to-make-an-arrow)
- [Use CSS to make the footer always at bottom and go with the content](#use-css-to-make-the-footer-always-at-bottom-and-go-with-the-content)
- [Use CSS to prevent image beyond the content](#use-css-to-prevent-image-beyond-the-content)
- [Use CSS to make a navigation with divide lines](#use-css-to-make-a-navigation-width-divide-lines)
- [Use CSS to define the height of an element by calculation](#use-css-to-define-the-height-of-an-element-by-calculation)
- [Use CSS to set a full page background image](#use-css-to-set-a-full-page-background-image)
- [Use CSS's BFC to clear float](#use-css's-bfc-toclear-float)
- [Use CSS to set the width of a div equal to the image](#use-css-to-set-the-width-of-a-div-equal-to-the-image)
- [Use CSS to preload images](#use-css-to-preload-images)
- [Use CSS to avoid blink](#use-css-to-avoid-blink)
- [Use CSS to make style broken images](#use-css-to-make-style-broken-images)

### Use CSS to center everything vertically

It's just a so easy method to center your every element vertically.

```css
html, body {
  height: 100%;
  margin: 0;
}

body {
  display: -webkit-flex;
  display: flex;
  -webkit-align-items: center;  
  -ms-flex-align: center;  
  align-items: center;
}
```

If this method doesn't fit your needs--if you want to center an element both vertically and horizontally, you should check out my another repository: [css-center-complete](https://github.com/Erichain/css-center-complete).

### Use CSS to make a arrow

So, how to use css to get a shape? Such as an arrow or a caret we will use frequently. just as following:

```css
// a down-caret 
.caret {
	display: inline-block;
	width: 0;
	height: 0;

	vertical-align: middle;
	
	// if need a up-caret, change the border-top to border-bottom
	border-top: 20px solid;
	border-right: 20px solid transparent;
	border-left: 20px solid transparent;
}
```

### Use CSS to make the footer always at bottom and go with the content

Well, I've been troubled by this problem several times. And finally I find a best method to solve this problem.

Assume you have the following marks

```html
<div class="header"></div>
<div class="content"></div>
<div class="footer"></div>
```

I want the footer at the bottom even our content is not full enough. Meanwhile, if the content is growing, I want the footer to move with the content's growing. So, how to deal with it? Just write the css code as following:

```css
html {
	height: 100%;
}

body {
	position: relative;
	min-height: 100%;

	&:after {
		display: block;
		content: '';
		height: 200px; // the height must be equal to the height of the footer
	}
}

.footer {
	position: absolute;
	bottom: 0;
	width: 100%;
	height: 200px;
}
```

### Use CSS to prevent image beyond the content

We have large images, we want to use them in our articles or any other palces. So, how to prevent the images' width beyond our content?

```css
img {
    display: block;
    max-width: 100%;
    margin: 0 auto;
}
```

### Use CSS to make a navigation with divide lines

We want make a navigation with divide lines between every two options, so we can use the `:not` and `:last-child` to make it work!

```css
.nav li:not(:last-child) {
    border-right: 1px solid #cccccc;
}
```

### Use CSS to define the height of an element by calculation

As everyone know that the `calc` property of CSS3 is a great property. We can use it to define the height of an element by calculation.

> When you use the calc to calculate the height of an element you should note that, the height the calc calculates is based on the height of the parent element. So you should set the height of the parent element first to use calc to calculate the height of the element.

```css
.container {
    height: 100vh;  // use the vh to set the parent element's height to 100%
}

.content {
  width: 100%;  
  height: calc(100% - 150px);
  background-color: #aaaaaa;
}
```

### Use CSS to set a full page background image

### Use CSS's BFC to clear float

To clear float, we can use the property of BFC.

As you know, when calculating the height of a BFC, floated element's height will be included.

```css
.container {
    width: 800px;
    padding: 20px;
    border: 1px solid #aaaaaa;
    overflow: hidden; // or set to auto
}
```

### Use CSS to set the width of a div equal to the image

If we want to add an image inside a div, we just write img tag inside a div tag.

However, there is a problem that there is some space between the div's border and the image's border.

So, how to deal with it? The solution is easy:

```css
.container {
    font-size: 0; // yes, just use this expression
}
```

### Use CSS to preload images

```css
#preload-01 { background: url(http://domain.tld/image-01.png) no-repeat -9999px -9999px; }
#preload-02 { background: url(http://domain.tld/image-02.png) no-repeat -9999px -9999px; }
#preload-03 { background: url(http://domain.tld/image-03.png) no-repeat -9999px -9999px; }
```

### Use CSS to avoid blink

### Use CSS to make style broken images

Make broken images more aesthetically-pleasing with a little bit of CSS:

```css
img:before {  
  content: "We're sorry, the image below is broken :(";
  display: block;
  margin-bottom: 10px;
}

img:after {  
  content: "(url: " attr(src) ")";
  display: block;
  font-size: 12px;
}
```

## Contribution

- Fork the repo to your own account
- Make a new branch to add your advice to css tips
- Make a pull request

## License
Release under the [MIT License](https://github.com/Erichain/Great-CSS-Tips-You-Should-Know/blob/master/LICENSE).