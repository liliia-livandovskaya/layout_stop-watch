1. [LAYOUT] - Don't forget about semantics, div development is not a better
   option
2. [STYLES] - Get used to style all elements using classes. And don't increase
   selectors specificity unless completely necessary.
3. [STYLES] - If you need to adjust positioning with `1px` or fractional numbers
   like `0.5`, you are doing something wrong, change the alignment technique you use
4. [STYLES] - Be consistent with your margins - if you have many sections in a
   row, add margins either to the bottom or to the top so that it will be easier
   to identify how to position the next element
5. [BEM] - Check your BEM structure using BEM-linter (`npm run lint`) and
   [this list](https://mate-academy.github.io/fe-program/css/typical-bem-mistakes)
6. [BEM] - Make sure to follow BEM naming convention

GOOD example:
```html
<div class="product__rating">
  <div class="product__stars stars stars--4">
    <div class="stars__star"></div>
    <div class="stars__star"></div>
    <div class="stars__star"></div>
    <div class="stars__star"></div>
    <div class="stars__star"></div>
  </div>
</div>
```

BAD example:
```html
<div class="product__rating">
  <div class="product__stars stars--4">
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
    <div class="star"></div>
  </div>
</div>

`stars--4` is a modifier of the `stars` block, but `stars` block does not exist in HTML;
`star` is another block, stars should be the elements of the `stars` block
```

7. [BEM & STYLES] - Don't add external styles (positioning or margins) to
   BEM-blocks. Use mix where necessary and move all external styles under element
   selector.

GOOD example
```html
<!--index.html-->
<div class="container">
  <div class="container__card card">
    ...
  </div>
</div>
```
```css
/*style.css*/
.container__card {
  margin: 48px 24px;
}

.card {
  font-size: 16px;
  background-color: purple;
}
```

BAD example
```html
<!--index.html-->
<div class="container">
  <div class="card">
    ...
  </div>
</div>
```
```css
/*style.css*/
.card {
  margin: 48px 24px;
  font-size: 16px;
  background-color: purple;
}
```

8. [SASS] - Make use of SASS nesting - write pseudo-class, pseudo-element
   selectors inside general selector. As well as media queries.

GOOD example:
```scss
&__buy-link {
  display: flex;
  margin-top: 20px;

  &:hover {
    color: blue;
  }
}
```

BAD example:
```scss
&__buy-link {
  display: flex;
  margin-top: 20px;
}

&__buy-link:hover {
  color: blue;
}
```

9. [SASS] - use variables for the main values so that you'll be able to reuse
    them and give them descriptive names. But don't overuse them, don't create
    variable for the value that's used just once.
10. [SASS] - Try to use different features - mixins etc - where it makes sense.
11. [CODE STYLE] - Remember about styles properties order - ([css order](https://codeguide.academy/html-css.html#css-order))
