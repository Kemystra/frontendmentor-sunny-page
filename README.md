# Frontend Mentor - Sunnyside agency landing page solution

This is a solution to the [Sunnyside agency landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/sunnyside-agency-landing-page-7yVs3B6ef). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

![](./screenshot.jpg)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.

Alternatively, you can use a tool like [FireShot](https://getfireshot.com/) to take the screenshot. FireShot has a free option, so you don't need to purchase it.

Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

**Note: Delete this note and the paragraphs above when you add your screenshot. If you prefer not to add a screenshot, feel free to remove this entire section.**

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library
- [Next.js](https://nextjs.org/) - React framework
- [Styled Components](https://styled-components.com/) - For styles

**Note: These are just examples. Delete this note and replace the list above with your own choices**

### What I learned

1. CSS Orders
I can specify which order an element should be in a flexbox!

```css
#first-div {
    order: 2;
}

#second-div {
    order: 1;
}
```

2. CSS Clip Path
Can be used to crop pictures into desired shapes.
```css
#image {
    // Crop image into a circle of 50% radius
    // right at the center
    clip-path: circle(50% at 50% 50%)
}
```

3. SCSS @each
Very useful to write repetitive CSS!
```scss
// Specify order of children of #promote in its grid.
$element-orders: (
	--transform-brand-text-order: 1,
	--transform-brand-image-order: 2,
	--standout-image-order: 3,
	--standout-text-order: 4,
	--graphic-design-order: 5,
	--photo-order: 6
);

#promote {
    display: grid;
    grid-template-columns: repeat(2, 1fr);

	$i: 0;
	@each $varname, $order in $element-orders {
		#{$varname}: $order;
		$i: $i + 1;

		& > :nth-child(#{$i}) {
			order: var(#{$varname});
		}	
	}
}
```

4. SCSS Imports
Used it to separate files. Really nice, considering that I was working with a single file with 500+ LOC CSS for this challenge. I spent some time refactoring it after realizing this feature, and it was definitely worth it!
```scss
// Import the file '_test.scss'
@use 'test';

// This one imports, but also forwards it.
// The file that will use this file will also be able to use that file.
@forward 'file_that_the_main_file_also_needs';
```

5. Default \<img\> `display` value
It turns out by default, \<img\> have `display: inline-block`, which causes a small gap underneath the image. Its super annoying, and next time I will just do:
```css
// Place this first!
img {
    diplay: block;
}
```

6. \<a\> behaviour without `href` attribute.
The tag will only show the pointer cursor when `href` attribute is present (even if it's empty). Wasted quite a bit of time wondering why the cursor won't change when hovering over an \<a\> tag.

### Continued development

Use this section to outline areas that you want to continue focusing on in future projects. These could be concepts you're still not completely comfortable with or techniques you found useful that you want to refine and perfect.

**Note: Delete this note and the content within this section and replace with your own plans for continued development.**

### Useful resources

- [CSS Tricks: How to Scale SVG](https://css-tricks.com/scale-svg/) - Helped me in finding ways to resizing SVGs, which is used in the site's logo.
-[CSS Tricks: Approaches to Media Queries in Sass](https://css-tricks.com/approaches-media-queries-sass/) - Really opened my eyes to the true power of SASS; I was just a casual @mixin user until now.
- [MDN Web Docs on CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) - Too much to list here but I just want to mention on the abundant methods to use justify-* with Flexbox.

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)

**Note: Delete this note and add/remove/edit lines above based on what links you'd like to share.**

## Acknowledgments

This is where you can give a hat tip to anyone who helped you out on this project. Perhaps you worked in a team or got some inspiration from someone else's solution. This is the perfect place to give them some credit.

**Note: Delete this note and edit this section's content as necessary. If you completed this challenge by yourself, feel free to delete this section entirely.**
