# advance-css-and-sass
advance-css-and-sass


```html
<nav class="clearfix">
  <ul class="navigation">
    <li><a href="#">About us</a></li>
    <li><a href="#">Pricing</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
  <div class="button">
    <a class="btn-main" href="#">Sign up</a>
    <a class="btn-hot" href="#">Get a quote</a>
  </div>
</nav>     

```

```
$ npm init
$ npm install node-sass --save-dev
$ npm install jquery --save
$ npm uninstall jquery --save

// larazon por la que guardo todo en un archivo json es porque me permite installar todo en otro lado solo haciendo:

$ npm install

$ mkdir sass
$ cd sass
$ touch main.scss

// I have this on my json file:
{
  "name": "starter",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "compile:sass": "node-sass sass/main.scss css/style.css -w"
  },
  "author": "thusspokedata",
  "license": "ISC",
  "devDependencies": {
    "node-sass": "^7.0.1"
  }
}

//to install sass I have to do:
npm run compile:sass   

```



```scss
$color-primary: #55c57a;
$color-primary-light: #55c57a;
$color-primary-dark: #28b485;

$color-gray-dark: #777;
$color-white: #fff;
$color-black: #000;
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: "Lato", sans-serif;
  font-weight: 400;
  font-size: 16px;
  line-height: 1.7;
  color: $color-gray-dark;
  padding: 30px;
}

.header {
  height: 95vh;
  background-image: linear-gradient(
      to right bottom,
      rgba($color-primary-light, 0.8),
      rgba($color-primary-dark, 0.8)
    ),
    url(../img/hero.jpg);
  background-size: cover;
  background-position: top;
  position: relative;
  clip-path: polygon(0 0, 100% 0, 100% 75vh, 0 100%);

  &__logo-box {
    // hermoso!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
    position: absolute;
    top: 40px;
    left: 40px;
  }
  &__logo {
    height: 35px;
  }
  &__text-box {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(
      -50%,
      -50%
    ); /* esto me situa el texto realmente en el medio */
    text-align: center;
  }
}

.heading-primary {
  color: $color-white;
  text-transform: uppercase;

  backface-visibility: hidden; /*esto elimina la subida q hacen las figuras en movimiento luego q se frenan*/
  margin-bottom: 60px;
  &--main {
    display: block;
    font-size: 60px;
    font-weight: 400;
    letter-spacing: 35px;

    animation-name: moveInLeft;
    animation-duration: 1s;
    animation-timing-function: ease-out;

    /*
    animation-delay: 3s;
    animation-iteration-count: 3;
    */
  }

  &--sub {
    display: block;
    font-size: 20px;
    font-weight: 400;
    letter-spacing: 17.4px;

    animation: moveInRight 1s ease-out;
  }
}

@keyframes moveInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100px) rotate(0deg); /*efecto de giro */
  }

  60% {
    transform: rotate(180deg); /*efecto de giro */
  }

  80% {
    transform: translateX(10px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}

@keyframes moveInRight {
  0% {
    opacity: 0;
    transform: translateX(100px);
  }

  80% {
    transform: translateX(-10px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}

@keyframes moveInBottom {
  0% {
    opacity: 0;
    transform: translateY(30px);
  }

  100% {
    opacity: 1;
    transform: translate(0);
  }
}

.btn {
  /* sudo clases son un estado especial de un selector, las usamos para generar condiciones especiales */
  &:link,
  &:visited {
    text-transform: uppercase;
    text-decoration: none;
    padding: 15px 40px;
    display: inline-block;
    border-radius: 100px; /*esto hace el bordeado del boton */
    transition: all 0.2s;
    position: relative;
  }
  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba($color-black, 0.2);

    &::after {
      transform: scaleX(1.4) scaleY(1.6); /* esto nos va a acrecentar el elemento */
      opacity: 0;
    }
  }
  &:active {
    transform: translateY(-1px);
    box-shadow: 0 5px 10px rgba($color-black, 0.2);
  }

  &--white {
    background-color: $color-white;
    color: $color-gray-dark;
    &::after {
      background-color: $color-white;
    }
  }

  &::after {
    content: "";
    display: inline-block;
    height: 100%;
    width: 100%;
    border-radius: 100px;
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1; /* este indice indica la posicion de los elementos si uno está encima del otro */
    transition: all 0.4s;
  }

  &--animated {
    animation: moveInBottom 0.5s ease-out 0.75s; /* el .75s es un delay que hace q la figura aparezca mas tarde q las demas */
    animation-fill-mode: backwards; /* esto va a hacer que se apliquen automaticamente los estilos hasta un 0% antes que comience la animacion */
  }
}


```
