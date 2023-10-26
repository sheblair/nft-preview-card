# NFT preview card

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Update 2023](#update-2023)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](/images/nft-preview-card-screenshot.png)

### Links

- [Solution](https://www.frontendmentor.io/solutions/nft-preview-card-with-vanilla-css-YhzCIBOtTt)
- [Live Site](https://sheblair.github.io/nft-preview-card/)

## My process

1. Okay so I started this challenge before I was in the habit of taking notes and documenting my process, so I don't have any notes from the first stage of building it. Now it's some weeks later and I'm coming back to finish it. And from what I recall, most of it I built without difficulty but I remember where I got stuck--it was in creating the overlay for the image upon hover/active states.
2. Before I tackled the card overlay, I fixed some alignment issues with the icons in the pricing and timing information. I moved them into separate HTML elements, switched justify-content from space-between to flex-start, and added padding to space them out. I also tweaked padding in the profile icon for the creator.
3. To figure out the card overlay, since I'd never done this before, I decided to take the code from another user's solution and then work backwards to figure out how it worked. I used @correlucas' solution. This worked well--it was pretty easy to see what he'd done and to figure out how it worked. I ran into a couple of weird issues though:
   - First, the icon wasn't sizing correctly. I figured out this was because of how I'd written my HTML and how I was referencing elements in my CSS, so I fixed that and resized it correctly.
   - Secondly, there was this tiny overhang, where the bottom of the overlay extended a handful of pixels or so past the bottom of the image. I tried so many different things to make the height of the image fill the size of the parent div, to remove the overhang. I tried to fix it by adjusting the height from 100% to 99%, which in DevTools only showed me that the correct height would lie somewhere in between 99 and 100% -- no good. I finally figured this out by going back to @correlucas' solution code: I needed to set the display property to block. Once I did that, the image and overlay aligned perfectly. Done (with mobile styles)!
4. To write the desktop styles I only had to reduce the width of the content wrapper to 25% and added a drop shadow filter.

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- Mobile-first workflow

### What I learned

- Why you should use classes vs. ids. I'm still learning this, but for a long time I couldn't figure out why people used classes more than ids, because I was thinking oh well ids must be better, because they are more specific and then you can just use CSS to tell each specific element on your page exactly what you want it to do. But the more I write code, the more I realize that often what is more useful is being able to layer effects on and off elements, and in order to do this you need to use classes.

Here's the code for the card overlay, that I took from @correlucas (a user on Frontend Mentor). He had also added some transitions that were definitely nice but I removed them because I wanted to first just understand the bare bones of what he did:

```css
.card-overlay {
  display: flex;
  position: absolute;
  border-radius: 10px;

  align-items: center;
  justify-content: center;
  flex-direction: column;

  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: hsl(178, 100%, 50%, 0.5);
  opacity: 0;
}

.card-overlay:hover {
  opacity: 1;
}
```

### Continued development

Things to keep working on:

- On using classes vs. ids
- On display: block and display: inline and how they affect layouts
- On hover effects and overlay
- On accurate referencing of elements in CSS and how to make your life easier in this regard
  - Actually, codepip games were useful for this and I learned a lot more about selector specificity and practiced a lot using them. I'll link below.

### Update 2023

I came back to take a look at this and see what could be improved - the setup was mostly good, but I rewrote my class names and tweaked a couple of minor flexbox details. Minor cleanup stuff but it makes a big difference.

### Useful resources

- [@correlucas' solution to the challenge on Frontend Mentor](https://www.frontendmentor.io/solutions/nft-preview-card-vanilla-css-custom-design-and-hover-effects-zVKSAE5IXI) - This solution code helped me figure out how to add a card overlay effect upon hover.
- [Codepip Games](https://codepip.com/) - These games, and especially Selector Showdown, helped me improve my knowledge of selector specificity.

## Author

- [Sheila Blair](https://www.frontendmentor.io/profile/sheblair)

## Acknowledgments

Huge thanks to @correlucas on Frontend Mentor! Relying on others' solution code is such an helpful thing and one of the aspects I love most about learning to code. That we can all help each other out, and I so appreciate people sharing their work. Such a great way to learn.
