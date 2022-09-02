# Frontend Mentor - NFT preview card component solution

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
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

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

1. Okay so I started this challenge before I was in the habit of taking notes and documenting my process, so I don't have any notes from the first stage of building it. Now it's some weeks later and I'm coming back to finish it. And from what I recall, most of it I built without difficulty but I remember where I got stuck--it was in creating the overlay for the image upon hover/active states.
2. Before I tackled the card overlay, I fixed some alignment issues with the icons in the pricing and timing information. I moved them into separate HTML elements, switched justify-content from space-between to flex-start, and added padding to space them out. I also tweaked padding in the profile icon for the creator.
3. To figure out the card overlay, since I'd never done this before, I decided to take the code from another user's solution and then work backwards to figure out how it worked. I used @correlucas' solution. This worked well--it was pretty easy to see what he'd done and to figure out how it worked. I ran into a couple of weird issues though:
  - First, the icon wasn't sizing correctly. I figured out this was because of how I'd written my HTML and how I was referencing elements in my CSS, so I fixed that and resized it correctly.
  - Secondly, there was this tiny overhang, where the bottom of the overlay extended a handful of pixels or so past the bottom of the image. I tried so many different things to make the height of the image fill the size of the parent div, to remove the overhang. I tried to fix it by adjusting the height from 100% to 99%, which in DevTools only showed me that the correct height would lie somewhere in between 99 and 100% -- no good. I finally figured this out by going back to @correlucas' solution code: I needed to set the display property to block. Once I did that, the image and overlay aligned perfectly. Done (with mobile styles)!

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

- Why you should use classes vs. ids. I'm still learning this, but for a long time I couldn't figure out why people used classes more than ids, because I was thinking oh well ids must be better, because they are more specific and then you can just use CSS to tell each specific element on your page exactly what you want it to do. But the more I write code, the more I realize that often what is more useful is being able to layer effects on and off elements, and in order to do this you need to use classes.

Here's the code for the card overlay, that I took from @correlucas. He had also added some transitions that were definitely nice but I removed them because I wanted to first just understand the bare bones of what he did:
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

- On using classes vs. ids
- On display: block and display: inline and how they affect layouts
- On hover effects and overlay
- On accurate referencing of elements in CSS and how to make your life easier in this regard
  - Actually, codepip games were useful for this and I learned a lot more about selector specificity and practiced a lot using them. I'll link below.

### Useful resources

- [Example resource 1](https://www.example.com) - This helped me for XYZ reason. I really liked this pattern and will use it going forward.
- [Example resource 2](https://www.example.com) - This is an amazing article which helped me finally understand XYZ. I'd recommend it to anyone still learning this concept.

**Note: Delete this note and replace the list above with resources that helped you during the challenge. These could come in handy for anyone viewing your solution or for yourself when you look back on this project in the future.**

## Author

- Website - [Add your name here](https://www.your-site.com)
- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/yourusername)
- Twitter - [@yourusername](https://www.twitter.com/yourusername)

**Note: Delete this note and add/remove/edit lines above based on what links you'd like to share.**

## Acknowledgments

This is where you can give a hat tip to anyone who helped you out on this project. Perhaps you worked in a team or got some inspiration from someone else's solution. This is the perfect place to give them some credit.

**Note: Delete this note and edit this section's content as necessary. If you completed this challenge by yourself, feel free to delete this section entirely.**
