# Frontend Mentor - Product preview card component

![Design preview for the Product preview card component coding challenge](./Project%20Requirements/design/desktop-preview.jpg)

## 🌍 Overview

This component is a beginner project from [Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa/hub). I wanted to build this project to stay connected to my CSS skills.

As with any skill, if you don't use it, you lose it. 😫 So this little build is a part of my ongoing professional development.

You can see a couple of other little, cutie builds [here](https://github.com/crwainstock/fe-mentor-qr) and [here](https://github.com/crwainstock/fe-mentor-3-column-preview-card) and [here](https://github.com/crwainstock/fe-mentor-single-price-grid) and [here](https://github.com/crwainstock/fe-mentor-order-summary).

## 🛠️ Technologies & Dependencies

This component was built with HTML and vanilla CSS and a tiny bit of vanilla JavaScript. No dependencies! 🥳 I also used [PerfectPixel](https://www.welldonecode.com/perfectpixel/) and the [Eye Dropper/Color Picker](https://eyedropper.org/) browser extensions to help with the build.

I deployed the component with Netlify, though, so check that out [here](https://reliable-cupcake-1661bb.netlify.app/).

## 🤔 Reflection

In the [last Frontend Mentor build](https://github.com/crwainstock/fe-mentor-stats-preview) I did, the brief required two different images to be rendered depending on whether the component was being viewed on a desktop or mobile screen. I tried to use [picture and source elements in HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/picture), but I didn't quite get it to work as intended.

This component also required multiple images to be rendered depending on the view, and again, I couldn't get the html to work the way I needed it to. With this build, though, I decided to make a workaround using vanilla JavaScript to check the screensize and then render the image for either the mobile or desktop view.

The JavaScript function is as follows:

```
      const screenWidth = window.screen.width;
      let imgSrc = null;
      const loadImage = () => {
        if (screenWidth <= 660) {
          imgSrc = "./Project Requirements/images/image-product-mobile.jpg";
        } else {
          imgSrc = "./Project Requirements/images/image-product-desktop.jpg";
        }
        const productImage = document.getElementById("product-image");
        productImage.src = imgSrc;
      };

      loadImage();
```

This solution works for the initial render, but if you manually change screen size, by changing the browser window, for example, the image doesn't update unless you refresh it.

I also tried using an event listener to run the loadImage function when the window is resized, but it wasn't working quite the way I had hoped. While all of this allows each image to render based on the screen view, it's not, perhaps, the ideal solution to this issue.

I think there is also some layout weirdness when screens get below 400px wide. With a bit more time, these issues could be resolved pretty easily, though, I think.

## 👀 Demo & Live Version

Check out the live version of this component [here](https://reliable-cupcake-1661bb.netlify.app/).

And here's a little look at how the desktop version of the component compares with the design from the brief.
![gif comparing desktop view](./product%20compare.gif)
