# Simple Scroll animate using pure JavaScript function

## Description : this simple tutorial teach you to make a simple scroll animate using css and js pure in HTML layout.

- Tecnologies : HTML , CSS and JavaScript

---

### Getting start

#### First step : Create your HTML code

```html
<html lang="en">
  <head>
    your head content
  </head>
  <body>
    your page content
  </body>
</html>
```

#### Second step : Create your CSS code

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
... your css code;
```

#### Third step : Add data type in your HTML content you want animate

```html
<header class="header-style" data-animate="left"></header>
<main class="main-style" data-animate="right"></main>
<footer class="footer-style" data-animate="left"></footer>
```

#### Fourth step : Add animation style to your content

```css
[data-animate] {
  opacity: 0;
  transition: 0.3s;
}

[data-animate="left"] {
  transform: translate3d(-50px, 0, 0);
}

[data-animate="right"] {
  transform: translate3d(50px, 0, 0);
}
```

#### Fifth step : Add the class using to animate

```css
[data-animate].animate {
  opacity: 1;
  transform: translate3d(0, 0, 0);
}
```

#### Sixth step : Create the JavaScript code

- Create the const's

```javascript
const target = document.querySelectorAll("[data-animate]");
const animateClassName = "animate";
```

- Create Function anime Scroll

```javascript
...const's

function animeScroll() {}
```

- Calculate the distance from each element to the top of the page

```javascript
...const's

function animeScroll() {
  const windowTop = window.pageYOffset + (window.innerHeight * 3) / 4;
}
```

- Select each target to aply the animate using classList property

```javascript
...const's

function animeScroll() {
  const windowTop = window.pageYOffset + (window.innerHeight * 3) / 4;
  target.forEach(function (element) {
    if (windowTop > element.offsetTop) {
      element.classList.add(animateClassName);
      return;
    }
    element.classList.remove(animateClassName);
  });
}
```

- Call the function on start page

```javascript
...const's

...function(){

}

animeScroll();

```

- Using the function if data-aniamte existing using debounce function

```javascript
...const's

...function(){

}

animeScroll();

if (target.length) {
  window.addEventListener(
    "scroll",
    debounce(function () {
      animeScroll();
      console.log("teste");
    }, 200)
  );
}

```

- Create debounce function in script to have a delay in the function to improve performance of the page

```javascript

const debounce = function (func, wait, immediate) {
  let timeout;
  return function (...args) {
    const context = this;
    const later = function () {
      timeout = null;
      if (!immediate) func.apply(context, args);
    };
    const callNow = immediate && !timeout;
    clearTimeout(timeout);
    timeout = setTimeout(later, wait);
    if (callNow) func.apply(context, args);
  };
};

...const's

...function(){

}

animeScroll();

```

- Using the function if data-aniamte existing and use debounce function

```javascript
...const's

...function(){

}

animeScroll();

if (target.length) {
    ... debounce function
}

```

---

## That's all Folks, you learn to create a simple JS animate Scroll! :brain: :call_me_hand:
