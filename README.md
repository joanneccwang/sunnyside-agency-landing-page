# Frontend Mentor - Sunnyside agency landing page solution

This is a solution to the [Sunnyside agency landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/sunnyside-agency-landing-page-7yVs3B6ef). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Vue3 with Vite
- CSS variables
- Flexbox
- Mobile-first workflow


### What I learned

- Getting familiar with Vite
- Getting familiar with Vue3 Composition API
- Passing data in Vue component using `provide` and `inject`
- Change svg color to white using `filter` property: [Reference from Stackoverflow](https://stackoverflow.com/questions/24224112/css-filter-make-color-image-with-transparency-white)
```css
  img:hover {
    filter: brightness(0) invert(1); 
  }
```

- Work with JS media queries using window.matchMediaQuery() method : [Reference from CSS Tricks](https://css-tricks.com/working-with-javascript-media-queries/)
```javascript
// Create a media condition that targets viewports at least 768px wide
const mediaQuery = window.matchMedia('(min-width: 768px)')
const handleMediaQueryChanged = (e) => {
  // Check if the media query is true
  if (e.matches) {
    // Then log the following message to the console
    console.log('Media Query Changed!')
  }
}
// Register event listener
mediaQuery.addListener(handleMediaQueryChanged)
// Initial check
handleTabletChange(mediaQuery)
```

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@joanneccwang](https://www.frontendmentor.io/profile/joanneccwang)