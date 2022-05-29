<img src="https://github.com/thusspokedata/dev-advanced-css-and-sass/blob/main/images/grid.png">

```html
<div class="container">
  <div class="item item--1">1: Orange</div>
  <div class="item item--2">2: Green</div>
  <div class="item item--3">3: Violet</div>
  <div class="item item--4">4: Pink</div>
  <div class="item item--5">5: Blue</div>
  <div class="item item--6">6: Brown</div>
</div>

```

**scss:**

```scss

.container {
  background-color: #eee;
  width: 1000px;
  margin: 30px auto;
  
  // height: 1000px;

  display: grid;
  grid-template-rows: repeat(2, 150px);
  //grid-template-rows: repeat(2, 1fr);
  // grid-template-columns: repeat(2,150px) 1fr; //1fr toma el resto del espacio
  grid-template-columns: repeat(3, 1fr); // todos igual tamaño
  // grid-template-columns: 1fr 2fr 1fr;
  // grid-template-columns: 50% 1fr 2fr;
  
  
  // grid-row-gap: 20px;
  // grid-column-gap: 20px;
  grid-gap: 30px;
}

.item {
  padding: 20px;
  font-size: 30px;
  font-family: sans-serif;
  color: white;
  
  &--1 {
    background: orangered;
  }
  &--2 {
    background: yellowgreen;
  }
  &--3 {
    background: blueviolet;
  }
  &--4 {
    background: palevioletred;
  }
  &--5 {
    background: royalblue;
  }
  &--6 {
    background: goldenrod;
  }
}


